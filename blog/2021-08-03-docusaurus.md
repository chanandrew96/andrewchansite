---
slug: Docusaurus
title: Docusaurus  
author: Andrew Chan
author_title: Analyst Programmer @ ASL
author_url: https://github.com/chanandrew96
author_image_url: https://avatars.githubusercontent.com/u/12830221?s=400&v=4
tags: [js, Docusaurus, JavaScript, i18n]
---

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

### 設定Navbar, Footer  
在 ``` docusaurus.config.js ``` 中我們可以更改themeConfig中的設定以更新Navbar及Footer的項目  
```
themeConfig: {
    // Navbar設定
    navbar: {
      title: 'My Site',
      logo: {
        alt: 'My Site Logo',
        src: 'img/logo.svg',
      },
      items: [
        {
          type: 'doc',
          docId: 'intro',
          position: 'left',
          label: 'Tutorial',
        },
        {to: '/blog', label: 'Blog', position: 'left'},
        {
          href: 'https://github.com/facebook/docusaurus',
          label: 'GitHub',
          position: 'right',
        },
      ],
    },

    // Footer設定
    footer: {
      style: 'dark',
      links: [
        {
          title: 'Docs',
          items: [
            {
              label: 'Tutorial',
              to: '/docs/intro',
            },
          ],
        },
        {
          title: 'Community',
          items: [
            {
              label: 'Stack Overflow',
              href: 'https://stackoverflow.com/questions/tagged/docusaurus',
            },
            {
              label: 'Discord',
              href: 'https://discordapp.com/invite/docusaurus',
            },
            {
              label: 'Twitter',
              href: 'https://twitter.com/docusaurus',
            },
          ],
        },
        {
          title: 'More',
          items: [
            {
              label: 'Blog',
              to: '/blog',
            },
            {
              label: 'GitHub',
              href: 'https://github.com/facebook/docusaurus',
            },
          ],
        },
      ],
      copyright: `Copyright © ${new Date().getFullYear()} My Project, Inc. Built with Docusaurus.`,
    },
  },
```

### 設定Sidebar  
由於在不同的設備上可能因解像度不同有不同的顯示，在較小的畫面上Navbar上會出現Sidebar的Button，而Sidebar的項目可在 ``` sidebar.js ``` 中更新  
在sidebar中，我們可以新增多於一個sidebar的object。  
而在預設中，sidebar會使用autogenerate的方式新增項目 ``` tutorialSidebar: [{type: 'autogenerated', dirName: '.'}], ```  
更多的設定可到[官方文件](https://docusaurus.io/docs/sidebar#sidebar-object)查看

### 設定Index Page  
在預設的專案中，首頁放於 ` /src/pages/index.js ` 中  
在 ` index.js ` 中，有部分頁面的字是由 ` docursaurus.config.js ` 中提供的  
```
// 引入docusaurus.config.js
const {siteConfig} = useDocusaurusContext();

// 使用Config中的字元
```  
如有使用i18n，相關字元將另外於 ` code.json ` 中翻譯

### 新增Docs Versioning  
使用以下指令可以新增新Version並更新 ``` versions.json ```  
```
// npm run docusaurus docs:version [version] 
npm run docusaurus docs:version 1.1.0
```

### 設定預設顏色主題
在 ` docusaurus.config.js ` 中，我們可以在 ` themeConfig ` 下新增/更改colorMode  
```
themeConfig: {
    colorMode: {
        // 可選: "light", "dark"
        defaultMode: "dark",
        // 可設為true以不讓用戶更改主題
        disableSwitch: false,
    },
}
```  
更多的設定可參考[官方文件](https://docusaurus.io/docs/api/themes/configuration#color-mode---dark-mode)  

### 禁用"Edit This Page"  
若想要整個專案都禁用，可以在 ` docusaurus.config.js ` 下，設定以下更改  
```
presets: [
    [
      '@docusaurus/preset-classic',
      {
        docs: {
            ...
            // Set editUrl to undefined
            editUrl: undefined,
        },
      },
    ],
  ],
```  
若只想在某部分頁面禁用，可以在每頁的Markdown Frontmatter中加上 ` custom_edit_url: null `   
```
---
custom_edit_url: null
---
```
[Reference](https://knktc.com/2021/05/27/docusaurus-disable-edit-url/)  
[Docusaurus GitHub Reference](https://github.com/facebook/docusaurus/issues/2159)  

### Markdown Frontmatter
[Markdown Frontmatter](https://docusaurus.io/docs/api/plugins/@docusaurus/plugin-content-docs#markdown-frontmatter)可以更改該Docs的設定

### i18n  
如要加上i18n支持，需要在 ``` docusaurus.config.js ``` 中加上i18n  
``` 
module.exports = {
  i18n: {
    defaultLocale: 'en',
    locales: ['en', 'zh-hk'],
  },
};
```
然後在Menu上加上語言選擇  
```
module.exports = {
  themeConfig: {
    navbar: {
      items: [
        {
          type: 'localeDropdown',
          position: 'right',
        },
      ],
    },
  },
};
```
在開始專案時，可以加上語言選擇
``` npm run start -- --locale zh-hk ```

在翻譯頁面時，對應不同的頁面有不同的方式
- 翻譯JavaScript頁面時，可使用[translation APIs](https://www.docusaurus.cn/docs/docusaurus-core#translate)  
```
import Translate, {translate} from '@docusaurus/Translate';
<Translate>Welcome to my website</Translate>
<Translate
    id="homepage.visitMyBlog"
    description="The homepage message to ask the user to visit my blog"
    values={{blog: <Link to="https://docusaurus.io/blog">blog</Link>}}>
    {'You can also visit my {blog}'}
</Translate>
<input
    type="text"
    placeholder={
        translate({
            message: 'Hello',
            description: 'The homepage input placeholder',
        })
    }
/>
```

- 翻譯Json檔案 (包括React/JSX, Layout/navbar/footer, Docs sidebar)  
使用指令新增相關翻譯檔案
``` npm run write-translations -- --locale zh-hk ```  
在以下檔案中可以看到其他Json檔案中的Label  
``` 
// Files
i18n/zh-hk/code.json 
i18n/zh-hk/docusaurus-theme-classic/navbar.json

// Code
{
  "Welcome to my website": {
    "message": "Welcome to my website",
    "description": "The homepage welcome message"
  },
  "Hello": {
    "message": "Hello",
    "description": "The homepage input placeholder"
  }
}
```

- 翻譯Markdown檔案 (.md / .mdx檔案)  
將 ``` docs, blog, pages ``` 分別複製到以下路徑
```
// docs
mkdir -p i18n/fr/docusaurus-plugin-content-docs/current
cp -r docs/** i18n/fr/docusaurus-plugin-content-docs/current

// blogs
mkdir -p i18n/fr/docusaurus-plugin-content-blog
cp -r blog/** i18n/fr/docusaurus-plugin-content-blog

// pages
mkdir -p i18n/fr/docusaurus-plugin-content-pages
cp -r src/pages/**.md i18n/fr/docusaurus-plugin-content-pages
cp -r src/pages/**.mdx i18n/fr/docusaurus-plugin-content-pages
```

