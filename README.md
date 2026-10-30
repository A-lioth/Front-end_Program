# Front-end_Program

一个用于存放前端练习与小型项目的**合集仓库**：根目录下并列放着若干个相互独立的前端练习/小项目，各自有各自的目录、技术栈和打开方式，彼此之间没有构建或依赖关系。本 README 作为整个仓库的索引，逐个说明每个子项目。

> 仓库根目录本身没有 `package.json`、`pnpm-workspace.yaml` 或根级 `.gitignore`，也不是一个统一的应用工程——**不存在**"在根目录装一次依赖然后一次跑起来"的用法，详见[整体运行 / 构建方式](#整体运行--构建方式)。

## 子项目一览表

| 子项目目录 | 技术栈 | 一句话说明 |
| --- | --- | --- |
| [`pink-H5C3/`](pink-H5C3) | 原生 HTML5 + CSS3（无 JS、无构建工具） | 31 个单页练习，涵盖 CSS 布局、CSS3 新特性、HTML/HTML5 标签，以及"品优购"商城和"学成在线"两个整站静态页 |
| [`NewYear/`](NewYear) | 原生 HTML + CSS + Canvas 2D JavaScript | 新年倒计时 + 烟花粒子动画页面（目标时间为 2025-01-01） |
| [`test/`](test) | Vue 3.5 + Vite 7（JavaScript，非 TypeScript） | 由 `create-vue` 脚手架生成的 Vue 3 练习工程，目前基本是模板页 + 一个实验性计数器组件 |
| [`网页设计_银川风景名胜/`](网页设计_银川风景名胜) | 原生 HTML + CSS（`styles.css` 为 GBK 编码） | 银川旅游主题的 4 页静态站点（首页 + 宁夏博物馆 / 镇北堡西部影城 / 贺兰山三个景点页） |
| [`视频展示/`](视频展示) | 无代码（纯素材） | 仅含一个 `video.mp4` 视频素材（约 178 MB），没有页面文件，用途待补充 |
| [`swms-web/`](swms-web) | Vue 3 + TypeScript + Vite + pnpm monorepo + Module Federation | 独立的智慧水务系统前端工程，**本身是一个独立的 Git 子仓库**，已有完整文档，见 [swms-web/README.md](swms-web/README.md) |

## pink-H5C3

跟随"前端 HTML+CSS"课程做的单页练习集合，**全部是原生 HTML/CSS**：每个练习就是一个可以双击打开的 `index.html`（少数练习另带一个 `style.css`），没有 JavaScript、没有 `package.json`、没有构建流程。

### 技术栈

- HTML5 语义化标签、表单与多媒体标签
- CSS：盒模型、浮动布局、定位、`clearfix` 清除浮动、CSS 初始化（京东/淘宝风格）
- CSS3：`box-sizing`、过渡 `transition`、伪元素 `::before/::after`、属性选择器、结构伪类选择器
- 图标：品优购页面使用 `icomoon` 字体图标（`fonts/icomoon.*`，通过 `@font-face` 引入）
- 页面内图片部分直接引用外链（如小米、淘宝案例），部分使用本地 `images/`、`upload/` 素材

### 目录结构

```text
pink-H5C3/
├── CSS/                      # 15 个 CSS 基础布局练习
│   ├── 三角妙用/              # 用 border 画三角形做价格标签
│   ├── 五彩导航/              # 导航栏 hover 变色
│   ├── 产品模块/
│   ├── 京东CSS初始化/         # 只有 style.css，京东风格的 CSS reset
│   ├── 京东三角/
│   ├── 土豆网显隐遮罩/        # hover 显示半透明遮罩
│   ├── 小米网页布局/          # 小米手机模块的浮动布局
│   ├── 小说排行榜/
│   ├── 底端页码/              # 分页条样式
│   ├── 新浪导航/
│   ├── 新闻快报/
│   ├── 新闻页面/
│   ├── 淘宝焦点图/            # 轮播图静态版（左右切换按钮）
│   ├── 简洁版小米侧边栏/
│   └── 鼠标样式/
├── CSS3/                     # CSS3 新特性练习
│   ├── 三角/
│   ├── 盒子模型/              # content-box vs border-box 对比
│   ├── 过渡/                  # transition：进度条、小米 logo 切换
│   └── 选择器/
│       ├── 属性选择器/
│       ├── 结构伪类选择器/
│       └── 伪元素选择器/
├── HTML/                     # HTML 基础练习
│   ├── 圣诞节案例/            # Christmas.html（锚点跳转）+ man.html
│   ├── 小说排行榜/
│   └── 注册页面案例/          # 用 table 排版的注册表单
├── HTML5/                    # HTML5 标签练习
│   ├── 多媒体标签/            # <video>/<audio>（素材文件缺失，见备注）
│   ├── 表单标签/              # email/url/tel/color/time/number/search 等 input 类型
│   └── 语义化标签/            # header/nav/section/aside/footer
├── 品优购/
│   └── shoping/              # 较完整的电商静态站（3 个页面）
│       ├── index.html        # 首页：快捷导航、头部、搜索、分类导航、快报、生活服务、今日推荐、楼层、页脚
│       ├── list.html         # 列表页：带"秒杀"模块的商品列表
│       ├── register.html     # 个人注册页：手机号/验证码/协议勾选
│       ├── css/              # base.css（初始化）、common.css（版心 .w / 浮动 / 字体图标）、index.css、list.css、register.css
│       ├── fonts/            # icomoon 字体图标（eot/svg/ttf/woff）
│       ├── images/           # logo、图标、提示图等
│       └── upload/           # 楼层与推荐位图片
└── 学成在线/
    ├── index.html            # 在线教育站点首页：头部、banner + 侧边分类 + 我的课程表、精品推荐、页脚
    ├── style.css
    └── images/
```

### 主要功能

- `CSS/`、`CSS3/`、`HTML/`、`HTML5/` 下每个子目录都是一个独立的小练习页，用于演示单个知识点（三角形、遮罩、分页、过渡、选择器等）。
- `品优购/shoping/` 是三页电商静态站：首页（`index.html`）→ 列表页（`list.html`，含秒杀区块）→ 注册页（`register.html`）；三个页面共用 `css/base.css` 与 `css/common.css`，通过 `.w`（1200px 版心）与 `.fl`/`.fr` 浮动工具类统一布局。
- `学成在线/index.html` 是单页在线教育首页，含二级分类侧栏、课程表卡片与精品推荐课程列表。

### 运行方式

无依赖、无脚本，直接打开 HTML 即可：

```bash
# 方式一：文件管理器双击，例如
pink-H5C3/品优购/shoping/index.html

# 方式二：起一个静态服务器（推荐，避免个别浏览器的本地文件限制）
npx serve pink-H5C3        # 或 python -m http.server
```

## NewYear

一个纯前端的"新年倒计时 + 烟花"演示页，用 Canvas 2D 手写粒子系统，无任何第三方库。

### 技术栈

- 原生 HTML + CSS（`position: absolute` 居中、媒体查询适配小屏）
- 原生 JavaScript（ES6 `class`、`requestAnimationFrame`、Canvas 2D）
- 外部资源：背景音乐通过网易云音乐外链播放（`music.163.com/song/media/outer/url?id=...`）

### 目录结构

```text
NewYear/
├── index.html      # 倒计时文本 #countdown、<canvas id="fireworksCanvas">、祝福语 #greetings、<audio id="bgm">
├── script.js       # Particle / Firework 类 + 倒计时逻辑 + 动画循环
└── styles.css      # 全屏布局、元素居中、小屏字体适配
```

### 主要功能

- **倒计时**：每秒计算到 `2025-01-01 00:00:00` 的天/时/分/秒并写入 `#countdown`。
- **烟花动画**：`Firework` 从画布底部随机位置升空，上升到画布自上而下 18%–40% 的位置时爆炸（`y < canvas.height * (0.18 + Math.random() * 0.22)`），生成 100–1100 个粒子；爆炸图案在圆形、星星、爱心、散射、螺旋 5 种中随机；粒子带重力、透明度衰减，用半透明黑色矩形覆盖画布形成拖尾。
- **到点庆祝**：倒计时小于 0 时隐藏倒计时、显示 `2025, 新年快乐！`，并启动烟花（初始 30 发 + 每 200ms 补一发）。
- **背景音乐**：`toggleSound()` 配合 `setInterval(..., 1)` 反复尝试播放，属于绕过浏览器自动播放限制的写法（实现较粗糙，见备注）。

### 运行方式

```bash
# 直接打开，或起静态服务器
NewYear/index.html
npx serve NewYear
```

## test

由 `create-vue` 脚手架生成的 **Vue 3 + Vite** 练习工程（JavaScript 版，未使用 TypeScript），目前基本停留在模板状态，只额外加了一个实验组件和一个独立的爱心动画页。

### 技术栈（依据 `package.json`）

| 分类 | 依赖 |
| --- | --- |
| 运行时 | `vue` `^3.5.29` |
| 构建 | `vite` `^7.3.1`、`@vitejs/plugin-vue` `^6.0.4` |
| 开发辅助 | `vite-plugin-vue-devtools` `^8.0.6` |
| Node 要求 | `^20.19.0 \|\| >=22.12.0`（`engines` 字段） |
| 别名 | `@` → `./src`（`vite.config.js` 与 `jsconfig.json` 中均配置） |
| 包管理 | 仓库内只有 `package-lock.json`（lockfileVersion 3），因此按 npm 使用 |

### 目录结构

```text
test/
├── index.html                  # Vite 入口，挂载 #app，加载 /src/main.js
├── vite.config.js              # vue() + vueDevTools() 插件、@ 别名
├── jsconfig.json               # @/* → ./src/*
├── package.json / package-lock.json
├── README.md                   # create-vue 生成的英文模板说明
├── test.html                   # 独立页面：纯 CSS 动态爱心（不经过 Vite 入口）
├── public/favicon.ico
├── .vscode/                    # 推荐 Vue.volar 扩展、文件嵌套设置
├── .idea/                      # JetBrains IDE 配置
└── src/
    ├── main.js                 # createApp(App).mount('#app')
    ├── App.vue                 # 模板首页：logo + HelloWorld + TheWelcome
    ├── assets/                 # base.css、main.css、logo.svg
    └── components/
        ├── HelloWorld.vue      # 接收 msg prop 的标题组件
        ├── TheWelcome.vue      # 脚手架欢迎区块
        ├── WelcomeItem.vue     # 欢迎区块的条目容器
        ├── icons/              # IconDocumentation / IconTooling / IconEcosystem / IconCommunity / IconSupport
        └── Test.vue            # 实验组件：模板里放了按钮计数器，但 script 中又 createApp 并 mount('#app')
```

### 主要功能

- 默认页面就是 Vue/Vite 脚手架欢迎页（`App.vue` → `HelloWorld` + `TheWelcome`）。
- `test.html` 是一个不依赖 Vue 的独立静态页：纯 CSS 画心形 + `heartbeat` 关键帧动画，鼠标悬停暂停动画并变色。
- `Test.vue` 是一个未完成/实验性的计数器组件：它没有通过 props 与父组件通信，而是在 `<script setup>` 里再次 `createApp({...}).mount('#app')`，属于重复挂载的错误写法；且 `main.js` 里 `import Test from './components/Test.vue'` 后并未使用，该组件实际上没有被渲染。

### 运行方式（依据 `scripts`）

```bash
cd test
npm install        # 仓库内是 package-lock.json，故用 npm
npm run dev        # vite，启动开发服务器
npm run build      # vite build
npm run preview    # 预览构建产物
```

`test.html` 无需构建，直接用浏览器打开即可。

## 网页设计_银川风景名胜

一个以银川旅游为主题的静态多页站点，共 4 个 HTML 页面 + 1 个公共样式表 + 3 张配图。

### 技术栈

- 原生 HTML5（`<header>`/`<nav>`/`<main>`/`<footer>` 语义化结构）
- 单文件公共样式 `styles.css`（含 `@media` 针对 1024×768 分辨率的定宽适配）
- 无 JavaScript、无依赖、无构建工具
- 注意：`styles.css` 是 **GBK 编码**（以 UTF-8 读取会乱码），HTML 文件本身为 UTF-8

### 目录结构

```text
网页设计_银川风景名胜/
├── index.html              # 首页：标题 + 导航（三个景点）+ 银川城市介绍长文 + 了解更多 + 页脚
├── ningxia_museum.html     # 宁夏博物馆：大图 + 简介 + 百科链接 + 返回首页
├── zhenbei_film_city.html  # 镇北堡西部影城：同上结构
├── helan_mountain.html     # 贺兰山风景区：同上结构
├── styles.css              # 头部蓝色 #3498db、页脚固定底部、版心与媒体查询
├── ningxia_museum.jpg
├── zhenbei_film_city.jpg
└── helan_mountain.jpg
```

### 主要功能

- 首页展示银川历史沿革介绍，并通过 `nav` 链接到三个景点子页。
- 三个景点页结构一致：标题、1500×600 大图、一段简介、百度百科外链、"返回首页"链接。
- 页面间跳转为相对路径，无需服务器也能在本地打开（图片为同目录相对引用）。

### 运行方式

```bash
# 直接打开
网页设计_银川风景名胜/index.html
```

## 视频展示

### 技术栈

无代码、无配置，仅有一个视频素材文件。

### 目录结构

```text
视频展示/
└── video.mp4      # 约 186,974,585 字节（≈178 MB）
```

### 主要功能

待补充：目录内没有 HTML 页面、脚本或说明文件，也没有任何文件引用该视频，因此无法从仓库内判断它的用途或展示方式。

### 运行方式

待补充（无页面可运行）。如需预览，可用任意本地播放器打开 `视频展示/video.mp4`。

## 整体运行 / 构建方式

各子项目**完全独立**，需要分别进入各自目录处理：

| 子项目 | 是否需要安装依赖 | 启动 / 构建 |
| --- | --- | --- |
| `pink-H5C3/` | 不需要 | 直接用浏览器打开各 `index.html`，或 `npx serve pink-H5C3` |
| `NewYear/` | 不需要 | 打开 `NewYear/index.html`，或 `npx serve NewYear` |
| `网页设计_银川风景名胜/` | 不需要 | 打开 `index.html` |
| `test/` | 需要 | `cd test && npm install && npm run dev`（构建：`npm run build`） |
| `swms-web/` | 需要（pnpm workspace） | `cd swms-web && pnpm install && pnpm dev:all`，详见其自身 README |
| `视频展示/` | 不需要 | 无页面，仅素材 |

纯静态的三个子项目（`pink-H5C3`、`NewYear`、`网页设计_银川风景名胜`）都没有构建步骤，也不产出 `dist/`；根目录也没有统一脚本可以批量启动或构建它们。

## 备注

- **仓库性质**：这是一个练习/学习性质的合集仓库，`pink-H5C3` 明显来自 HTML+CSS 课程作业，`test` 是脚手架模板，`NewYear` 与 `网页设计_银川风景名胜` 是课程/个人练手页面。`swms-web` 则是另有一个独立仓库的完整工程，性质与前几者不同。
- **Git 状态**（`git status` 只读查看，未做任何改动）：当前分支 `main`，跟踪 `origin/main`（`https://github.com/A-lioth/Front-end_Program.git`），共 64 次提交，最近一次提交为 `27f07d7`（2024-11-06，"优化请假页面样式及结构…"）。
  - 未提交/未跟踪内容：`NewYear/`、`swms-web/`、`视频展示/` 整体未被跟踪；`test/` 除 `src/components/Test.vue` 外基本都未跟踪；`test/src/components/Test.vue` 处于 `AM`（已 add 后又有改动）。
  - 工作区删除：`请假页面/index.html` 与 `请假页面/yes.png` 已被删除（`D`），该目录在磁盘上已不存在，但仍是 HEAD 中跟踪的文件。
  - 仓库内**没有根级 `.gitignore`**，`node_modules/`（`test/`、`swms-web/`）目前靠各子项目自带的 `.gitignore` 忽略；`swms-web/.gitignore` 只忽略 `node_modules/`、`dist`、`.idea`、`.__mf__temp/`、`@mf-types/` 等。
- **子仓库关系**：`swms-web/` 内含自己的 `.git`，远端为 `https://gitee.com/hetian-xinyihua/swms-web.git`，但根仓库没有 `.gitmodules`，所以它不是标准 submodule，而是"仓库里套仓库"（未跟踪状态）。克隆根仓库时不会自动获得该目录。
- **缺失素材**：
  - `pink-H5C3/HTML5/多媒体标签/index.html` 引用的 `video.mp4`、`audio.mp3` 在该目录下不存在（该目录只有 `index.html`）。
  - `NewYear/styles.css` 引用 `assets/a.png` 作为背景图，但 `NewYear/` 下没有 `assets/` 目录，该背景不会显示。
- **过时/可改进之处**：
  - `NewYear` 的目标时间硬编码为 `Jan 1, 2025 00:00:00`，该时间已过，页面打开后会立刻显示"2025, 新年快乐！"并放烟花，倒计时不再生效；页面标题与文案也仍是 2025。
  - `NewYear/index.html` 用 `setInterval("toggleSound()", 1)`（1 毫秒）反复尝试播放外链音乐，属于轮询式绕过自动播放限制，开销大且依赖第三方音乐接口是否可用。
  - `test/src/components/Test.vue` 在 `<script setup>` 内再次 `createApp(...).mount('#app')`，且 `main.js` 中导入后未使用，是无效代码。
  - `test/package.json` 要求 Node `^20.19.0 || >=22.12.0`；本机当前 Node 为 v22.22.2，满足要求。
  - `pink-H5C3` 部分页面直接引用外链图片（如 `s3.xchuxing.com`、`gw.alicdn.com`、`pic.baike.soso.com`），断网或外链失效时图片无法显示。
  - `网页设计_银川风景名胜/styles.css` 为 GBK 编码，与其他文件的 UTF-8 不一致，跨平台编辑时容易乱码。
- **未核实信息**：`视频展示/` 的用途、`pink-H5C3` 中部分练习的教学出处，均无法从文件内容确认，按"待补充"处理。
