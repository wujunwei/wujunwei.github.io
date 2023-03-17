---
title: 2021 leetcode 春季赛
menu:
 notes:
  name: 第五题
  identifier: 2021-spring-leetcode-contest-5
  parent: 2021 leetcode 春季赛
  weight: 50
---
{{< note title="第五题" >}}
```go
var dir4 = []struct{ x, y int }{{-1, 0}, {1, 0}, {0, -1}, {0, 1}}

func escapeMaze(g [][]string) bool {
	k, n, m := len(g), len(g[0]), len(g[0][0])
	vis := make([][][][6]bool, k)
	for i := range vis {
		vis[i] = make([][][6]bool, n)
		for j := range vis[i] {
			vis[i][j] = make([][6]bool, m)
		}
	}
	// s 的最低位：是否使用了临时消除术
	// s 的其余位：0-未使用永久消除术，1-当前正位于永久消除的位置，2-已使用永久消除术
	var f func(t, x, y, s int) bool
	f = func(t, x, y, s int) bool {
		if x < 0 || x >= n || y < 0 || y >= m || t+n-1-x+m-1-y >= k || vis[t][x][y][s] {
			return false
		}
		if x == n-1 && y == m-1 {
			return true
		}
		vis[t][x][y][s] = true
		if s>>1 == 1 {
			for _, d := range dir4 {
				if f(t+1, x+d.x, y+d.y, s^6) { // 跳出永久消除的位置
					return true
				}
			}
			return f(t+1, x, y, s)
		}
		if s>>1 == 0 && g[t][x][y] == '#' && f(t, x, y, s|2) { // 尝试使用永久消除术
			return true
		}
		// 使用永久消除术已无法走到终点，遇到障碍只能使用临时消除术
		if g[t][x][y] == '#' {
			if s&1 == 1 {
				return false
			}
			s |= 1
		}
		for _, d := range dir4 {
			if f(t+1, x+d.x, y+d.y, s) {
				return true
			}
		}
		return f(t+1, x, y, s)
	}
	return f(0, 0, 0, 0)
}

//作者：endlesscheng
//链接：https://leetcode-cn.com/problems/Db3wC1/solution/dfs-48ms-by-endlesscheng-ckzn/
```
{{< /note >}}