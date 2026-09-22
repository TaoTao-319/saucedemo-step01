# BUG-001 商品详情信息与商品不对应

## 缺陷标题

使用 `visual_user` 时商品显示信息与对应商品不一致。

## 关联测试用例

TC-006

## 前置条件

使用 Windows + Microsoft Edge 打开 Sauce Demo，使用 `visual_user / secret_sauce` 登录。

## 复现步骤

1. 登录 Sauce Demo。
2. 查看商品列表或打开商品详情。
3. 对比商品名称、图片和价格。

## 预期结果

商品名称、图片、价格和详情应属于同一商品，并保持一致。

## 实际结果

成功登录，但商品详情信息不对应。

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

`BUG-001.png`
