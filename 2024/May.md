# 5-10
比赛
| **Name**                                                   | **solved** | **A** | **B** | **C** | **D** | **E** | **F** | **G** | **Rank** | **Rating**       |
| ---------------------------------------------------------- | :--------: | ----- | ----- | ----- | ----- | ----- | ----- | ----- | -------- | ---------------- |
| [cf round 944(Div.4)](https://codeforces.com/contest/1971) |     4      | Ο     | Ο     | Ο     | Ο     | Ø     | Ø     | !     | 3198     | 1194 &rarr; 1236 |

E题被卡精度了qwq。应该先乘后除可以减少精度丢失。

# 5-13
- [Card Game-cf1400](https://codeforces.com/contest/1932/problem/D)
一道模拟题，可以用优先队列实现，出队就能满足要求。当时队列名写错队列空弹RE了好几发，一直debug,最后还是Chatgpt检查出的拼写错误。
- [Vlad and a Sum of Sum of Digits-cf1200](https://codeforces.com/contest/1926/problem/C)
直接按题目要求来即可，当时还在想有什么规律qwq。
- [Informatics in MAC-cf1200](https://codeforces.com/problemset/problem/1935/B)
多个mex子数组数组最终可以等效为两个mex数组。

# 5-14
- [Reverse Card (Easy Version)-cf1400](https://codeforces.com/contest/1972/problem/D1)
数学题，找到结论直接枚举即可  
如果gcd(a,b) = g , a = p\*g, b = q\*g.可证gcd(p,q) = 1(反证)。 
化简p = q(kg - 1),则根据gcd(p,q) = 1, kg - 1 >= 1,可知q = 1。  
根据q = 1原式子化简 a+b = kb\*b,根据1 =< a <= n,可得(1+b)/b\*b =< k <= (n+b) / b\*b。
注意到当且仅当b = 1 时 k >= 2,所以ans最后减掉1。

# 5-15
- [Minimizing the Sum-cf1700](https://codeforces.com/contest/1969/problem/C)
DP
对于任意一个满足题意的最终序列，其中有若干个连续区间，每个区间的值经过变换都相等。
对于每一个s[i][j], 遍历i次求所有可能的最小值，必定会保留最终的序列的最小值。
- [Circle Perimeter-cf1600](https://codeforces.com/contest/1971/problem/F)
几何
算1/4半圆所有内含的点后*4，相邻半径圆内含半径相减即为答案。优化的思路有点奇怪，不过数据不强Ac了。

# 5-16
- [How Does the Rook Move?-cf1600](https://codeforces.com/contest/1957/problem/C)  
DP
根据题意发现每一步能消除一个行列（对角线）和两个行列（非对角线）。对于dp[n],避免重复只考虑外层新增的行列。若在（1，1），则有dp[n-1]种情况，对于其余(n-1)位置,由于棋子颜色差别算不同，有dp[n-2]\*(2*n-2)种情况。  
O o o o o o                
o x x x x x    
o x x x x x   
o x x x x x   
o x x x x x   
o x x x x x   

# 5-17
- [XOUR-cf1400](https://codeforces.com/contest/1971/problem/G)  
要求两数XOR小于4可以交换，即除后两位其它位都相同的数可以互相交换，可以把它们归到一组。  
同组内的元素可以任意交换，使用map<,priority_queue<> >来存储，自动排序。  

- [Game on Tree (Easy)-cf1400](https://codeforces.com/contest/1970/problem/C1)  
模拟一个链表，判断起点距离两端的的距离奇偶性。    

- [Turtle Tenacity: Continual Mods-cf1200](https://codeforces.com/problemset/problem/1933/D)
排序，注意到最小值只有一个，必定可以。最小值大于一个，若不能通过操作将最小值降低到一个>0且小于最小值的数，则取模必定存在0。 

- [Long Multiplication-cf1200](https://codeforces.com/contest/1954/problem/C)  
和一定，差小积大。

- [Bessie's Birthday Cake (Easy Version)-cf1300](https://codeforces.com/contest/1942/problem/C1)
判断相邻点中间是否有一个点,注意尾部首部特判。

比赛
| **Name**                                                   | **solved** | **A** | **B** | **C** | **D** | **E** | **F** | **Rank** | **Rating**       |
| ---------------------------------------------------------- | :--------: | ----- | ----- | ----- | ----- | ----- | ----- | -------- | ---------------- |
| [cf round 945(Div.2)](https://codeforces.com/contest/1973) |     1      | Ο     | Ø     | Ø     | ！    | ！    | ！    | 7468     | 1236 &rarr; 1201 |

爆1了qwq。

# 5-18
- [B - Cat, Fox and the Lonely Array](https://codeforces.com/contest/1973/problem/B)
昨天的B题。可以用一个int b[21]数组存储每一位的信息，对于一个数是log(a)的复杂度。
开始搜索从1开始到最先到达元素最大或值的位置，记录下这个区间b[j] 即 2^j的总数。
用双指针维护区间。区间长度即为最小值。时间复杂度nlog(a)。赛时想到用bool数组bool b[21],就不能有nlog(a)的复杂度。

- [Left and Right Houses-cf1200](https://codeforces.com/contest/1945/problem/C)
注意细节，别漏情况。

- [Anna and the Valentine's Day Gift-cf1400](https://codeforces.com/contest/1931/problem/E)
思维题，操作只对末尾有0的数生效。只要把每个数末尾0的个数的数组排序。所有数的总位数隔项减去末尾零的数组元素对给定数进行比较。

- [Divisible Pairs-cf1300](https://codeforces.com/contest/1931/problem/D)
可以发现满足条件的ai,aj模y都相同，模x的值都为零或者相加和为x。结构体数组按照%y的部分升序排列，对每个%y相同的元素区间进行遍历，使用map<>求值，注意要/2,相同元素要-1。

# 5-19
- [Jumping Through Segments-cf1400](https://codeforces.com/contest/1907/problem/D)
二分
想贪心想了好久qwq。注意边界的讨论分类要严格。

- [Array Game-cf1400](https://codeforces.com/contest/1904/problem/C)
注意到k >= 3时答案均为0。只要讨论k = 1 和 k =2的情况即可。
数据范围较小k = 2时直接暴力来算，加个二分复杂度 $N^2\lg N$。

# 5-20
- [Equalize-cf1200](https://codeforces.com/contest/1928/problem/B)
二分，排序
用lower_bound写二分好方便

比赛
| **Name**                                                   | **solved** | **A** | **B** | **C** | **D** | **E** | **F** | **G** | **Rank** | **Rating**        |
| ---------------------------------------------------------- | :--------: | ----- | ----- | ----- | ----- | ----- | ----- | ----- | -------- | ----------------- |
| [cf round 946(Div.3)](https://codeforces.com/contest/1973) |     2      | Ο     | O     | Ø     | Ø     | Ø     | Ø     | Ø     | 9882     | 1201 &rarr;  1159 |

补D （一个简单构造）
# 5-21
补题round 946 C
用3个map分别统计第1，2，3位不同，再用一个map统计重复的部分，减去3倍重复的。

# 5-22
补题round 946 E,F,G
G：反悔贪心，优先队列维护。
F: 模拟，不用二分会TLE。注意边界是用upper_bound还是lower_bound。
E：DP。感觉比G还难。和一般贪心的反过来，这里每一位存放的是钱数，位置放的是要求的结果。

# 5-23
补题round 945 C
构造
值为1这个特殊的位置可能导致最大构造失败。
晚上摆烂打植物大战僵尸杂交版，打到57波闪退了。

# 5-24
- [CUSTacm 牛客](https://ac.nowcoder.com/acm/contest/83521/C)
补题
DP

- [B3637 最长上升子序列 洛谷 普及-](https://www.luogu.com.cn/problem/B3637)
DP

- [逃脱 牛客](https://ac.nowcoder.com/acm/contest/27/G)
补题
BFS
比裸BFS多判断个火焰区域，如果在火区域边缘刚好到出口时特判可以逃走（因为这个一直WA）

- [Three Activities-cf1200](https://codeforces.com/contest/1914/problem/D)
可以用结构体排序，多记录一维原来的位置。能暴力就别贪了qwq。

# 5-25
比赛
| **Name**                                                             | **solved** | **A** | **B** | **C** | **D** | **E** | **F** | **G** | **H** | **I** | **Rank** |     **Rating**    |
| -------------------------------------------------------------------- | :--------: | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | -------- | ----------------- |
| [cf round 947(Div. 1 + Div. 2)](https://codeforces.com/contest/1975) |     2      | Ο     | O     | Ø     | !     | !     | !     | !     | !     | !     | 7900     | 1159  &rarr; 1141 |  

三连掉
# 5-26
补题round 947 C
比赛
| **Name**                                                   | **solved** | **A** | **B** | **C** | **D** | **E** | **Rank** |     **Rating**    |
| ---------------------------------------------------------- | :--------: | ----- | ----- | ----- | ----- | ----- | -------- | ----------------- |
| [cf round 948(Div.2)](https://codeforces.com/contest/1973) |     2      | Ο     | O     | Ø     |    !  |    !  |   2665   | 1141 &rarr;  1258 |  

打回绿名

# 5-27 到 5-31
Vjudge上刷了一些题目，部分题目  
[Puzzle UVA-227](https://vjudge.net/problem/UVA-227)  
字符串  
题目本身不难  
输入输出格式问题硬控我几个小时qwq(WA了12发)  
[时间复杂度 洛谷-绿](https://www.luogu.com.cn/problem/P3952)  
模拟，栈，字符串
[回文日期 洛谷-黄](https://www.luogu.com.cn/problem/P2010)  
字符串
[拼数 洛谷-黄](https://www.luogu.com.cn/problem/P1012)  
字符串
[打字练习 洛谷-黄](https://www.luogu.com.cn/problem/P5587)  
字符串  

比赛

| **Name**                                                       | **solved** | **A** | **B** | **C** | **D** | **E** | **F** | **Rank** | **Rating**       |
| -------------------------------------------------------------- | :--------: | ----- | ----- | ----- | ----- | ----- | ----- | -------- | ---------------- |
| [cf Edu round 166(Div.2)](https://codeforces.com/contest/1976) |     2      | Ο     | O     |  Ø    | ！    | ！    | ！    | 5510     | 1258 &rarr; 1285 |

| **Name**                                                   | **solved** | **A** | **B** | **C** | **D** | **E** | **F** | **Rank** | **Rating**       |
| ---------------------------------------------------------- | :--------: | ----- | ----- | ----- | ----- | ----- | ----- | -------- | ---------------- |
| [cf round 949(Div.2)](https://codeforces.com/contest/1981) |     1      | Ο     |   Ø     | !     | ！    | ！    | ！    | 7144     | 1285 &rarr; 1227 |