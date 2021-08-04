---
slug: nativeBase
title: Native Base  
author: Andrew Chan
author_title: Analyst Programmer @ ASL
author_url: https://github.com/chanandrew96
author_image_url: https://avatars.githubusercontent.com/u/12830221?s=400&v=4
tags: [react, reactNative, nativeBase]
---

## 應用UI程式庫 - NativeBase  
以下將在React Native中使用NativeBase的元件庫  

### 安裝依賴  
使用指令 
```
npm install native-base styled-components styled-system 
expo install react-native-svg
expo install react-native-safe-area-context
```  
> :warning:注意：如果你正在運行安裝目的地的ReactNative專案會引致安裝失敗  

安裝完成後你可以用import去使用NativeBase庫  
``` import { ... } from 'native-base'; ```  

### 開始使用  
參考[官方文件](https://docs.nativebase.io/setup-provider)  

要使用NativeBase，你需要import NativeBaseProvider在根元件(App.js)  
NativeBaseProvider令你的應用可以應用NativeBase的主題  
```
import { NativeBaseProvider, Text, Box } from 'native-base';
export default function App() {
  return (
    <NativeBaseProvider>
        // Your code here ...
    </NativeBaseProvider>
  );
}

```

### 部署至你的Expo  
當你完成了你的程式想部署到Expo時，你可以在npm start彈出的網站(Metro Bundler)找到 ` Publish or republish project... ` 的選項  
然後你可以再Console中選擇登入已有的Expo帳戶或新增帳戶  
成功登入後便會開始將你的程式部署到Expo上  
> :warning:注意：如果彈出有任何依賴套件找不到，使用 ` npm install [packagename] ` 來安裝相關依賴  
如果問題在安裝後未能解決，可嘗試重啟程式  

### 在Expo上構建  
如果你想要在Expo上構建Android和iOS的程式，你可以在Console上輸入以下指令，將你的程式碼放入Expo的構建隊列  
```
expo build:android  
expo build:ios  
```  
如果想要查看隊列及查看構建，你可以在Expo上你的專案中查看  
或者你可以到[Expo Turtle Queues](https://expo.dev/turtle-status)查看當前的隊列  
當構建完成後，你可以在 ` Builds ` 的頁面中找到對應平台的紀錄  
點入對應平台的紀錄後，你可以下載構建完的包並安裝到你的模擬器中  

### 例子  
以上的步驟及程式部署到了[Expo](https://expo.dev/accounts/chanandrew96/projects/reactNativeTutorial)  
有興趣可以到Expo上查看，也可以到[GitHub](https://github.com/chanandrew96/reactNativeTutorial)中查看源碼  
