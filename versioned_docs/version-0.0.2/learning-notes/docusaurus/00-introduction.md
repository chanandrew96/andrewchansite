---
sidebar_position: 1
id: docusaurusIntro
title: 開始建立Docusaurus
---

[開始建立Docusaurus][t01]

### 建立專案  
建立及使用Docusaurus前先確認已安裝了nodeJs及npm/yarn  
- node.Js version >= 12.13.0
- yarn version >= 1.5  

建立新Docusaurus專案
``` 
// npx @docusaurus/init@latest init [name] [template]
// template: classic / facebook / bootstrap
npx @docusaurus/init@latest init my-website classic 
```
進入專案資料夾，開啟Docusaurus
``` 
npx docusaurus start 
npm start
npm run serve -- --build --port 80 --host 0.0.0.0
```

### 部署  
要部署Docusaurus可用 ``` npm run build ``` 指令構建。檔案會建至 ``` /build ```的目錄下  
要測試構建了出來的版本，可用 ``` npm run serve ``` 指令測試

### Markdown Frontmatter
[Markdown Frontmatter](https://docusaurus.io/docs/api/plugins/@docusaurus/plugin-content-docs#markdown-frontmatter)可以更改該Docs的設定

[t01]: /blog/Docusaurus