# BUG-002 商品详情页图片和价格与商品列表不一致

## 缺陷标题

使用 `visual_user` 查看商品详情时，详情页图片和价格与商品列表不一致。

## 关联测试用例

TC-007

## 前置条件

使用 Windows + Microsoft Edge 打开 Sauce Demo，使用 `visual_user / secret_sauce` 登录。

## 复现步骤

1. 登录 Sauce Demo。
2. 在商品列表选择一个商品。
3. 打开该商品详情页。
4. 对比商品列表页和详情页的图片、名称和价格。

## 预期结果

商品详情页应显示与列表页相同的商品图片、名称和价格。

## 实际结果

详情页面商品图片以及商品价格与首页不对应。

## 严重程度

Medium

## 优先级

High

## 测试环境

- Website: https://www.saucedemo.com/
- Browser: Microsoft Edge
- Operating System: Windows
- Account: visual_user
- Date: 2026.9.21

## 附件

`BUG-002.png`
