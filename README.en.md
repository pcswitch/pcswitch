# pcswitch

#### Introduction

- pcswitch call system, free to use forever, supports webRTC, IVR, incoming queue, visual configuration of incoming rules, customizable fields for customer information, etc.
- Official website: [https://www.pcswitch.cn](https://www.pcswitch.cn)
- Trial website: [https://demo.pcswitch.cn](https://demo.pcswitch.cn)

#### Software architecture

- Front-end: using vue+elementUI
- Back-end: developed in golang language
- Bottom layer: using freeswitch for secondary development

### System functions
1. Support multiple client types, including: webRTC, sip client
2. Support static seats and dynamic seats
3. Support multi-tenant mode, the free version only opens 1 organization
4. Support IVR, incoming queue, time judgment, etc.
5. Incoming rules are configured visually, easy to operate
6. Customizable fields for customer information

#### Installation tutorial
1. The download address of the installation package is: https://pan.baidu.com/s/1ZvH6sjthjIcqa2Ygx76N8A?pwd=6t59
2. It is recommended to use the centos7.9 operating system for installation
3. Download the pcswitch installation package
4. Unzip pcswitch, for example, unzip it to: /opt directory
5. Run the following command to install:
./pcs_cli install
6. After successful installation, start the system service
./pcs_cli start
7. Stop all services
./pcs_cli stop
8. View the help command
./pcs_cli -h
9. Certificate replacement method

- 1) Replace the web certificate
- The certificate storage path is: config/web/cert
- You can replace server.key and server.cert with new certificates, please keep the file name unchanged!
- Note: If you change the certificate file name, you need to change the certificate name in the config/web/nginx.conf file as well
- Restart the web service
- ./pcs_cli restart web
- Check if the certificate is effective
-
- 2) Replace the core certificate
- The certificate storage path is: data/core/certs
- Delete dtls-strp.pem and wss.pem
- Combine the certificate key and crt into: wss.pem, and then store it in the data/core/certs directory, as follows:
#cat server.key server.crt > wss.pem
- Restart the service
- ./pcs_cli restart core

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
![Enter image description](images/20250411153513.png)
4. Visual configuration of incoming call rules
![Enter image description](images/20250411153535.png)

#### Problem feedback
Email address: kf@pcswitch.cn