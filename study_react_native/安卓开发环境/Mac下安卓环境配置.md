
环境：
cordova 8.0版 对应安卓的 jdk1.8.x 不要安装高版本，防止有问题

//查看java安装目录
/usr/libexec/java_home -V 

//删除java高版本
cd /Library/Java/JavaVirtualMachines
ls -la
sudo rm -rf jdk-11.0.1.jdk

## 配置环境
> 步骤一 安装jdk1.8
> 步骤二 安装 android studio 并更新 android sdk 
> 步骤三 配置对应环境变量


```javascript
    // 进入用户家目录
    cd ~

    //创建 .bash_profile 用于环境变量的配置脚本
    touch .bash_profile

    //配置java 环境变量 
    export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk1.8.0_181.jdk/Contents/Home;

    //查看 java 环境变量是否配置成功命令
    java -version

    //配置 android_home
    export ANDROID_HOME=/Users/wurong/Library/Android/sdk; 
    export ANDROID_HOME_TOOLS=/Users/wurong/Library/Android/sdk/platform-tools;  
    export PATH=${PATH}:${JAVA_HOME}:${ANDROID_HOME}:${ANDROID_HOME_TOOLS};

    //手动下载 gradle 4.10.2 ,并将 gradle 移动至 /usr/local/gradle/ 目录下
    mv gradle-4.10.2 /usr/local/gradle

    //配置 gradle 环境变量
    export GRADLE_HOME=/usr/local/gradle/gradle-4.10.2
    export PATH=$PATH:$GRADLE_HOME/bin 

    //最后执行 source .bash_profile 脚步，更改环境配置
    source .bash_profile

    //安装 cordova，建议安装 cordova@8.0.0 版本 
    npm install cordova -g

    //然后命令构建项目
    cordova create web-app
    cd web-app
    cordova add android
    cordova build android
```

## 下载并安装 genymotion 模拟器
注意事项：建议试用 微软邮箱，否则会在软件登录时出现 network err 问题
1. 下载并安装 virtualbox [virtualbox 下载地址](https://www.virtualbox.org/wiki/Downloads)
2. 下载并安装 genymotion [genymotion 下载地址](https://www.genymotion.com/download/)









