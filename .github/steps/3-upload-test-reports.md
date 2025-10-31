<!--
  <<< Author notes: Step 3 >>>
  Start this step by acknowledging the previous step.
  Define terms and link to docs.github.com.
-->

## Step 3: 上传测试报告

_工作流已经运行完成啦! :tada:_

那如果我们想在另一个任务（job）中使用上一个任务的输出结果，该怎么办呢？
可以借助 GitHub Actions 内置的 [artifact 存储功能](https://docs.github.com/actions/advanced-guides/storing-workflow-data-as-artifacts)，把某个任务生成的文件保存下来，供同一个工作流中的其他任务使用。

要上传这些文件（称为“构件”或 artifact），我们可以使用 GitHub 官方提供的 [`actions/upload-artifact`](https://github.com/actions/upload-artifact) 这个 Action。

### :keyboard: 实操环节: 上传测试报告

1. 打开并编辑你的工作流文件。
2. 在 `build` 任务中的 `Run markdown lint` 步骤里，修改命令，使用 `vfile-reporter-json` 把检测结果输出为 `remark-lint-report.json`。
3. 在 `build` 任务中添加一个新步骤，使用 `upload-artifact` 动作，把生成的 `remark-lint-report.json` 文件上传到 artifact 存储中。
4. 修改后的 `build` 任务应如下所示：

   ```yml
   build:
     runs-on: ubuntu-latest
     steps:
       - uses: actions/checkout@v4

       - name: Run markdown lint
         run: |
           npm install remark-cli remark-preset-lint-consistent vfile-reporter-json
           npx remark . --use remark-preset-lint-consistent --report vfile-reporter-json 2> remark-lint-report.json

       - uses: actions/upload-artifact@v4
         with:
           name: remark-lint-report
           path: remark-lint-report.json

5. 提交（Commit）修改到当前分支。
6. 等待大约 20 秒，然后刷新本教程页面。[GitHub Actions](https://docs.github.com/actions) 会自动检测更新并进入下一步。

就像 `upload-artifact` 负责上传文件一样，你也可以使用 [`actions/download-artifact`](https://github.com/actions/download-artifact) 在后续任务中下载这些文件。
不过，为了让课程流程更简洁，这里我们暂时不演示下载步骤。