---
slug: reactNative
title: React Native  
author: Andrew Chan
author_title: Analyst Programmer @ ASL
author_url: https://github.com/chanandrew96
author_image_url: https://avatars.githubusercontent.com/u/12830221?s=400&v=4
tags: [react, reactNative]
---

### 依賴及設定  
以下以npm作安裝，如以yarn安裝可到[官方文件](https://reactnative.dev/docs/environment-setup)查看
#### 安裝expo-cli  
使用指令 ` npm install -g expo-cli ` 安裝expo到你的裝置  
#### 建立專案及開啟應用程式  
```
// 建立專案
// expo init [project-name]
expo init AwesomeProject

// 開啟應用程式  
cd [project-name]
npm start 
```  
當程式開啟了，在Console中會顯示一個QR Code可以在手機上進行除錯測試  
如果安裝了模擬器，可以以下指令開啟特定的平台版本進行除錯  
```
// Android
npm run android
// iOS (只能在macOS上運行)  
npm run ios
```

### 編程及除錯  
#### 網頁版除錯  
當開啟了網頁版的除錯時你應該可以看到 ` Open up App.js to start working on your app! `  
如果你看到了以上的訊息就代表可以開始編程了  

#### 開發  
打開 ` App.js ` ，你可以修改App function中去嘗試不同的結果  

### 例子  
以上的步驟及程式部署到了[Expo](https://expo.dev/accounts/chanandrew96/projects/reactNativeTutorial)  
有興趣可以到Expo上查看，也可以到[GitHub](https://github.com/chanandrew96/reactNativeTutorial)中查看源碼  
