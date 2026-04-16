**Flow2API反代无限次数的Banana Pro**

![c64949ee5b1c1de62368ee9d992f1901.png](./_resources/c64949ee5b1c1de62368ee9d992f1901.png)

它主打的是账号池、负载均衡、代理支持、自动刷新 token，还有一个网页后台，偏向自己部署后统一管理调用的玩法。

![d59e29ff9faf8fe048a0d06f7fb72b96.png](./_resources/d59e29ff9faf8fe048a0d06f7fb72b96.png)

因为打码和ip的问题，最后图片生成失败了，只能是演示安装过程

推荐服务器部署，不要选择国内地区，选择Linux版本Docker上手快

腾讯云新加坡，硅谷，东京地区价格是199元一年，2核4G30M带宽，60GBSSD盘 1.5T月流量，推荐硅谷地区CN2线路↓↓↓，系统选Ubuntu

购买地址：https://curl.qcloud.com/oyWDLkRJ

![72d493eab65af6588b3ed9cb7585b177.png](./_resources/72d493eab65af6588b3ed9cb7585b177.png)

**教程**

1.Ubuntu24系统安装Docker

```
sudo apt update
sudo apt install -y ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg
echo \
"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
$(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
sudo docker run hello-world
```

![df5bef0b9db29a8555c85009815ac8bf.png](./_resources/df5bef0b9db29a8555c85009815ac8bf.png)

2.下载项目

```
git clone https://github.com/TheSmallHanCat/flow2api.git
cd flow2api
```

![3cb4347025eece5c2d39613ae43530f1.png](./_resources/3cb4347025eece5c2d39613ae43530f1.png)

3.Docker 部署项目

```
cd ~/flow2api
sudo docker compose -f docker-compose.headed.yml up -d --build
sudo docker compose -f docker-compose.headed.yml logs -f
```

![05ef9d4536347e3fc32730acfbe66f93.png](./_resources/05ef9d4536347e3fc32730acfbe66f93.png)

4.浏览器访问管理后台: 

http://localhost:8000

用户名: admin
密码: admin

登录后建议立即修改密码

![2df145d9b23ae7417dbef38e6c9932fa.png](./_resources/2df145d9b23ae7417dbef38e6c9932fa.png)

5.去下载项目配套的 Flow2API-Token-Updater 插件

https://github.com/TheSmallHanCat/Flow2API-Token-Updater

![0ed5781169d1dfe9ca418323a9c66a39.png](./_resources/0ed5781169d1dfe9ca418323a9c66a39.png)

6.配置插件

去项目系统设置复制插件接口和token

配置号之后会自动同步https://labs.google/ 的信息到项目

![c8962ba501ce4aa9e1abe04acd37463e.png](./_resources/c8962ba501ce4aa9e1abe04acd37463e.png)

7.项目这边也有同步出现账号信息

![e280e35e6df8b83db9738196fe526ca1.png](./_resources/e280e35e6df8b83db9738196fe526ca1.png)

8.验证码配置

去这个网站配置：https://yescaptcha.com/dashboard.html

![8c1ecf7a9b69a743d37c68650b5e929e.png](./_resources/8c1ecf7a9b69a743d37c68650b5e929e.png)

8.测试Gemini 官方 generateContent（文生图）

模型: gemini-3.1-flash-image

接口：http://57.180.47.138:38000

失败了，风控过不去，一般失败是打码和ip的问题，可以轮流换一个打码应该可以成功

![82d4cd0c7b953f9c42501da57330957a.png](./_resources/82d4cd0c7b953f9c42501da57330957a.png)


