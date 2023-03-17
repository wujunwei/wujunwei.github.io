---
title: 2021 leetcode 秋季赛
menu:
 notes:
  name: 第一题~第三题
  identifier: 2021-fail-contest-1~3
  parent: 2021 leetcode 秋季赛
  weight: 10
---

{{< note title="第一题">}}

```golang
func minimumSwitchingTimes(source [][]int, target [][]int) int {
    have := make(map[int]int)
	for i := 0; i < len(source); i++ {
        for j := 0; j < len(source[i]); j++ {
            have[source[i][j]]++
        }
    }
    need:=make(map[int]int)
    for i := 0; i < len(target); i++ {
        for j := 0; j < len(target[i]); j++ {
            need[target[i][j]]++
        }
    }
    ans:=0
    for i, c := range need {
        if have[i] >= c{
            continue
        }
        ans+= c-have[i]
    }
    return ans
}
```
{{< /note >}}

{{< note title="第二题">}}

```go
func maxmiumScore(cards []int, cnt int) int {
	var odd, even []int
	for i := 0; i < len(cards); i++ {
		if cards[i]&1 == 1 {
			odd = append(odd, cards[i])
		} else {
			even = append(even, cards[i])
		}
	}
	sort.Ints(even)
	sort.Ints(odd)
	ans := 0
	if cnt&1 == 1 {
		if len(even) == 0 {
			return 0
		}
		ans += even[len(even)-1]
		even = even[:len(even)-1]
		cnt--
	}

	var i, j = len(even)-1, len(odd)-1
	for cnt > 0 {
		if i < 1 && j >= 1 {
			ans += odd[j] + odd[j-1]
			j -= 2
		} else if i >= 1 && j < 1 {
			ans += even[i] + even[i-1]
			i -= 2
		}else{
			if i<1 && j<1{
				return 0
			}
			if odd[j] + odd[j-1]> even[i] + even[i-1]{
				ans += odd[j] + odd[j-1]
				j -= 2
			}else{
				ans += even[i] + even[i-1]
				i -= 2
			}
		}
		cnt -= 2
	}
	return ans
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
