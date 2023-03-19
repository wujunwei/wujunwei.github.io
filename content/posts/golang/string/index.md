---
title: golang-string
date: 2021-04-05
hero: go.png
menu:
 sidebar:
  name: string 解析
  parent: go
  identifier: go-string
  weight: 1
---

## 关于go strings 包的方法改动记录

Go语言中的strings包提供了一系列处理字符串的函数。

## 废弃的方法

在Go 1.17版本中，为了提高代码质量和减少维护成本，strings包废弃了一些方法，这些方法被标记为不推荐使用，建议使用替代方法。下表列出了废弃的方法及其替代方法：

| 废弃的方法                 | 替代方法                  |
|-----------------------|-----------------------|
| strings.FieldsFunc()  | strings.Split()       |
| strings.SplitAfterN() | strings.SplitN()      |
| strings.Count()       | strings.Count()       |
| strings.IndexRune()   | strings.Index()       |
| strings.Replace()     | strings.ReplaceAll()  |
| strings.Map()         | strings.ToLower()等    |
| strings.Title()       | case.Title().String() |

## Go 1.20对该包的改动

在Go 1.20版本中，strings包新增了一个方法`strings.TrimSuffix()`，该方法用于去除字符串末尾的指定后缀。例如：

```
str := "hello world.txt"
suffix := ".txt"
res := strings.TrimSuffix(str, suffix)
fmt.Println(res) // 输出：hello world

```

除此之外，Go 1.20还优化了`strings.ReplaceAll()`方法的实现，提高了其性能和稳定性。

## 总结

本文介绍了Go strings包的使用方法，包括废弃的方法及其替代方法，以及Go 1.20对该包的改动。在使用该包时，应注意避免使用废弃的方法，同时关注新版本的改动，以便及时更新代码，提高程序的稳定性和性能。