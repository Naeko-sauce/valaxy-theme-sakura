<h1 align="center">Valaxy Theme Sakura</h1>
<pre align="center">
🧪 正在测试、完善主题示例和主题文档 | <a href="https://sakura.valaxy.site/">文档</a> | <a href="https://sakura.wrxinyue.org/">示例</a> | <a href="./README.en.md">English</a>
</pre>

<p align="center">
<a href="https://www.npmjs.com/package/valaxy-theme-sakura" rel="nofollow"><img src="https://img.shields.io/npm/v/valaxy-theme-sakura?color=0078E7" alt="NPM version"></a>
<a href="https://github.com/WRXinYue/valaxy-theme-sakura/actions/workflows/release.yml"><img src="https://github.com/WRXinYue/valaxy-theme-sakura/actions/workflows/release.yml/badge.svg" alt="Release"></a>
<a href="https://stackblitz.com/edit/stackblitz-starters-tqdtk7?file=README.md"><img src="https://developer.stackblitz.com/img/open_in_stackblitz_small.svg" alt="Open in StackBlitz"></a>
</p>

### 🚀 使用

**安装主题:**

~~~bash
pnpm create valaxy
pnpm add valaxy-theme-sakura
~~~

**启用主题:**

~~~ts
// valaxy.config.ts
import { defineConfig } from 'valaxy'
import type { ThemeUserConfig } from 'valaxy-theme-sakura'

export default defineValaxyConfig<ThemeUserConfig>({
  theme: 'sakura'
})
~~~

**配置示例：**

<details>

```ts
// valaxy.config.ts
import { defineValaxyConfig } from 'valaxy'
import type { ThemeUserConfig } from 'valaxy-theme-sakura'

/**
 * User Config
 */
export default defineValaxyConfig<ThemeUserConfig>({
  // site config see site.config.ts

  theme: 'sakura',

  themeConfig: {
    // colors: {
    //   primary: '#e67474', // 主题色
    // },

    navbarTitle: ['かなしい', 'の', '心悦'],

    favicon: false, // 导航栏图标

    banner: {
      // 壁纸支持图片及视频
      title: 'Hello, sakura',
      motto: 'You got to put the past behind you before you can move on.',
      urls: [
        'https://wrxinyue-images.s3.bitiful.net/wallpaper/Genshin Impact - Yae Miko (4) Cybust PC.mp4',
        'https://wrxinyue-images.s3.bitiful.net/pc-wallpaper/wallhaven-yxwy7k.jpg'
      ],
      // 背景样式选项:
      // - '': 无特效，显示原图
      // - 'filter-dim': 阴影效果
      // - 'filter-grid': 横条效果
      // - 'filter-dot': 点点效果
      style: '',
    },

    articlePinned: [
      {
        title: 'Valaxy Theme Sakura',
        desc: '本站使用的 valaxy sakura 主题',
        img: 'https://wrxinyue-images.s3.bitiful.net/pc-wallpaper/wallhaven-d6mryl.jpg',
        link: 'https://github.com/WRXinYue/valaxy-theme-sakura',
      },
      {
        title: 'Valaxy sakura theme docs',
        desc: '主题文档',
        img: 'https://wrxinyue-images.s3.bitiful.net/pc-wallpaper/wallhaven-gpxyed.jpg',
        link: 'https://sakura.valaxy.site/',
      },
      {
        title: '示例站点',
        desc: 'https://sakura.wrxinyue.org/',
        img: 'https://wrxinyue-images.s3.bitiful.net/pc-wallpaper/wallhaven-jxqgjw.jpg',
        link: 'https://sakura.wrxinyue.org/',
      },
    ],

    pagination: {
      animation: true,
      infiniteScrollOptions: {
        preload: true,
      },
    },

    article: {
      navigationMerge: true,
    },

    // 导航栏
    navbar: [
      {
        text: '🌈 首页',
        link: '/',
      },
      {
        text: '📁 分类',
        link: '/categories',
      },
      {
        text: '🏷️ 标签',
        link: '/tags',
      },
      {
        text: '🔦 时光轴',
        link: '/archives',
      },
      {
        text: '🍻 友情链接',
        link: '/links',
        submenu: [
          {
            text: 'GitHub',
            icon: 'i-ri-github-fill',
            link: 'https://github.com/WRXinYue/valaxy-theme-sakura',
          },
          {
            text: 'Discord',
            icon: 'i-ri-discord-fill',
            link: 'https://discord.gg/sGe4U4p4CK',
          },
          {
            text: 'Valaxy →',
            icon: 'i-ri-cloud-fill',
            link: 'https://github.com/YunYouJun/valaxy',
          },
        ],
      },
      {
        text: 'RSS',
        icon: 'i-ri-rss-fill',
        link: 'https://sakura.wrxinyue.org/atom.xml',
      },
    ],

    sidebar: [
      {
        text: '首页',
        icon: 'i-ri-home-4-line',
        link: '/',
      },
      {
        locale: 'menu.archives',
        icon: 'i-ri-archive-line',
        link: '/archives/',
      },
      {
        locale: 'menu.categories',
        icon: 'i-ri-folder-2-line',
        link: '/categories/',
      },
      {
        locale: 'menu.tags',
        icon: 'i-ri-price-tag-3-line',
        link: '/tags/',
      },
    ],

    // 页脚配置
    footer: {
      since: 2024,

      icon: {
        img: '/favicon-16x16.ico',
        animated: true,
        url: 'https://wrxinyue.org',
        title: 'WRXinYue',
      },
    },
  },
})
```

更多示例请见[Sakura配置示例](https://sakura.valaxy.site/examples/config)

<br></details>

**更新主题：**

~~~bash
pnpm up valaxy-theme-sakura --latest
~~~

### 0.6.0+版本升级注意事项

如果您是从老版本升级过来的，推荐在 `styles` 目录下新建 `index.scss` 文件，然后填入以下内容：

```scss
@use "valaxy-theme-sakura/styles/themes/sakura/index.scss" as *;
```

这样就会启动`sakura`样式，后期会不断新增其他的样式文件，敬请期待

### 📋 计划清单

- [ ] 添加博客echarts可视化数据统计 (预计0.7.0版本发布)
- [ ] 发布博客主题到valaxy (预计0.7.0版本同步)
- [ ] 可视化博客主题编辑 (预计0.8.0版本发布)
- [ ] 添加后端及后端文章管理面板支持 (等待Ocean项目， 预计1.0.0+)
- [ ] 添加本地文章与云端进行数据同步支持 (等待Ocean项目, 预计1.0.0+)
- [ ] 添加双向链支持
- [ ] 相册板块

**非重要:**

- [ ] 添加黑夜白天页面过度动画
- [ ] 添加更多画面效果内置支持，如樱花飘落、星空等
- [ ] 添加首页视频播放效果
- [ ] 添加网页右下角工具组件
- [ ] 优化网页加载，如网络不好博客产生加载闪烁
- [ ] 添加网站导航网站模板

### 🌟 鸣谢

- [云游君(云猫猫)](https://valaxy.site/)
- [樱花庄的白猫博客主题](https://github.com/mashirozx/sakura)
- [hexo-theme-sakura](https://github.com/honjun/hexo-theme-sakura)
- [vitepress-theme-sakura](https://github.com/flaribbit/vitepress-theme-sakura)
