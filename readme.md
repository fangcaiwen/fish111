## 调试运行

**Android**

```
1. cd gniot
2. npm i
3. react-native run-android

// 如遇不能正常启动，在运行
asasasasjasjhjhsajhajhasjhas

asjashjhasjhsajhasjhsahj
ahjajsjhasjhasjhsa

1.npm start

// 打开android studio，点击运行，启动遇红屏错误

2.adb reverse tcp:8081 tcp:8081

```


**IOS**
// ios开发人员添加

```
1. cd gniot
2. yarn
3. cd node_modules/react-native/third-party/glog-0.3.4
4. ../../scripts/ios-configure-glog.sh
5. File -> Project Settings... -> Build System -> legacy Build System
6. 打开工程 -> Libraies -> RCTWebSocket -> Targets -> RCTWebSocket -> Build Phases -> Link Binary -> libfishhook.a 删除 重新添加 

```

## 打包发布

**Android**
// 生成bundle
react-native bundle --platform android --dev false --entry-file index.js  --bundle-output android/app/src/main/assets/index.android.bundle  --assets-dest android/app/src/main/res/



// 如何设置密钥文件

// 如何生成apk文件

mac:./gradlew assembleRelease

window:gradlew assembleRelease


**iOS**
// ios开发人员添加



## 发布更新：

**Code Push**

  > 发布更新（android）

   code-push release-react gniotAndroid android

  > 详细操作(android)

   code-push release-react gniotAndroid android  --t 1.0.0 --dev false --d Staging --des "1.优化操作流程" --m true

   code-push release-react gniotAndroid android  --t 1.0.0 --dev false --d Production --des "1.优化操作流程" --m true

  > 发布更新（ios）

   code-push release-react gniotIos ios

  > 详细操作(ios)

   code-push release-react gniotIos ios  --t 1.0.0 --dev false --d Staging --des "1.优化操作流程" --m true

   code-push release-react gniotIos ios  --t 1.0.0 --dev false --d Production --des "1.优化操作流程" --m true

  > 查看app列表

   code-push app list

  > 查看android所有历史调试版本

   code-push deployment history gniotAndroid Staging

  > 查看ios所有历史调试版本

   code-push deployment history gniotIos Staging

  > 查看android最近发布的版本

   code-push deployment ls gniotAndroid

  > 查看ios最近发布的版本

   code-push deployment ls gniotIos

  > 增加app（ios）

   code-push app add gniotIos ios react-native

  > 增加app（android）

   code-push app add gniotAndroid android react-native

  > 回滚到上一个版本操作：(限于同一原生版本之间的回退，不能跨版本回退)

   code-push rollback gniotAndroid Production|Staging

  > 回滚到指定版本

   code-push rollback gniotAndroid Staging --targetRelease v3

  > android测试 =>正式

   code-push promote gniotAndroid Staging Production

  > 灰度更新20%

   code-push promote gniotAndroid Staging Production -r 20%

  > 软件稳定后，可以全面发布：

   code-push patch gniotAndroid Production -r 100%


## 其他

 > // 安装code-push命令

  npm install -g code-push-cli

 > 注册

  code-push register

 > 登陆

  code-push login

 > 注销 code-push logout

 > 列出 登陆的token

  code-push access-key ls

 > 删除某个access-key

  code-push access-key rm <accessKey>



// 项目介绍

// 相关贡献者


// 参考文献
