![听话狗](https://github.com/awildostrich/arithmetic_study/blob/master/images/%E5%90%AC%E8%AF%9D%E7%8B%97.gif)

关于自己算法学习过程的记录和一些笔记，同时熟悉 Git 管理代码的过程。
[1. 买卖股票的最佳时机](#1.买卖股票的最佳时机)

# 1.买卖股票的最佳时机
## 题目
给定一个数组，它的第 i 个元素是一支给定股票第 i 天的价格。

如果你最多只允许完成一笔交易（即买入和卖出一支股票），设计一个算法来计算你所能获取的最大利润。

注意你不能在买入股票前卖出股票。

## 示例 1:
`
输入: [7,1,5,3,6,4]
输出: 5
解释: 在第 2 天（股票价格 = 1）的时候买入，在第 5 天（股票价格 = 6）的时候卖出，最大利润 = 6-1 = 5 。
     注意利润不能是 7-1 = 6, 因为卖出价格需要大于买入价格。
`
## 示例 2:
`
输入: [7,6,4,3,1]
输出: 0
解释: 在这种情况下, 没有交易完成, 所以最大利润为 0。
`

## C ++ 代码实现：

```c++
class Solution {
public:
	int maxProfit(vector<int>& prices) {
		int n = prices.size();
		if(n <= 1) return 0;
		std::vector<int> prices_wave;
		for(int i = 0; i < n; i ++){
			prices_wave.push_back(prices[i+1] - prices[i]);
		}
		int max = 0, res = 0;
		for(int i = 0; i < n-1; i ++){
			max += prices_wave[i];
			if(max > res){
				res = max;
			}else if(max < 0){
				max = 0;
			}
		}
		return res;
    }
};
```
