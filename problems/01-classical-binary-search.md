# Round 3 · #01 · Classical Binary Search

**死因** 口述时把终止条件说成「left == right 时停」，代码就照着写成了 `while(left < right)`。真正的终止是 `left > right`——`left == right` 时区间还剩一个元素，必须再查一次。**讲错的模型直接变成了写错的代码。**

**这道题的金句** The invariant is: if the target exists, its index is always inside [left, right].

**跟读方法** 看着念三遍 → 只看中文列说一遍 → 全盖住说一遍。

| 时机 | 你要表达的意思 | 英文 |
|---|---|---|
| 0:00 开场 | 我先通读一遍，会安静一两分钟 | Let me read through this once — I'll be quiet for a minute or two. |
| 1:45 复述 | 给一个升序整数数组和目标 T，返回**任意一个** A[i] == T 的下标，找不到返回 −1 | So, to make sure I understand — we're given an integer array **sorted in** ascending order and a target T, and we need to return **any** index i where A[i] == T, or −1 if the target isn't in the array. |
| 2:15 提问① | 数组里会有重复值吗，还是严格递增 | Can the array contain duplicate **values**, or is it strictly increasing? |
| 2:15 提问② | 数组大概多大？如果接近 int 上限，我中点会写成 left+(right−left)/2 防溢出 | Roughly how large can the array be? I'm asking because if the length gets close to the max int value, I'll compute the midpoint as left + (right − left) / 2 to avoid **overflow**. |
| 2:15 提问③ | null 或空数组应该返回什么，也是 −1 吗 | And what should I return for a null or empty array — is −1 right there as well? |
| 3:30 归约 | 因为有序，比一下中点就知道目标只可能在哪一半，所以每步能扔掉一半 | Since the array is sorted, **comparing the middle element with the target tells me which half the target can be in**, so I can discard half the array on every step. That's binary search — O(log n). |
| 4:30 不变量 | 目标如果存在，下标一定在 [left, right] 里；区间空了才停 | The **invariant** is: if the target exists, its index is always inside [left, right]. The loop runs **while left <= right**, and exits when left > right — the range is empty and the target isn't there. |
| 5:30 边界 | 我要小心长度为 1 的数组，[0,0] 这个区间还得查一次，所以是 <= 不是 < | The case I want to be careful about is an array of **length 1** — the range [0, 0] still has to be checked, which is exactly why the condition is left <= right, not left < right. |
| 6:00 复杂度 + 递球 | 时间 O(log n)，空间 O(1)，只要两个边界变量。开始写之前你觉得可以吗 | Time is O(log n), space is O(1) — just two boundary variables, no **any extra** data structure needed. **Does that sound reasonable before I start coding?** |
| 写码时 | 中点这么算是为了防溢出 | I'm computing the midpoint as left + (right − left) / 2 to avoid overflow. |
| 写码时 | 这个分支把左半边扔掉 | This branch **discards the left half**, so left = mid + 1. |
| 写码时 | 这是给 null 输入的防御 | And this is the guard for a null input. |
| 25:00 测试开场 | 我走几个例子验证一下 | Let me walk through a few cases. |
| 例① 正常命中 | 中点是 2，A[2] 是 3，返回 2 | [1,2,3,4,5] with T = 3 — mid is 2, A[2] is 3, so we return 2. |
| 例② 找不到 | left 越过 right，退出，返回 −1 | T = 6 — left ends up past right, so we exit and return −1. |
| 例③ 单元素 **关键** | left 等于 right，循环还得跑一次，返回 0。这就是条件写成 < 会挂的那个 case | [1] with T = 1 — left equals right, so the loop still runs once and we return 0. **This is the case that breaks if the condition is left < right.** |
| 例④ 空数组 | 根本进不去循环，自己就返回 −1，所以开头那个防御其实只为 null 存在 | An empty array never enters the loop, so it returns −1 on its own — the guard at the top is really only needed for null. |
| 33:00 追问 | 如果要找第一次出现的位置 | If you wanted the **first** occurrence instead, I'd keep searching to the left after a match rather than returning immediately — that's the **lower-bound** variant. |
| 卡住时 | 让我想一下，我想把边界弄对 | Let me think for a second — I want to get the boundary right. |
| 发现自己写错时 | 等一下，这个没处理长度为 1 的情况 | Actually, wait — that doesn't handle the length-one case. Let me fix that. |

**这四个说法每题都会用到，先背熟**

| 中文 | 英文 |
|---|---|
| 题目给了我们一个… | **we're given** a / an … |
| 按升序排好的 | sorted **in** ascending order |
| 没有这样的下标 | there's **no such index** |
| 不需要额外的数据结构 | we don't need **any extra** data structure |
| 二分查找（不是 two pointers） | **binary search**, with two boundary pointers |

**代码**

```java
public int binarySearch(int[] array, int target) {
  if (array == null || array.length == 0) return -1;   // 严格说只有 null 需要它
  int left = 0, right = array.length - 1;
  while (left <= right) {                 // 不是 <，left==right 时还剩一个元素要查
    int mid = left + (right - left) / 2;  // 防溢出，正是你问的那个问题
    if (array[mid] == target) return mid;
    else if (array[mid] < target) left = mid + 1;   // discard the left half
    else right = mid - 1;                            // discard the right half
  }
  return -1;
}
```

**下一题只带走三件事**

1. 讲终止条件永远讲**不变量**（区间里一定有答案，区间空了才停），不讲「什么时候停」
2. 开口前先换名词，上一题的实义词一个都不许带进来
3. walkthrough 必跑 **n = 1**，这一个 case 今天本来就能替你抓到两个 bug
