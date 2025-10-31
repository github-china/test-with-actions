<!--
  <<< Author notes: Step 2 >>>
  Start this step by acknowledging the previous step.
  Define terms and link to docs.github.com.
-->

## Step 2: 修复测试问题

_做得好！你已经成功添加了模板工作流! :tada:*_

把这个文件添加到分支中后，GitHub Actions 就会自动在你的仓库上运行持续集成（CI）流程。

当 GitHub Actions 开始执行工作流时，你会在拉取请求的合并区域看到类似下图的检查进度：

<img alt="checks in progress in a merge box" src=https://user-images.githubusercontent.com/16547949/66080348-ecc5f580-e533-11e9-909e-c213b08790eb.png width=400 />

你可以通过进入 **Actions** 标签页，或者点击合并区域中的 **Details（详细信息）**，来查看 GitHub Actions 的执行情况。

测试完成后，你会看到一个红色叉号 :x:（代表失败）或 :heavy_check_mark:（代表通过）。这时，你可以打开构建日志，查看每个步骤的执行结果。

*能从日志中看出是哪个测试没通过吗？*
进入一个失败的构建，向下滚动日志，找到列出所有单元测试的部分。带有 “x” 的那一项就是出错的测试。

<img alt="screenshot of a sample build log with the names of the tests blurred out" src=https://user-images.githubusercontent.com/16547949/65922013-e740a200-e3b1-11e9-8151-faf52c30201e.png width=400 />

如果没有出现检查结果，或者检查卡在“运行中”状态，可以尝试以下方法让它重新触发：

* 刷新页面，有时工作流已运行完，但页面尚未更新。
* 在当前分支上再提交一次，因为工作流是通过 `push` 事件触发的。
* 打开 GitHub 上的工作流文件，确认没有红色波浪线提示语法错误。

### :keyboard: 实操环节：修复测试问题

1. 修改 `ci` 分支中的内容，为了让测试能够通过。你需要查看日志来找出失败的原因。
2. **提交更改（Commit changes）**。
3. 等待大约 20 秒，然后刷新此页面（当前教程页面）。[GitHub Actions](https://docs.github.com/actions) 会自动检测并跳转到下一步。