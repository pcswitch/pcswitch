# pcswitch

#### 介绍

- pcswitch呼叫系统，永久免费使用，支持ASR(语音识别)、TTS(语音合成)、自定义语音机器人、webRTC、IVR、呼入队列、呼入流程可视化管理、客户资料可自定义字段等等
- 官网：[https://www.pcswitch.cn](https://www.pcswitch.cn)
- 试用网址：[https://demo.pcswitch.cn](https://demo.pcswitch.cn)


#### 软件架构

- 前端：采用vue+elementUI
- 后端：采用golang语言开发
- 底层：采用freeswitch同时进行二次开发


### 系统功能
1. 支持ASR(语音识别)、TTS(语音合成)，可自定义语音机器人
2. 支持多种客户端类型，包括：webRTC、sip客户端
3. 支持静态坐席、动态坐席
4. 支持多租户模式，免费版本只开放了1个组织
5. 支持IVR、呼入队列、时间判断等
6. 呼入规则采用可视化配置，操作方便
7. 支持自定义客户信息，可随意增加、减少、修改字段

#### 安装教程
1. 安装包下载地址为：https://pan.baidu.com/s/1ZvH6sjthjIcqa2Ygx76N8A?pwd=6t59
2. 推荐使用centos7.9操作系统安装
3. 下载pcswitch安装包
4. 将pcswitch解压，比如解压到：/opt目录中
5. 运行如下命令安装：
   ./pcs_cli install
6. 安装成功后，开启系统服务
   ./pcs_cli start
7. 停止所有服务
   ./pcs_cli stop
8. 查看帮助命令
   ./pcs_cli -h
9. 证书替换方法

```
   1）替换web证书
      证书存放路径为：config/web/cert
      可以将server.key、server.cert替换为新的证书，请保持文件名不变! 
      注：如果更改证书文件名，需要将config/web/nginx.conf文件中的证书名一起更换
      重启web服务
      #./pcs_cli restart web
      查看证书是否生效

   2）替换core证书
      证书存放路径为：data/core/certs
      删除dtls-strp.pem、wss.pem
      将证书key和crt合并为：wss.pem，然后存放到data/core/certs目录下，如下：
      #cat server.key server.crt > wss.pem
      重启服务
      #./pcs_cli restart core

```
10. 智能语音配置
    目前只对接了阿里云智能语音，需要开通阿里云“智能语音交互”服务
    1）AccessKey ID、AccessKey Secret创建方法
     [创建AccessKey阿里云文档](https://help.aliyun.com/zh/ram/user-guide/create-an-accesskey-pair?spm=a2c4g.11186623.help-menu-28625.d_2_6_0.72f52c6aBsQZDH)
    2）Appkey获取方法，先创建项目，然后在项目管理页可获取
     [阿里云文档](https://help.aliyun.com/zh/isi/getting-started/manage-projects?spm=a2c4g.11186623.help-menu-30413.d_1_1.54f220d0aZccXv)
    3）创建好后，可在“呼入流程”、语音文件中调用使用

#### 使用说明

1.  此版本为免费版本，安装后系统已进行了初始化配置，包括3个分机等
2.  系统默认使用了私有证书，用户可替换为正式证书
3.  系统默认没有配置网关，用户需要自行配置下网关
4.  默认账号/密码：admin/a2f55ef976bcf8b0ae

#### 系统展示
1. 登录界面
![输入图片说明](images/20250411153349.png)
2. webRTC注册
![输入图片说明](images/20250411153431.png)
3. 后台管理
![输入图片说明](images/20250516132532.png)
4. 呼入规则可视化配置
![输入图片说明](images/20250516132751.png)
5. ASR、TTS流程
![输入图片说明](images/asrtts.png)

#### 问题反馈

- 微信：![输入图片说明](images/wx.png)
- 邮箱地址：kf@pcswitch.cn


