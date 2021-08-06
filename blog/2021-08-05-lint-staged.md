---
slug: lintStaged
title: Lint-Staged  
author: Andrew Chan
author_title: Analyst Programmer @ ASL
author_url: https://github.com/chanandrew96
author_image_url: https://avatars.githubusercontent.com/u/12830221?s=400&v=4
tags: [linter, lint-staged]
---

## [Lint-Staged](https://github.com/okonet/lint-staged)  
### 安裝及配置Lint-Staged  
使用指令 ` npm install lint-staged --save ` 安裝Lint-Staged到專案  
安裝完成後，在 ` package.json ` 中加上 ` lint-staged `或新增副檔名為(.json / .yaml / .yml)的 ` .lintstagedrc ` 檔案 (v3.1 或之後版本支持)  
這裡我們只針對副檔名為 ` .js ` 的檔案作檢查  
```
"scripts": {
    ...
    "lint:staged": "lint-staged",
    ...
},
"lint-staged": {
    "*.js": "eslint --fix"
},
```  
在Husky中的 ` pre-commit ` 修改成以下來使用Lint-Staged  
```
. "$(dirname "$0")/_/husky.sh"
npx lint-staged
```
更詳細的配置可到[官方GitHub](https://github.com/okonet/lint-staged#configuration)上查看  
