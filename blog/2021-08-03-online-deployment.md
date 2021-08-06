---
slug: online-deployment
title: Online Deployment
author: Andrew Chan
author_title: Analyst Programmer @ ASL
author_url: https://github.com/chanandrew96
author_image_url: https://avatars.githubusercontent.com/u/12830221?s=400&v=4
tags: [Deployment, Online Deployment, Free]
---

## 開發及部署環境

### 序  
最近在找有什麼網上的開發環境及部署網站，以下歸納及介紹一下各站，同時也作一點筆記  

### 開發  
- [CodePen](https://codepen.io/)  
CodePen相信有不少程式員也有用過/留意過(應該?)  
CodePen感覺及使用上比較偏向UI/UX Design的層面上  
整體上介面、功能都很完善，在其Trending的頁面上也能找到不少大神的作品  

- [CodeSandbox](https://codesandbox.io/)  
近來較常用的是CodeSandbox，對比CodePen來說，CodeSandbox比較可以建設一個完整的Website/Web Application  
其網站也提供/支持不少常見的Framework Template，如Angular, React, Vue, Node HTTP Server，應能滿足不少用戶的開發需求  
同時，在其Sandbox中支持將Sandbox部署到Vercel等網站，不需要將程式另花功夫部署  

- [Replit](https://replit.com/)  
Replit官方聲稱支持多達50種語言以上，在用家的角度上整體也感覺方便舒適  
加上Replit支持開發Backend語言，對比而言能提供更多的開發選項  

### 部署  
在選擇部署的網站時，我大多都會選擇支持GitHub Deploy的，能免去一大堆步驟  
- [Vercel](https://vercel.com/)  
Vercel其實是我在使用CodeSandbox時發現的，以往也沒有用過  
其提供了自動化部署，你可以指定GitHub中的一個分支作為生產環境，當程式碼Push到這個Branch時便會自動部署  
而你Push到其他Branch的時候，Vercel也會部署一個Review的版本，同時會保留以往部署過的版本，方便對比及查看版本更新的改變  

- [Expo](https://docs.expo.dev/)  
React Native官方採用的模擬器  
因比較少開發React Native，所以也沒有太多的評價，日後會再補充  

- [Appetize.io](https://appetize.io/)  
如果想測試手機開發的程式，Appetize.io是個不錯的選擇  
它提供了一個月100分鐘的免費方案，如果想要分享給別人測試應該是足夠的  
[彼得潘的 iOS App Neverland - 利用 appetize.io 分享 iOS App，從網頁就能測試 ~](https://medium.com/%E5%BD%BC%E5%BE%97%E6%BD%98%E7%9A%84-swift-ios-app-%E9%96%8B%E7%99%BC%E5%95%8F%E9%A1%8C%E8%A7%A3%E7%AD%94%E9%9B%86/%E5%88%A9%E7%94%A8-appetize-io-%E5%88%86%E4%BA%AB-ios-app-%E5%BE%9E%E7%B6%B2%E9%A0%81%E5%B0%B1%E8%83%BD%E6%B8%AC%E8%A9%A6-f4517c2af82c)  

