# pcswitch

#### Introduction

- pcswitch call system, free to use forever, supports ASR (speech recognition), TTS (speech synthesis), custom voice robot, webRTC, IVR, incoming queue, visual management of incoming process, customizable fields for customer information, etc.
- Official website: [https://www.pcswitch.cn](https://www.pcswitch.cn)
- Trial website: [https://demo.pcswitch.cn](https://demo.pcswitch.cn)

#### Software architecture

- Front-end: using vue+elementUI
- Back-end: developed in golang language
- Bottom layer: using freeswitch for secondary development

### System functions
1. Support ASR (speech recognition), TTS (speech synthesis), customizable voice robot
2. Support multiple client types, including: webRTC, sip client
3. Support static seats and dynamic seats
4. Supports multi-tenant mode, the free version only opens 1 organization
5. Supports IVR, incoming call queue, time judgment, etc.
6. Incoming call rules are configured visually, easy to operate
7. Support custom customer information, allowing for the addition, reduction, and modification of fields at will

#### Installation tutorial
1. The installation package download address is: https://pan.baidu.com/s/1ZvH6sjthjIcqa2Ygx76N8A?pwd=6t59
2. It is recommended to use the centos7.9 operating system for installation
3. Download the pcswitch installation package
4. Unzip pcswitch, for example, unzip to: /opt directory
5. Run the following command to install:
./pcs_cli install
6. After successful installation, start the system service
./pcs_cli start
7. Stop all services
./pcs_cli stop
8. View the help command
./pcs_cli -h
9. Certificate replacement method

```
1) Replace the web certificate
The certificate storage path is: config/web/cert
You can replace server.key and server.cert with new certificates, please keep the file name unchanged!
Note: If you change the certificate file name, you need to change the certificate name in the config/web/nginx.conf file together
Restart the web service
#./pcs_cli restart web
Check whether the certificate is effective

2) Replace the core certificate
The certificate storage path is: data/core/certs
Delete dtls-strp.pem and wss.pem
Merge the certificate key and crt into: wss.pem, and then store it in the data/core/certs directory, as follows:
#cat server.key server.crt > wss.pem
Restart the service
#./pcs_cli restart core

```
10. Intelligent voice configuration
Currently only Alibaba Cloud Intelligent Voice is connected, and Alibaba Cloud "Intelligent Voice Interaction" service needs to be activated
1) AccessKey ID, AccessKey Secret creation method
[Create AccessKey Alibaba Cloud Document](https://help.aliyun.com/zh/ram/user-guide/create-an-accesskey-pair?spm=a2c4g.11186623.help-menu-28625.d_2_6_0.72f52c6aBsQZDH)
2) How to obtain Appkey, first create a project, then obtain it on the project management page
[Alibaba Cloud Document](https://help.aliyun.com/zh/isi/getting-started/manage-projects?spm=a2c4g.11186623.help-menu-30413.d_1_1.54f220d0aZccXv)
3) After creation, you can call it in the "Incoming Process" and voice file

#### Instructions

1. This version is a free version. After installation, the system has been initialized and configured, including 3 extensions, etc.
2. The system uses a private certificate by default, which can be replaced by a formal certificate
3. The system does not configure a gateway by default, and users need to configure the gateway by themselves
4. Default account/password: admin/a2f55ef976bcf8b0ae

#### System display
1. Login interface
![Enter image description](images/20250411153349.png)
2. WebRTC registration
![Enter image description](images/20250411153431.png)
3. Backend management
![Enter image description](images/20250516132532.png)
4. Visual configuration of incoming call rules
![Enter image description](images/20250516132751.png)
5. ASR, TTS process
![Enter image description](images/asrtts.png)

#### Problem feedback

- WeChat: ![Enter image description](images/wx.png)
- Email address: kf@pcswitch.cn
