# https://github.com/FKPYW/mimotion

# 小米运动自动刷步数

> 小米运动自动刷步数

## Github Actions 部署指南

### 一、Fork 此仓库

### 二、设置账号密码

添加名为  **XMYD_USER**、**XMYD_PASSWD**、**XMYD_STEP**、**TG_BOT_TOKEN**、**TG_USER_ID** 的变量，值分别为 、 **账号（仅支持手机号）**、**密码**、**步数（0则为1w-2w之间随机 或自定义随机范围[18000-25000]）**

推送为TG推送

> SettingsSecrets-->New secret

### 三、多账户(用不上请忽略)

多账户请用 **#** 分割 -->


########################################


> 小米运动 微信步数 支付宝步数

#### VPS部署
```bash
wget --no-check-certificate -O mimotion.sh https://github.com/mixool/mimotion/raw/main/mimotion.sh
chmod 755 mimotion.sh
bash mimotion.sh 18812345678@password@10000-20000 19912345678@password@2000-3000
```

#### Docker部署
```bash
wget --no-check-certificate -O docker-compose.yml https://github.com/mixool/jdmode/blob/main/mimotion.yml
修改 par_mimotion 参数
docker-compose up -d
docker exec -it mimotion /bin/sh
crontab -l
```

| 参数 | 说明 |
| -------- | ----- |
| `18812345678@password@10000-20000` | 账号@密码@随机步数起止点,可多次传入支持多账号 |
| `deviceId@*************` | 设备ID,无则使用随机ID |
| `token@*** chat_id@***` | telegram bot通知所需参数,无则不进行信息通知 |
| `ding_token@*** ding_secret@***` | 钉钉机器人通知所需参数,无则不进行信息通知 |
| `others` | 其它说明查看脚本内容 |

* 因各种原因,不提供任何定时运行脚本,推荐在本地运行

* 小米运动app步数不会更新,仅更新关联应用

* 微信排行榜开关:微信-设置-通用-辅助功能-微信运动-隐私及提醒设置

* 支付宝排行榜开关:支付宝运动-...-设置

#### thanks:
* jd_docker
* [mimotion](https://github.com/Squaregentleman/mimotion)
