## 项目名称

Sauce Demo 手工测试练习

## 测试人员

Tao_Tao_

## 测试日期

2026.9.21

## 浏览器

Microsoft Edge

## 操作系统

Windows

## 测试范围

1. 用户登录
2. 商品浏览
3. 商品详情
4. 添加商品到购物车
5. 修改购物车
6. 提交订单
7. 用户登出

## 暂不测试

1. 后端接口
2. 数据库
3. 性能
4. 安全性
5. 自动化脚本

## 测试角色

普通用户

## 测试目标

确认用户能否正常登录、浏览商品、将商品加入购物车并完成结算和登出。

## 测试账号

- `standard_user`：正常用户主流程
- `locked_out_user`：锁定账号登录
- `problem_user`：异常行为探索
- `performance_glitch_user`：响应时间和页面行为探索
- `error_user`：错误行为探索
- `visual_user`：商品图片和页面显示探索

所有账号使用密码：`secret_sauce`。特殊账号不能直接视为缺陷，必须实际观察、复现并保存证据。

## 测试入口

https://www.saucedemo.com/
