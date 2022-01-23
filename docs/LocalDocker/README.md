# 本地部署
::: tip 提示
本教程将默认你会使用Git、Python、Linux等工具~  
🖐️会者不难  
使用Python 版本不低于**3.6**  
::: 

## 1.1 克隆本项目至本地并进入目录  
``` shell
git clone https://github.com/XiaoMiku01/bili-live-heart
cd bili-live-heart
```
## 1.2 安装所需模块  
``` shell
pip install -r requirements.txt
```

## 1.3 配置用户信息  
``` shell
vim user.toml
```
```
[[users]] # 账号1
# B站cookie(不要忘记双引号)
cookie = "buvid3=7E689B52-04B2-427D-A827-9E6767C8010A167611infoc; _uuid=7DA69981-BA5F-8609-1A27-5AAA4E38298004353infoc; blackside_state=1; rpdid=|(JlRlYYlYRR0J'uYJYYRYJuu; DedeUserID=28104254; DedeUserID__ckMd5=1cd100949782830f; bili_jct=eb767c7d2592974589dccc15125848c7; LIVE_BUVID=AUTO1816367242915384; fingerprint3=b7352f289cf60b1cde87f47381451b5b; fingerprint=127f22336f083bead0f1f922d9bc8be1; fingerprint_s=0ca8c2f3e800e4b6f2883fb8eed82db6; video_page_version=v_old_home; b_ut=5; buvid_fp_plain=7E689B52-04B2-427D-A827-9E6767C8010A167611infoc; CURRENT_QUALITY=0; i-wanna-go-back=-1; CURRENT_BLACKGAP=0; Hm_lvt_8a6e55dbd2870f0f5bc9194cddf32a02=1641729656,1641990189,1642068841,1642595708; CURRENT_FNVAL=2000; buvid_fp=127f22336f083bead0f1f922d9bc8be1; buvid4=981D82C6-B682-8664-24D6-68187C41699C72286-022012116-1vkv2uTByYuwFtggvIQlEQ%3D%3D; PVID=1; bp_t_offset_28104254=618602559098738497; innersign=0; b_lsid=10B76E316_17E84B2F10F; bp_video_offset_28104254=618753737654168400; GIFT_BLOCK_COOKIE=GIFT_BLOCK_COOKIE"
# 需要自动打卡主播uid(不是房间号！是UID! 如果为0则只进行签到不赠送小心心 只能填一个)
ruid = 672342685

[[users]] # 账号2
cookie =""
ruid = 0

# 多账号请以相同格式添加

[cron] # Cron 表达式(五位数）
cron = "10 0 * * *"

[serverchan] # Server酱sendkey(微信推送，选填)
sendkey = "SCT115167TIc8bPZH2UijtIzoBM2d8y5V6"
```
::: tip 提示
cron 默认为 0 0 * * * 即每天0点0分运行  
补充：五位数Cron表达式，第一位表示分，第二位表示时，后三位本项目用不到不解释，例如：  
`10 0 * * *` 表示每天0点10分运行  
`30 8 * * *` 表示每天8点30分运行  
`50 20 * * *` 表示每天20点50分运行 
:::

## 1.4 运行脚本文件
``` shell
python3 index.py
```
::: tip 提示
本项目内置定时模块，并且默认在首次运行时执行一次，之后只需程序后台保持运行即可，可以使用screen tmux 等工具保持后台运行  
:::

# Docker

## 随手写的Dockerfile
没从环境拿变量，先填写配置再构建镜像的，反正能跑，开摆！
