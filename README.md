<header>

<!--
  <<< Author notes: Course header >>>
  Include a 1280×640 image, course title in sentence case, and a concise description in emphasis.
  In your repository settings: enable template repository, add your 1280×640 social image, auto delete head branches.
  Add your open source license, GitHub uses MIT license.
-->

# 使用 Actions 进行测试

_创建工作流，让你的项目具备持续集成（CI）能力。_

</header>

<!--
  <<< Author notes: Course start >>>
  Include start button, a note about Actions minutes,
  and tell the learner why they should take the course.
-->

## Welcome

[持续集成（Continuous Integration，简称CI）](https://en.wikipedia.org/wiki/Continuous_integration) 可以帮助你和团队在开发过程中保持良好的代码质量。
它会在每次提交后自动运行构建与测试，并在 GitHub 上反馈结果。这样能让主分支（`main`）的问题更少，开发过程中的反馈也更及时。

* **目标人群**：开发者、DevOps 工程师、GitHub 新用户、学生、团队。
* **学习内容**：了解持续集成的概念、学习如何使用 GitHub Actions 实现 CI、掌握创建运行测试并生成测试报告的工作流。
* **您将完成**：我们将使用 [remark-lint](https://github.com/remarkjs/remark-lint) 来检查 Markdown 文件的格式一致性。
* **先决条件**：建议先完成 [Hello GitHub Actions](https://github.com/github-china/hello-github-actions) 课程。
* **学习时长**：整个课程用时不到两小时。

在这门课程中，你将完成以下任务：

1. 添加一个用于测试的工作流(Workflow)
2. 修复测试中发现的问题
3. 上传测试报告
4. 设置分支保护
5. 合并你的拉取请求（Pull Request）

### 如何开始课程

<!-- For start course, run in JavaScript:
'https://github.com/new?' + new URLSearchParams({
  template_owner: 'skills',
  template_name: 'test-with-actions',
  owner: '@me',
  name: 'skills-test-with-actions',
  description: 'My clone repository',
  visibility: 'public',
}).toString()
-->

[![start-course](https://user-images.githubusercontent.com/1221423/235727646-4a590299-ffe5-480d-8cd5-8194ea184546.svg)](https://github.com/new?template_owner=github-china&template_name=test-with-actions&owner=%40me&name=skills-test-with-actions&description=My+clone+repository&visibility=public)

1. 右键点击上方 **Start course** 按钮，选择在新标签页中打开链接。
2. 在新页面中根据系统提示新建一个仓库。
   - 仓库名称、描述这些字段系统已经帮我们自动填充好了，您可以按需修改。
   - 建议选择公开仓库，因为私有仓库有[GitHub Actions 分钟数限制](https://docs.github.com/en/billing/managing-billing-for-github-actions/about-billing-for-github-actions)。
   - 最后点击 Create repository 按钮
3. 仓库创建完毕后，等待大约 20 秒（等待Action执行），然后刷新页面。注意是刷新您仓库的页面，不是本课程的页面。如果页面没有变化，请继续等待。然后按照 README 中的步骤一步步进行。

<footer>

<!--
  <<< Author notes: Footer >>>
  Add a link to get support, GitHub status page, code of conduct, license link.
-->

---

Get help: [Post in our discussion board](https://github.com/orgs/skills/discussions/categories/test-with-actions) &bull; [Review the GitHub status page](https://www.githubstatus.com/)

&copy; 2023 GitHub &bull; [Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [MIT License](https://gh.io/mit)

</footer>
