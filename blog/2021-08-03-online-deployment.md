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