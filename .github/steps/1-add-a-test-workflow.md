<!--
  <<< Author notes: Step 1 >>>
  Choose 3-5 steps for your course.
  The first step is always the hardest, so pick something easy!
  Link to docs.github.com for further explanations.
  Encourage users to open new tabs for steps!
-->

## Step 1: 添加测试工作流

_欢迎来到 "GitHub Actions: 持续集成" 课程! :wave:_

**什么是 _持续集成(CI)_?**: [Continuous integration](https://en.wikipedia.org/wiki/Continuous_integration) 它能帮助你在团队开发中保持良好的代码质量。每次提交（commit）都会触发自动构建和测试，测试结果会反馈到 GitHub 的拉取请求（Pull Request）中。这样既能减少 `main` 分支中的问题，又能让你在开发时获得更快的反馈。

![An illustration with a left half and a right half. On the left: illustration of how GitHub Actions terms are encapsulated. At the highest level: workflows and event triggers. Inside workflows: jobs and definition of the build environment. Inside jobs: steps. Inside steps: a call to an action. On the right: the evaluated sequence: workflow, job, step, action.](https://user-images.githubusercontent.com/6351798/88589835-f5ce0900-d016-11ea-8c8a-0e7d7907c713.png)

- **Workflow（工作流）**：从触发到结束的一整套自动化流程。包括触发条件、运行环境以及触发后执行的任务。
- **Job（任务）**：工作流中的一个阶段，由一个或多个步骤组成。例如，这里我们定义的 `build` 任务就是其中一部分。
- **Step（步骤）**：任务中的一个具体动作，比如运行某个命令或执行一个 Action。
- **Action（动作）**：一个可复用的自动化单元，可以由 GitHub 官方、开源社区，或者你自己编写。

想了解更多，请查看 GitHub 文档：[Workflow syntax for GitHub Actions](https://docs.github.com/actions/using-workflows/workflow-syntax-for-github-actions)。

接下来，我们要在这个仓库中添加一个工作流，用来检测（lint）Markdown 文件的格式一致性。

### :keyboard: 实操环节: 添加测试工作流

1. 打开一个新的浏览器标签页，方便一边操作一边阅读本教程。
2. 进入仓库的 **Actions** tab页。
3. 点击 **New workflow（新建工作流）**。
4. 搜索 “Simple workflow”，并点击 **Configure（配置）**。
5. 将工作流文件命名为 `ci.yml`。
6. 删除模板中最后两个步骤。
7. 在工作流的末尾添加以下步骤：

   ```yml
   - name: Run markdown lint
     run: |
       npm install remark-cli remark-preset-lint-consistent
       npx remark . --use remark-preset-lint-consistent --frail
   ```

   > 即使在 `ci.yml` 中正确缩进后，GitHub Actions 仍可能报错。我们会在下一步修复它。
8. 点击 **Commit changes...（提交更改）**，并选择创建一个名为 `ci` 的新分支。
9. 点击 **Propose changes（提交修改建议）**。
10. 点击 **Create pull request（创建拉取请求）**。
11. 等待大约 20 秒，然后刷新此页面（即当前教程页面）。[GitHub Actions](https://docs.github.com/actions) 会自动检测并跳转到下一步。