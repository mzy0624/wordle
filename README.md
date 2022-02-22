## <center>wordle</center>

可以用 `Makefile` 启动程序，相应的命令为（简单难度）

```makefile
make run
```

或者（困难难度）

```makefile
make run HARD=HARD
```

程序随机从词库中选择一个单词，给出长度 `len`，要求在 `(len - 1) * 2` 次机会内，猜中这个单词。

每次机会你需要输入一个长度为 `len` 的单词（也可以输入不是单词的字符串？要实现判断一个字符串是否为英文单词，要么需要一个很大的词库，查找单词是否在词库中；要么将其看作一个二分类问题，给一个足够大的数据集，包含正例（是单词）和反例（不是单词）。使用机器学习方法训练一个分类器，然后对每个输入用分类器来判断是否为单词，在这里就没实现了）

每次都会将输入的单词和随机选择的单词作比较：

- 若某个字母变成绿色，则说明这个字母猜对了，之后输入单词这个位置都需要是该字母（简单难度没有这个要求）
- 若某个字母变成黄色，则说明单词中有这个字母但位置错了，之后输入单词需要包含这个字母（简单难度没有这个要求）
- 若某个字母变成灰色，则说明单词中没有这个字母，之后仍然可以输入带该字母的单词

不管最后游戏成功还是失败，都会显示正确单词和中文释义。
