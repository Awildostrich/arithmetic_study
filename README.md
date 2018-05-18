![听话狗](https://github.com/awildostrich/arithmetic_study/blob/master/images/%E5%90%AC%E8%AF%9D%E7%8B%97.gif)

关于自己算法学习过程的记录和一些笔记，同时熟悉 Git 管理代码的过程。

<<<<<<< HEAD
[2. 实现 Singleton](#2-实现-singleton)

=======
[xx](# 0)
>>>>>>> 4702111ac2c8a1504141842a56b334fac827dbef
- [1. best-time-to-buy-and-sell-stock](# 1. best-time-to-buy-and-sell-stock)
- [2. ##](2. ##)
# 0

# 1. best-time-to-buy-and-sell-stock

C ++ 代码实现：

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



# 2. 实现 Singleton

[单例模式](https://github.com/CyC2018/Interview-Notebook/blob/master/notes/%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F.md)