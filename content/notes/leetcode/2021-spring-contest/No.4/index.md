---
title: 2021 leetcode 春季赛
menu:
 notes:
  name: 第四题
  identifier: 2021-spring-leetcode-contest-4
  parent: 2021 leetcode 春季赛
  weight: 40
---

{{< note title="第四题" >}}
```go
type Pair struct {
 a, b, index int
}

type PriorityQueue []*Pair

func (pq PriorityQueue) Len() int { return len(pq) }

func (pq PriorityQueue) Less(i, j int) bool {
 return pq[i].a < pq[j].a
}

func (pq PriorityQueue) Swap(i, j int) {
 pq[i], pq[j] = pq[j], pq[i]
 pq[i].index = i
 pq[j].index = j
}

func (pq *PriorityQueue) Push(x interface{}) {
 n := len(*pq)
 item := x.(*Pair)
 item.index = n
 *pq = append(*pq, item)
}

func (pq *PriorityQueue) Pop() interface{} {
 old := *pq
 n := len(old)
 item := old[n-1]
 old[n-1] = nil
 item.index = -1
 *pq = old[0 : n-1]
 return item
}

func processTasks(tasks [][]int) int {
 var vt []int

 n := len(tasks)
 ts := make(map[int]bool)
 for i := 0; i < n; i++ {
  ts[tasks[i][0]] = true
  ts[tasks[i][1] + 1] = true
 }
 m := len(ts)
 for key := range ts {
  vt = append(vt, key)
 }
 sort.Ints(vt)
 mp := make(map[int]int)
 for i := 0; i < m; i++ {
  mp[vt[i]] = i
 }

 starts := make([][]int, m)
 for i := 0; i < n; i++ {
  starts[mp[tasks[i][0]]] = append(starts[mp[tasks[i][0]]], i)
 }

 ans := 0
 extra := 0
 pq := make(PriorityQueue, 0)
 heap.Init(&pq)

 for i := 0; i < m - 1; i++ {
  for len(pq) > 0 {
   if tasks[pq[0].b][1] < vt[i] {
    heap.Pop(&pq)
   } else {
    break
   }
  }

  for _, u := range starts[i] {
   heap.Push(&pq, &Pair{a: extra + tasks[u][1] - vt[i] + 1 - tasks[u][2], b: u})
  }

  currentSeg := vt[i + 1] - vt[i]
  if len(pq) > 0 {
   minSlots := pq[0].a - extra
   slotsToDel := currentSeg
   if minSlots < currentSeg {
    delta := currentSeg - minSlots
    ans += delta
    slotsToDel -= delta
   }
   extra += slotsToDel
  }
 }

 return ans
}

//作者：lucifer1004
//链接：https://leetcode-cn.com/problems/t3fKg1/solution/you-xian-dui-lie-tan-xin-rust-by-lucifer-4spv/
```
{{< /note >}}