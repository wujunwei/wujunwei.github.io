---
title: 2021 leetcode 春季赛
menu:
 notes:
  name: 第一题~第三题
  identifier: 2021-spring-leetcode-contest-1~3
  parent: 2021 leetcode 春季赛
  weight: 10
---

{{< note title="第一题">}}

```go
func purchasePlans(nums []int, target int) int {
    sort.Ints(nums)
    ans := 0
    i, j := 0, len(nums)-1
    for; i < j; i++ {
        for i<j && nums[i]+nums[j]>target {
            j--
        }
        ans += j - i

    }
    return ans % (1e9 + 7)
}
```
{{< /note >}}

{{< note title="第二题">}}

```go
func min(a, b int) int {
    if a < b {
        return a
    }
    return b
}
func orchestraLayout(num int, xPos int, yPos int) int {
    qx := min(num-xPos-1, xPos)
    qy := min(num-yPos-1, yPos)
    q := min(qx, qy)
    n1 := num*4 - 4
    var start int
    if q == 0 {
        start = 1
    } else {
        start = n1*q - (q-1)*q*4 + 1
    }
    if xPos == q {
        start += yPos - xPos
    } else if yPos == q {
        start += (num-q*2-1)*3 + num - q - 1 - xPos
    } else if num-xPos-1 == q {
        start += (num-q*2-1)*2 + num - q - 1 - yPos
    } else if num-yPos-1 == q {
        start += num - q*2 - 1 + xPos - q
    }
    if start%9 == 0 {
        return 9
    }
    return start % 9
}
```
{{< /note >}}

{{< note title="第三题" >}}
```go
type myHeap struct {
	arr []int
}

func (m *myHeap) Len() int {
	return len(m.arr)
}

func (m *myHeap) Less(i, j int) bool {
	return m.arr[i] > m.arr[j]
}

func (m *myHeap) Swap(i, j int) {
	m.arr[i], m.arr[j] = m.arr[j], m.arr[i]
}

func (m *myHeap) Push(x interface{}) {
	m.arr = append(m.arr, x.(int))
}

func (m *myHeap) Pop() interface{} {
	top := m.arr[len(m.arr)-1]
	m.arr = m.arr[:len(m.arr)-1]
	return top
}
func magicTower(nums []int) int {
	rest := 0
	mh := &myHeap{}
	hp := 1
	limit := 0
	for i := 0; i < len(nums); i++ {
		hp += nums[i]
		if nums[i] < 0 {
			heap.Push(mh, -nums[i])
		}
		if hp <= 0 {
			limit++
			add := heap.Pop(mh).(int)
			hp += add
			rest += add
		}
	}
	if hp <= rest {
		return -1
	}
	return limit
}
```
{{< /note >}}
