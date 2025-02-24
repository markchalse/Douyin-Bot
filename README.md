# 如何在抖音上找到漂亮小姐姐----抖音机器人

[![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.svg?v=103)](https://github.com/ellerbrock/open-source-badge/) [![MIT Licence](https://badges.frapsoft.com/os/mit/mit.svg?v=103)](https://opensource.org/licenses/mit-license.php)      

最近沉迷于抖音无法自拔，常常花好几个小时在抖音**漂亮小姐姐**身上。

本着**高效、直接**地找到漂亮小姐姐的核心思想，我用 Python + ADB 做了一个 Python 抖音机器人 Douyin-Bot。

<img src="./screenshot/demo.gif" title="Logo"  width="300"> <img src="./screenshot/auto_reply.gif" title="Logo"  width="300">
    
##  特性

- [x] **自动翻页**
- [x] **颜值检测**
- [x] **人脸识别**
- [x] **自动点赞**
- [x] **自动关注**
- [x] 随机防 Ban
- [x] **自动评论**

## 原理

- 打开《抖音短视频》APP，进入主界面
- 获取手机截图，并对截图进行压缩 (Size < 1MB)；
- 请求 [人脸识别 API](http://ai.qq.com/)；
- 解析返回的人脸 Json 信息，对人脸检测切割；
- 当颜值大于门限值 `BEAUTY_THRESHOLD`时，点赞并关注；
- 下一页，返回第一步；

## 使用教程

- Python版本：3.0及以上
- 相关软件工具安装和使用步骤请参考 [wechat_jump_game](https://github.com/wangshub/wechat_jump_game) 和 [Android 操作步骤](https://github.com/wangshub/wechat_jump_game/wiki/Android-%E5%92%8C-iOS-%E6%93%8D%E4%BD%9C%E6%AD%A5%E9%AA%A4)
- 在 [ai.qq.com](https://ai.qq.com) 免费申请 `AppKey` 和 `AppID`
1. 获取源码：`git clone https://github.com/wangshub/Douyin-Bot.git`
2. 进入源码目录： `cd Douyin-Bot`
3. 安装依赖： `pip install -r requirements.txt`
4. 运行程序：`python douyin-bot.py`
5. [自动评论](https://zhuanlan.zhihu.com/p/57242891)(可选)：`python3 douyin-bot.py --reply`

## 注意

- 目前暂时只适配了 一加5(1920x1080 分辨率)，如果手机不是该分辨率，请修改 `config/` 文件夹下面的配置文件；
- `config.json`配置文件参考：
    - `center_point`: 屏幕中心点`(x, y)`，区域范围 `rx, ry`
    - `follow_bottom`: 关注按钮位置`(x, y)`，区域范围 `rx, ry`
    - `star_bottom`: 点赞按钮位置`(x, y)`，区域范围 `rx, ry`
    

## 脸部截取

![](./screenshot/faces.png)

## LICENSE

MIT

欢迎 Star 和 Fork ~

如果你有什么问题请提 Issue，或者关注我的微信公众号留言，我都会一一解答

<p align="center">
<img src="screenshot/qrcode.jpg" title="Logo" width="150">
</>

------------------------------------------------------------------------------------
## 【markchalse版本2023.4.6】

## 【腾讯云人脸识别服务】

[选购](https://cloud.tencent.com/product/facerecognition?fromSource=gwzcw.3561167.3561167.3561167&utm_medium=cpc&utm_id=gwzcw.3561167.3561167.3561167)

可选购 (调用次数，人脸检测与分析，10万次)
<img src="./img/tenxun.png"  title="buy"  width="900">

## 【配置API ID 和 密码】

[腾讯云-访问管理-访问秘钥-API秘钥管理-新建秘钥](https://console.cloud.tencent.com/cam/capi)

<img src="./img/api_key.png" title="apikey" width="600">

## 【写入SecretId 及 SecretKey】

更新douyin-bot.py文件中的SecretId SecretKey

<img src="./img/douyin_botidkey.png" title="apikey" width="400">

## 【安装腾讯云python SDK】

python3

pip3 install tencentcloud-sdk-python-cvm


## 【配置手机屏幕】

手机屏幕不是1920x1080的话，根据程序提示的分辨率，需要再config文件夹下新建文件夹如2400x1080

文件夹内拷贝一个config.json

其中follow_bottom是关注 ，star_bottom是点赞 ， comment_bottom是评论

ps: x 是由左向右的像素，y 是由上向下的像素



## 【联系QQ】

915730705

【end】
------------------------------------------------------------------------------------