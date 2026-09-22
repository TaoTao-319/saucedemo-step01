# Sauce Demo 手工测试用例和执行结果

> 本文件是 GitHub 可浏览版本，内容与 `test-cases.xlsx` 和 `test-report.docx` 同步。测试环境：Windows + Microsoft Edge；测试人员：Tao_Tao_；测试日期：2026.9.21。

## 测试账号覆盖关系

| 账号 | 用途 | 对应用例 |
|---|---|---|
| `standard_user` | 正常用户主流程 | TC-001、TC-012～TC-019 |
| `locked_out_user` | 被锁定账号登录 | TC-002 |
| `problem_user` | 异常行为探索 | TC-003、TC-007 |
| `performance_glitch_user` | 登录延迟观察 | TC-004、TC-007 |
| `error_user` | 商品功能探索 | TC-005、TC-007 |
| `visual_user` | 商品图片和详情一致性检查 | TC-006、TC-007 |

所有账号使用密码：`secret_sauce`。特殊账号的异常表现必须以实际观察和截图为依据。

## 执行结果

| 用例编号 | 测试标题 | 测试数据 | 预期结果 | 实际结果 | 测试结果 | 备注或缺陷编号 |
|---|---|---|---|---|---|---|
| TC-001 | 使用 standard_user 正常登录 | `standard_user / secret_sauce` | 登录成功，进入商品列表页并显示 Products | 输入正确用户名和密码后成功跳转，页面无异常 | Pass | |
| TC-002 | 使用 locked_out_user 登录 | `locked_out_user / secret_sauce` | 登录被阻止，并显示账号被锁定提示 | 输入被锁定用户名后无法跳转，提示用户被锁定 | Pass | |
| TC-003 | 使用 problem_user 登录 | `problem_user / secret_sauce` | 账号可以登录并进入商品列表页 | 输入问题用户名后可以跳转 | Pass | |
| TC-004 | 使用 performance_glitch_user 登录 | `performance_glitch_user / secret_sauce` | 登录最终成功，页面可正常使用 | 登录成功，但登录延迟明显 | Pass | 观察到明显延迟 |
| TC-005 | 使用 error_user 登录并浏览商品 | `error_user / secret_sauce` | 可以登录，页面内容应正常展示 | 输入用户名和密码后成功登录 | Pass | |
| TC-006 | 使用 visual_user 检查商品显示 | `visual_user / secret_sauce` | 商品图片、名称、价格和详情应正确对应 | 成功登录，但商品详情信息不对应 | Fail | BUG-001；证据：BUG-001.png |
| TC-007 | 特殊账号登录后打开商品详情 | `visual_user / secret_sauce` | 商品详情可打开，页面信息应与商品列表一致 | 详情页面商品图片以及商品价格与首页不对应 | Fail | BUG-002；证据：BUG-002.png |
| TC-008 | 输入错误用户名和正确密码 | `wrong_user / secret_sauce` | 登录失败，并显示明确错误提示 | 登录失败，提示用户名错误 | Pass | |
| TC-009 | 输入正确用户名和错误密码 | `standard_user / wrong_password` | 登录失败，并显示明确错误提示 | 登录失败，提示密码错误 | Pass | |
| TC-010 | 用户名为空时登录 | 空用户名 / `secret_sauce` | 登录失败，并提示用户名必填 | 登录失败，提示用户名不能为空 | Pass | |
| TC-011 | 密码为空时登录 | `standard_user` / 空密码 | 登录失败，并提示密码必填 | 登录失败，提示密码不能为空 | Pass | |
| TC-012 | 登录后打开商品详情 | `standard_user / secret_sauce` | 显示名称、图片、价格和描述，且信息对应 | 商品名称、图片、价格和描述均无误 | Pass | |
| TC-013 | 添加一个商品到购物车 | 任意商品 | 购物车数量增加，商品出现在购物车中 | 商品成功添加到购物车，数量无误 | Pass | |
| TC-014 | 在购物车删除商品 | 已加入购物车的商品 | 商品被删除，购物车数量同步更新 | 商品成功被删除，购物车数量同步更新 | Pass | |
| TC-015 | 购物车为空时进入结算 | 空购物车 | 系统应阻止无商品结算或给出明确提示 | 系统未阻止无商品结算 | Fail | BUG-003；证据：BUG-003.png |
| TC-016 | 结算时姓为空 | First Name=张三；Last Name=空；Zip=100000 | 系统阻止继续，并提示姓氏必填 | 无法结算，提示姓氏必填 | Pass | |
| TC-017 | 结算时邮政编码为空 | First Name=张三；Last Name=测试；Zip=空 | 系统阻止继续，并提示邮编必填 | 无法结算，提示邮编必填 | Pass | |
| TC-018 | 填写完整信息并提交订单 | 张三 / 测试 / 100000 | 订单提交成功，并显示完成页面 | 成功结算 | Pass | |
| TC-019 | 用户登出 | `standard_user / secret_sauce` | 返回登录页，不能继续访问已登录页面 | 成功登出，且不能访问已登录页面 | Pass | |

## 统计

- 总用例数：19
- Pass：16
- Fail：3
- Blocked：0
- 缺陷：BUG-001、BUG-002、BUG-003
