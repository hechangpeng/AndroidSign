---
title: Android生成签名文件与对文件进行签名
date: 2017-10-31 10:38:02
tags:
categories: Android
---
<img src="http://owiq5fnuk.bkt.clouddn.com/7.jpg"/>

创建签名文件：
<!-- more -->
keytool  -genkey  -alias  keystoreAliasName  -keyalg  RSA  -validity  20000  -keystore  keystoreFileName.keystore


对jar或apk签名：
jarsigner  -verbose  -keystore  keystoreFilePath  -digestalg  SHA1  -sigalg  MD5withRSA  -signedjar  demo_signed.apk  demo.apk  keystoreAliasName


查看签名信息：
将签名后的jar或apk解压出来，得到METAINFO下面的xxx.RSA文件
keytool -printcert -file xxx.RSA
