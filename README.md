# 介绍

东南大学讲座预约半自动脚本，适用于图片验证码方式。

## 接口账户配置

1. 访问 [超级鹰](http://www.chaojiying.com/)，注册账号并充值1元。
2. 进入个人中心 > 软件ID，申请一个软件ID。
3. 将用户名、密码、软件ID分别复制到 `main.py` 中：

   ```python
   verify_code_params = {
       'user': '<your username>',
       'pass': '<your password>',
       'softid': '<your softid>',
       ...
   }
   ```

## 脚本使用

1. 浏览器访问 [东南大学讲座系统](http://ehall.seu.edu.cn/gsapp/sys/yddjzxxtjappseu/*default/index.do#/hdyy)。
2. 在网页中右键或按 F12 进入控制台，复制请求头中的 `cookie` 到 `main.py` 中，参考[这篇文章](https://blog.csdn.net/boheliang99/article/details/122348239)。

   ```python
   lecture_headers = {
       'Cookie': '<your cookie>',
       ...
   }
   ```

3. 寻找需要预约的讲座名称，将其标题中的部分以列表形式存储到 `main.py` 中：

   ```python
   lecture_keys = ["lecture1", "lecture2"]
   ```

4. 在讲座预约时间开始前10分钟内，运行 `main.py`，成功后控制台会输出相关信息。

5. 本脚本会对多个讲座同时执行预约操作，总共尝试3次。

## 鸣谢

本脚本基于 [seu-lecture-reserve](https://github.com/404874351/seu-lecture-reserve) 进行修改。
