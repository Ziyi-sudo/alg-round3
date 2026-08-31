# Alg Round 3

第三轮刷题。算法本身已经过了两轮，这一轮练的是**在压力下把逻辑讲清楚**。

---

## 每天做什么

```
1. 昨天那道，盖住说一遍             30 秒
2. 开 checklist.md，找第一个 [ ]
3. 开录音，讲四点：
   Return → Constraint → Reduction → Edge case
4. 写代码
5. 自己走例子（必跑 n = 1），不靠 run
6. 回来写两行：死因 + 金句，把 [ ] 改成 ✅
7. 金句抄进 phrases.md
8. 关掉
```

一天一到两道。**旧卡片永远不回看**——卡片是写的时候起作用，不是看的时候。

## 每周做什么

只开 `phrases.md`，出声读三遍。5 分钟。别的都不开。

## 本周只盯

> **we're given**（被动语态）

其余错误全部允许。一次只盯一条——说话时能同时监控的错误项只有一个，盯三个等于一个都盯不住。

---

## 三条规则

1. **讲终止条件永远讲不变量**——「区间里一定有答案，区间空了才停」，不讲「什么时候停」
2. **开口前先换名词**——上一题的实义词一个都不许带进来
3. **walkthrough 必跑 n = 1**——这一个 case 抓 bug 的密度最高

## 沉默的规矩

沉默不是问题，**没被标注的沉默**才是。三段合法沉默各有开场句：

| 时机 | 开场句 |
|---|---|
| 读题（~90 秒） | Let me read through this once — I'll be quiet for a minute or two. |
| 中途想（≤20 秒） | Let me think for a second — I want to get the boundary right. |
| 写代码（最长） | 前提是方向已经讲完并被认可 |

完整的 45 分钟执行图：[interview-clock](https://ziyi-sudo.github.io/algorithm-visualizers/)

---

## 文件说明

| 文件 | 什么时候开 | 会不会一直长 |
|---|---|---|
| `checklist.md` | 每天，找下一题 | 只改勾选状态 |
| `phrases.md` | 每周一次，出声读 | **会一直长** |
| `grammar.md` | 只在换「本周只盯」时看一眼 | **会一直长** |
| `problems/*.md` | 写完就不再打开 | 每题一个，写完不动 |

## 进度

- [x] 01 Classical Binary Search
