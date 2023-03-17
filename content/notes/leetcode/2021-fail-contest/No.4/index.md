---
title: 2021 leetcode 秋季赛
menu:
 notes:
  name: 第四题
  identifier: 2021-fail-contest-4
  parent: 2021 leetcode 秋季赛
  weight: 40
---

{{< note title="第四题" >}}
```go
func circleGame(toys [][]int, circles [][]int, r int) int {
	sort.Slice(circles, func(i, j int) bool {
		return circles[i][0] < circles[j][0]
	})
	ans := 0
	for i := 0; i < len(toys); i++ {
		if toys[i][2]>r{
			continue
		}
		l, h := 0, len(circles)
		for l < h {
			m := (l + h) / 2
			if toys[i][0]-toys[i][2] <= circles[m][0]+r {
                h = m
			} else {
                l = m + 1
			}
		}
		for j:= l; j < len(circles); j++ {
			if toys[i][0]-toys[i][2] < circles[j][0]-r {
				break
			}
			if in(toys[i], circles[j], r) {
				ans++
                break
			}
		}
	}
	return ans
}

func in(x, y []int, r int) bool {
	return (x[0]-y[0])*(x[0]-y[0])+(x[1]-y[1])*(x[1]-y[1]) <= (r-x[2])*(r-x[2])
}
```
{{< /note >}}