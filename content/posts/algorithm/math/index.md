---
title: "数学相关算法题推荐"
date: 2021-04-09T09:33:20+08:00
hero: math.jpg
menu:
 sidebar:
  name: 数学算法题
  parent: algorithm
  identifier: math-algorithm
  weight: 1
math: true
---

数学是计算机的重要基础，算法题中常常会用到数学知识，尤其是离散、具体的数学，以数论、排列组合、概率期望、多项式为代表，可以出现在几乎任何类别的题目中，所有题目涉及到的数学知识点都已标出，建议去[oi-wiki](https://oi-wiki.org/basic/) 学习。
> 强烈建议小伙伴先尝试用非数学的常规解法思考以下题目（也许会更简单更好理解），再用数学的解法。
## 第一周

### 5月3日

- 开胃小菜: [斐波那契数列](https://leetcode-cn.com/problems/fei-bo-na-qi-shu-lie-lcof/) ，在这道题中，你会学到算法题中必会的一个数学知识点 [中国剩余定理](https://oi-wiki.org/math/crt/) 。建议独自完成四种做法，并完成[快速幂](https://oi-wiki.org/math/quick-pow/) 的普通写法（模版）以及[公式法](https://oi-wiki.org/math/fibonacci/) 。 
- [灯泡开关](https://leetcode-cn.com/problems/bulb-switcher/) 尝试使用数学的思维分析`n`轮后灯泡亮着必须满足什么条件。

### 5月5日

- [超级丑数](https://leetcode-cn.com/problems/super-ugly-number/) 做这题之前先学习求[质数的几种方法](https://oi-wiki.org/math/prime/) （强烈建议掌握）,之后只需要思考如果求出第n个即可.
- [石子游戏](https://leetcode-cn.com/problems/stone-game/) 经典的石子游戏肯定是不能错过的，建议用动态规划解一遍。

### 5月7日

- [循环码排列](https://leetcode-cn.com/problems/circular-permutation-in-binary-representation/) ，可以先用朴素做法，再了解[格雷码](https://oi-wiki.org/misc/gray-code/) ，优化解法。
- [飞机座位](https://leetcode-cn.com/problems/airplane-seat-assignment-probability/) 这道题是很明显可以利用数学优化的题目。

## 第二周

### 5月12日

- [各位相加](https://leetcode-cn.com/problems/add-digits/) 尽量优化你的时间复杂度和空间复杂度至 $O(1)$ 。
- 放松一下： [不浪费原料的汉堡制作方案](https://leetcode-cn.com/problems/number-of-burgers-with-no-waste-of-ingredients/) 我愿称之为最简单中等题。

### 5月14日

- [使数组和能被 P 整除](https://leetcode-cn.com/problems/make-sum-divisible-by-p/) 剩余定理的应用，加上前缀和的思想。
- [最简分数](https://leetcode-cn.com/problems/simplified-fractions/) 思路很简单，可以学习到求[最大公约](https://oi-wiki.org/math/gcd/) 数的做法。

### 5月16日

- [检查「好数组」](https://leetcode-cn.com/problems/check-if-it-is-a-good-array/) 建议了解[裴蜀定理](https://oi-wiki.org/math/bezouts/) 之后再做这题，通过这个定理你还可以解决以下题目
   - [水壶问题](https://leetcode-cn.com/problems/water-and-jug-problem/)
- [安排邮筒](https://leetcode-cn.com/problems/allocate-mailboxes/) 动态规划中数学的应用，中位数的思想非常常用。

## 第三周

### 5月19日

- [剪绳子 II](https://leetcode-cn.com/problems/jian-sheng-zi-ii-lcof/) leetcode中有许多类似的题目掌握其中的思想，就能解决许多类似的问题：
    - [剪绳子](https://leetcode-cn.com/problems/jian-sheng-zi-lcof/)
    - [整数拆分](https://leetcode-cn.com/problems/integer-break/)
    - [好因子的最大数目](https://leetcode-cn.com/problems/maximize-number-of-nice-divisors/)
    - ...
- [构造乘积数组](https://leetcode-cn.com/problems/gou-jian-cheng-ji-shu-zu-lcof/) 记得考虑特殊情况。

### 5月21日

- [字符串相乘](https://leetcode-cn.com/problems/multiply-strings/) 高精度计算，行列式模拟即可。
- [航班预订](https://leetcode-cn.com/problems/corporate-flight-bookings/) 本题可以利用[差分](https://oi-wiki.org/basic/prefix-sum/#_6) 的思想来快速求解区间和（对于不会线段树和树状数组的小伙伴是很有利的）。

### 5月23日

- [石子游戏5](https://leetcode-cn.com/problems/stone-game-iv/) 石子游戏又来啦。
- [完全平方数](https://leetcode-cn.com/problems/perfect-squares/) 可以先尝试搜索算法，再看数学解答 [拉格朗日四平方定理](https://leetcode-cn.com/problems/perfect-squares/solution/wan-quan-ping-fang-shu-by-leetcode/) 。

## 第四周

### 5月26日

- [阶乘后的零](https://leetcode-cn.com/problems/factorial-trailing-zeroes/) ，我们只需要思考什么数相乘会等于零。
- [阶乘函数后 K 个零](https://leetcode-cn.com/problems/preimage-size-of-factorial-zeroes-function/) 有了上面的基础这题就会容易一些。

### 5月28日

- [形成两个异或相等数组的三元组数目](https://leetcode-cn.com/problems/count-triplets-that-can-form-two-arrays-of-equal-xor/) 思考如何利用异或的性质。
- [消失的两个数](https://leetcode-cn.com/problems/missing-two-lcci/) 希望能用三中解法解决本题其中位运算法和[此题](https://leetcode-cn.com/problems/single-number-iii/) 相似

### 5月30日
#### 结业考试

- [乐团站位](https://leetcode-cn.com/problems/SNJvJP/) 思考怎样通过坐标判断是第几圈， 总结每圈的公式。（本题是全站通过率最低的简单题）
- [奇妙序列](https://leetcode-cn.com/problems/fancy-sequence/) 预备知识：[乘法逆元](https://oi-wiki.org/math/inverse/) +快速幂+剩余定理。
  有能力的小伙伴也可以用树状数组来解答。 （本题是全站通过率最低的困难题）
