<!--
  <<< Author notes: Step 4 >>>
  Start this step by acknowledging the previous step.
  Define terms and link to docs.github.com.
-->

## Step 4: 添加分支保护规则

_太棒了! 你已经成功上传了测试报告! :partying_face:_

现在看看拉取请求的合并区域，你会发现：即使没有经过代码审查（review），这个分支仍然可以被合并。

为了避免这种情况，我们可以启用“分支保护”（Protected Branches）。
分支保护能防止协作者直接对关键分支进行不可逆的修改，还可以开启一系列额外的限制，比如：

* 必须通过状态检查（Status Checks）才能合并
* 必须经过代码审查（Review）
* 禁止强制推送（Force Push）等

通过这些设置，可以更好地保护 `main` 分支的稳定性和代码质量。

### :keyboard: 实操环节: 添加分支保护

1. 打开仓库的 **Branches（分支）** 设置页面。你可以在仓库顶部最右侧点击 **Settings（设置）** 标签，然后在左侧菜单中点击 **Branches**。
2. 在 “Branch protection rules” 区域下，点击 **Add classic branch protection rule（添加经典分支保护规则）**。
3. 在 **Branch name pattern（分支名称模式）** 中输入 `main`。
4. 勾选 **Require a pull request before merging（合并前需要拉取请求）**。
5. 取消勾选 **Require approvals（需要审批）**。
6. 勾选 **Require status checks to pass before merging（合并前必须通过状态检查）**。
7. 在出现的灰色区域中，勾选所有你希望强制通过的构建与测试任务。
8. 点击 **Create（创建）** 保存规则。
9. 一旦启用了分支保护，GitHub Actions 将不能再直接向 `main` 分支推送代码。等待大约 20 秒后，切换到 `ci` 分支。[GitHub Actions](https://docs.github.com/actions) 会自动检测到更改，并在 `ci` 分支中进入下一步。