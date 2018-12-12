# Mac下 React-Native 开发环境配置

## 优先安装 node.js
安装完毕后建议配置
```javascript
    npm config set registry https://registry.npm.taobao.org --global
    npm config set disturl https://npm.taobao.org/dist --global
```
> node -v
> npm -v

## 安装 Home-brew [时间超级漫长]
> /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
> brew -v

## 安装 watchman
> brew install watchman
> watchman -v

## 安装 flow [可选]
> brew install flow
> watchman -v

## 安装 react native cli
> npm install react-native-cli  -g

## 基本流程
//有问题，不建议试用最新版    
react-native init app    

//推荐试用 
react-native init app --version 0.55.0
cd app

//指定模拟器版本
react-native run-ios --simulator "iPhone 7"


