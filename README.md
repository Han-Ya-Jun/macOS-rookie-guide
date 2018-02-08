# macOS入门
```
by 东武
鸣谢 志伟
2018-02-08
```
## 很不专业的名词解释

- macOS/OS X: mac设备的图形界面操作系统名称，旧名为OS X，16年改为了macOS.
- Darwin: macOS和iOS的底层操作系统，类Unix，Mach + BSD，开源的。
- APFS: Apple File System, 针对固态存储优化过的文件系统。
- Apple ID: 苹果账户。
- App Store: 卖app的，需要Apple ID登录之后才能下载安装app。
- Apple Store: 卖苹果设备的，深圳的线下店在益田。
- iCloud: apple体系下的同步云存储，需要Apple ID。
- iTunes: 设备管理工具以及媒体库管理工具。
- Finder: 文件管理器。
- Dock: 放快捷方式的地方。
- AirDrop: 点对点传输文件，入口在Finder，依赖Wi-Fi和蓝牙。
- Handoff: iPhone, iPad和Macbook同步一些事件以利于切换使用设备。比如iPhone的来电在mac上接听，iPhone浏览的网页在mac上继续查看。
- Spotlight: 搜索和快捷命令的入口, 热键:⌥ + space(看不懂这个热键请继续往下)。另，强烈推荐使用第三方app: alfred, 替代Spotlight，很强大。
- FileVault: 磁盘加密，推荐打开，在"系统偏好设置"里可以找到。
- SIP: System Integrity Protection，简答来说，当开启SIP时，就算有root权限，也不能改动受到保护的系统文件。
- Boot Camp: 装双系统用的bootloader辅助工具。
- LLVM: 编译工具链及平台。比起gcc，LLVM和苹果的关系更亲密。
- 抹掉: 格式化。

## 关机

合上盖子就行

## 触摸板手势

从一根手指到五根手指，各种点按和触摸的搭配。在"系统偏好设置"里可以找到，建议全部勾上，逐一尝试。

*TIPS:* `滚动方向推荐: 自然`

## 热键

1. 牢记下列按键的提示图标和名称

- Command 键 ⌘
- Shift 键 ⇧
- Option 键 ⌥
- Control 键 ⌃
- Caps Lock 键 ⇪
- Fn 键
- Space 键

*TIPS:* `在大部分情况下，macOS的Command键 == Windows的ctrl键`

2. [热键官方文档](https://support.apple.com/zh-cn/HT201236)

3. 热键的终极解决方案:
[Cheatsheet](https://www.mediaatelier.com/CheatSheet/).  一个热键查看的利器，安装之后在任意界面长按⌘就能看到当前可用的热键，当然，要背熟上面的图标。

4. 举例几个常用热键

- 复制: ⌘ + c
- 粘贴: ⌘ + v
- 行首: ⌃ + a(vim除外)
- 行尾: ⌃ + e(vim除外)
- 向后删除: fn + del
- 框选截图到粘贴板: ⌃ + ⌘ + ⇧ + 4
- 移动: ⌘ + ⌥ + v
- 强制退出: ⌘ + ⌥ + esc
- 删除文件: ⌘ + del
- 当前应用的设置页面: ⌘ + ,

## 应用

### 几个名词

- .dmg: 一种镜像文件的格式
- Package(.pkg): 一种打包应用的方式，胜在single file
- Bundle(.app etc): 另一种打包软件包的方式。本质是一个文件夹，有其构建标准。macOS在大多数UI上会把符合bundle构建标准的文件夹展示为一个图标(该bundle内提供的)，并且可以双击执行，看起来就和Windows的exe文件很类似。

### 安装应用

- App Store，首推
- Brew, 开发者常用，各种开发工具、库、devel包在app store是没有的
- Brew Cask, 尽量app store，没有的才到这里找
- 自行下载安装包。绝大多数情况下，下载到的安装包都是dmg格式的。双击dmg文件之后其实做的是一个镜像挂载操作并在finder打开镜像里面的内容。大部分情况下是一个bundle包，看起来就是一个app的图标，它的旁边一般会有一个名为application的文件夹, 把app拖到application文件夹即可。另一种情况是pkg包，类似windows下面的安装器，双击之后下一步下一步安装即可，这种安装一般会请求root权限，谨慎一点。

### 卸载应用

- App Store安装的类似iPhone，在launchpad内长按图标，瑟瑟发抖之后点左上角的X删掉
- Bundle形式的，在`/Applications`内删掉对应的.app目录即可
- pkg安装方式的自行搜索，都是特异性的

### 应用推荐

***TIPS:***
```
1. 环境搭建三连: 申请apple id -> app store安装Xcode(装好记得打开走一遍init流程) -> 安装homebrew

2. 打"必装"和"强烈推荐"等tag的应用都是富有特色的好东西，类似docker这种常规东西就不打tag了。
```

*注：* `app太多，分了几类，就不一一附链接了。其中一部分app是抛砖引玉的意图，带有个人喜好因素，目的是展示支持mac的应用已经很多了。对自己熟悉的工具用App Store/brew/brew cask/google等搜一下看看有没有mac版本。`

#### 开发

- Xcode(**必装**, 大部分都是冲着commandline tools去的，为了更新方便就一起装了。在App Store装)
- [Homebrew](https://brew.sh/)(**必装**, macOS下的yum/apt-get)
- [Homebrew Cask](https://caskroom.github.io/)(**推荐**, 安装带UI app的homebrew)
- Oh my zsh(**强烈推荐**, 替代默认的bash)
- iTerm2(**强烈推荐**, 替代默认的term. 可以配置酷炫的terminal)
- Docker
- Docker-machine
- Sublime
- Atom
- VSCode
- IntelliJ
- Parallels(macOS专有的虚拟机app, 商业软件)
- VMware
- VirtualBox
- AndroidStudio

#### 效率

- [ShadowsocksX-NG](https://github.com/shadowsocks/ShadowsocksX-NG/releases)(**梯子**)
- [Alfred](https://www.alfredapp.com/)(**强烈推荐**, [介绍](https://www.jianshu.com/p/e9f3352c785f)。注意，理论上powerpack enhancement是需要花钱的)
- [Dash](https://kapeli.com/dash)(**强烈推荐**, 离线api文档工具,支持的语言、开发组件和框架很广泛,  梯子不灵的时候顶用。在线可github/stackoverflow)
- The Unarchiver(UI下使用的解压app)
- 有道词典 + alfred workflow
- Xmind
- FlowVPN
- Dropbox
- TeamViewer
- Araxis Merge(图形化diff工具)
- siri(?_?)
- Etcher(烧写linux发行版启动u盘)
- Synergy(跨机器、多平台的鼠标键盘同步工具)
- CleanMyMac
- CleanAPP
- Caffeine(**推荐**, 一个不锁屏不灭屏的小工具, 类似app很多)
- Manico
- PopClip
- XtraFinder
- Shortcat
- Bartender
- SizeUp
- thefuck(很搞的一个cmdline tool)

#### 办公

- Office
- iWork
  - Pages: 苹果的word
  - Numbers: 苹果的excel
  - Keynote: 苹果的powerpoint
- iMovie
- iPhoto
- GarageBand
- Adobe family
- Chrome
- Safari
- Firefox
- Opera
- Kindle
- 输入法(原生/搜狗等)
- QQ
- 微信
- 阿里旺旺
- Foxmail
- 自带Mail客户端
- Evernote
- 有道云笔记
- Fantastical 2
- Snip
- CheatSheet

#### 娱乐

- QQ音乐/网易云音乐
- 腾讯视频/优酷/爱奇艺(因为flash的原因，在mac上推荐用原生客户端而不是浏览器来看视频，国内这几家也都有原生的。)
- 迅雷
- Folx(下载工具)
- Battle.net
- Steam

#### 其他

- 忘掉杀毒软件
- 暂无丰声

## 文件系统

u盘推荐使用exFAT文件系统。不太推荐ntfs, mac对ntfs的支持怎么搞都有点别扭。通用性上，exFAT在windows/linux/macos上都没问题，也没有FAT单个文件4GB的限制。

## 重装系统

按住cmd + r开机，会进到隐藏关卡。

*TIPS:* `强烈不建议自己给macbook重新分区，不要手贱`

## one more thing

如果是使用公司发的mac，注意公司的使用条例。另，公司安装的管控软件会写不少日志，所以Apple ID/iCloud等隐私问题也请注意，可以设置不同步。

## Reference
- mac布道名人: 池建强
- [少数派报告](https://sspai.com)
- [<<高效MacBook工作环境配置>> 2017更新版
](https://mp.weixin.qq.com/s/TBeh3buH0X_-1g56HCI_gQ)
- [awesome-macOS](https://github.com/iCHAIT/awesome-macOS)
- [awesome-mac](https://github.com/jaywcjlove/awesome-mac)
- [terminal-mac-cheatsheet](https://github.com/0nn0/terminal-mac-cheatsheet)
- [UI-Development-Environment-on-Mac](https://github.com/kayo5994/UI-Development-Environment-on-Mac)

