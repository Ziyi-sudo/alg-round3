# 金句库

**每周出声读三遍。这是唯一需要回看的文件。**

收的是**句式**，不是台词。后面挂什么内容下一题全换——背整句的人一被追问就崩。

---

## 开场

| 中文 | 英文 | 来源 |
|---|---|---|
| 我先通读一遍，会安静一两分钟 | Let me read through this once — I'll be quiet for a minute or two. | 01 |
| 还在读，这题铺垫挺长 | Still reading — there's a lot of setup here. | 01 |

## 复述

| 中文 | 英文 | 来源 |
|---|---|---|
| 为了确认我理解对了 | So, to make sure I understand — … | 01 |
| 题目给了我们一个… | **we're given** a / an … | 01 |
| 按升序排好的 | sorted **in** ascending order | 01 |
| 返回任意一个满足…的下标 | return **any** index i where … | 01 |

## 提问

| 中文 | 英文 | 来源 |
|---|---|---|
| 会有重复值吗，还是严格递增 | Can it contain duplicate **values**, or is it strictly increasing? | 01 |
| 大概多大？我问是因为… | Roughly how large can it be? **I'm asking because** … | 01 |
| 空的或 null 应该返回什么 | What should I return for a null or empty input? | 01 |

## 归约

| 中文 | 英文 | 来源 |
|---|---|---|
| 所以这可以归约成… | So this **reduces to** … | — |
| 比中点就知道目标在哪一半 | Comparing the middle element with the target tells me which half it can be in. | 01 |
| 严格不等号有传递性，所以只查相邻就够 | Strict inequality is **transitive**, so if consecutive pairs increase, every pair does. | — |
| 分母不能为零，否则斜率不存在 | The **denominator** can't be zero, otherwise the slope is **undefined**. | — |

## 不变量与边界

| 中文 | 英文 | 来源 |
|---|---|---|
| 不变量是：答案如果存在，一定在这个区间里 | The **invariant** is: if the target exists, its index is always inside [left, right]. | 01 |
| 循环跑到区间为空才停 | The loop runs **while left <= right**, and exits when the range is empty. | 01 |
| 我要小心的是长度为 1 的情况 | The case I want to be careful about is an input of **length 1**. | 01 |
| 写代码前，先说一个边界 | Before I code — one edge case: … | 01 |

## 复杂度与递球

| 中文 | 英文 | 来源 |
|---|---|---|
| 时间 O(…)，空间 O(…)，不需要额外的数据结构 | Time is O(…), space is O(…) — we don't need **any extra** data structure. | 01 |
| 开始写之前，你觉得这样可以吗 | **Does that sound reasonable before I start coding?** | 01 |

## 写代码时（只说意图）

| 中文 | 英文 | 来源 |
|---|---|---|
| 我这里在处理重复的情况 | I'm handling the **duplicate** case here. | 01 |
| 这只是给空输入的防御 | This is just the guard for the empty input. | 01 |
| 这个分支把左半边扔掉 | This branch **discards the left half**. | 01 |
| 这个边界我待会儿回来补 | Let me come back to this edge case in a second. | 01 |

## 测试

| 中文 | 英文 | 来源 |
|---|---|---|
| 我走几个例子验证一下 | Let me walk through a few cases. | 01 |
| 这就是条件写成 < 会挂的那个 case | This is the case that breaks if the condition is left < right. | 01 |
| 这个自己就能正确返回，防御其实只为 null 存在 | It falls through correctly on its own — the guard is really only needed for null. | 01 |

## 追问

| 中文 | 英文 | 来源 |
|---|---|---|
| 如果要找第一次出现的位置 | If you wanted the **first** occurrence instead, … — that's the **lower-bound** variant. | 01 |
| 这就变成了三维偏序问题 | That would turn it into a **3D dominance** problem. | — |

## 保命句

| 中文 | 英文 | 来源 |
|---|---|---|
| 让我想一下，我想把边界弄对 | Let me think for a second — I want to get the boundary right. | 01 |
| 那个……记录状态的——抱歉，辅助数组 | …the thing that keeps track of — sorry, the auxiliary array. | — |
| 等一下，这个没处理…的情况 | Actually, wait — that doesn't handle the … case. Let me fix that. | 01 |
| 我还没看到最优解，先从暴力开始找冗余 | I'm not seeing the optimal approach yet — let me start with brute force and look for the redundant work. | — |
| 时间快到了，你希望我优化还是多走几个例子 | Given the time, should I optimize, or walk through more test cases? | — |
