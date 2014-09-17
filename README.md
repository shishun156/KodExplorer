﻿##KodExplorer (http://kalcaddle.com/)
###ver2.73(2014.9.17)
`商业版授权请联系：kalcaddle#qq.com`

####  1.是什么：
 - Kodexplorer为千帆网络工作室开发的一款服务器文件管理程序。
 - 完美取代FTP管理：可用于服务器文件管理,zip解压缩、备份还原、支持图片、音乐、视频预览、office、pdf等格式在线预览。文件夹拖拽上传……。
 - 在线编程：支持几乎所有编程语言的在线编辑(高亮,多光标编辑.堪比本地的sublime)
 - 极佳的操作体验：及其便捷的快捷键支持,让你拥有本地化的体验
 - 中文等多语言支持：中文编码全面兼容,文件编辑自动适配。
 - 超快的速度：全面采用Ajax+Json进行数据通信,毫秒级的响应速度；
 - 全平台兼容性：Win Linux Mac (Apache、Nginx、IIS)

#### 2.使用场景：
 - 取代FTP,服务端、客户端软件等复杂的安装配置。kod可以一键安装随处使用.
 - 你可以用它来管理你的服务器(备份,在线解压缩,版本发布....)
 - 你可以把他当做管理linux的一个操作系统界面
 - 可以用来作为私有云存储系统,存储你的文件...
 - 当然你也可以用来分享文件
 - Web IDE
 - 更多场景等你来挖掘！……

#### 3.使用说明
    管理员：  admin/admin
    普通用户：demo/demo
    游客用户：guest/guest
    [如何使用] 下载程序,解压上传到你的服务器路径下,data目录设置777权限。访问体验超便捷的服务吧！
    (为确保数据安全，最好配置服务器不允许列目录)
    [关于上传问题] 程序没有做任何限制,如果需要上传大文件,则修改
      php.ini：`upload_max_filesize = 1000M post_max_size = 1000M`  [详情：http://955.cc/R2yT]
    [关于解压缩问题] 程序不做任何限制,如若失败请设置php内存限制。memory_limit  1000M
    [关于"系统错误"] 请配置php错误提示级别error_reporting; 配置php.ini或者允许error_reporting函数
    [关于兼容性] 建议使用chrome firefox ie9+  体验更完整。ie8以下基本上不做兼容处理。chrome支持文件夹拖拽上传。
    [文件打开] office文件在线预览功能,服务器必须在公网(外部能访问该服务器);
        内部或局域网需要使用请参考qq群共享“web office搭建”,然后配置kod程序config/config.php OFFICE_SERVER
    [安全提示] 为确保数据安全，请设置http服务器不允许列目录。[详情：http://955.cc/R2vw]
    [忘记密码] 修改data/system/member.php 密码为明文的md5值 例如将admin密码重设为admin
        则修改第一行："name":"admin","password":"21232f297a57a5a743894a0e4a801fc3"

![](https://cloud.githubusercontent.com/assets/3761968/2583304/764f562a-b9cf-11e3-8e59-afdbdffc20eb.png)

###ver2.73 `2014/9/17`
####fix bug:
 - 安全优化补丁


###ver2.72 `2014/9/16`
####fix bug:（bug解决和程序优化）
 - 任意执行：远程下载apache 扩漏洞：判断扩展名中是否含有.php.
 - 不存在的用户
 - 桌面：开始按钮被tab盖住了
 - 主题切换,错位问题
 - 透明对话框拖动时 标题栏不显示问题

###ver2.71 `2014/8/31`
----
####update:
 - 编辑器配置保存：文字大小、主题风格；主题修改
 - 精简初始桌面应用

####fix bug:（bug解决和程序优化）
 - 修改用户密码失败：
 - 打开设置设置壁纸，关掉，再打开个人中心，桌面乱掉
 - 桌面开始菜单  最大化问题
 - 语言选择下拉菜单错位
 - 修改主题重叠问题
 - appstore 添加应用tips不见


###ver2.7 `2014/8/25`
----
####update:
 - 安全及性能优化
 - 静态文件加入?版本标识，版本更新后不缓存
 - webuploader 升级到0.14 优化部分上传问题
 - 错误级别：error_reporting(E_ERROR | E_WARNING);
 - 地址栏(tab模式、编辑模式)两种模式宽度自适应
 - 自建office解析服务器配置
 - 最大化全屏

####fix bug:（bug解决和程序优化）
 - install 加入iconv、mbstring检测
 - 右键重命名 快捷键冒泡处理
 - 文件列表图片缩略图拖拽问题
 - 标题超出部分截取优化
 - 编辑器预览滚动条自适应



###ver2.61 `2014/7/12`
----
####update:
 - 实时搜索，根据搜索框内容变化，实时选中匹配到的结果;
 - 弹出搜索框遍历子文件夹递归搜索
 - session key 加入kod_前缀  避免和其他系统key冲突
 - 编辑器选中优化 选择鼠标到窗口外事件处理

####fix bug:（bug解决和程序优化）
 - backspace后退截获浏览器事件,作为后退前一次访问的文件夹;
 - 搜索首字母不匹配问题
 - 弹出层中的弹出层关闭，父窗口失去焦点问题。
 - 代码中grunt部分代码拆分开，放到程序外面；提交到git、osc
 - 桌面：删除alert enter快捷键删除
 - install 检测 加入跳过，(只判断用到的函数) 加入多语言
 - zip压缩没有权限  提示红色,false 统一查找
 - 登录成功后 验证码输错清除 
 - 非root用户拖拽到文件夹问题
 - 非root解压问题 不能解压
 - list oexe 图标问题
 - 用户目录不存在判断
 - fileCahe 互斥锁  reset 不用
 - ie 8~10样式问题调整


###ver2.6 `2014/7/6`
----
####update:
 - 完全性优化;加入严格的校验机制
 - 首次运行环境检测[data目录检测，必须的函数支持提示]
 - 上传已存在处理——创建副本(另外包括粘贴，解压)
 - 选中优化 ctrl选中拖拽
 - 键盘快捷键选中文件,多个字符支持
 - 文件文件夹权限修改(右键——属性,即可修改)
 - 对话框加入ico,对应任务栏
 - 右键等部分菜单效果优化
 - 远程下载加入进度条,下载速度等信息

####fix bug:（bug解决和程序优化）
 - 下载前判断当前目录可写
 - 文件扩展名处理,分为用户方式和扩展名权限方式
 - 上传结束提示：是否成功、失败原因
 - 上传扩展名限制 解决apache .php.*当做php执行bug 
 - 文件名非法字符限定 <script>
 - 树目录展开箭头状态修复
 - 树目录新建文件,没有子节点刷新bug解决
 - 文件大小为0上传不了问题
 - windows下进入某些系统文件夹死循环bug解决
 - tips 居中显示
 - 任务栏标签选中问题：已经显示且为交点窗口 点击——隐藏；否则——显示，并且置为焦点窗口
 - 拖入url ——oexe 新窗口打开
 - 选中文件时,移动到屏幕可视区域(解决上下左右选中文件滚动条不一致问题)


###ver2.51 `2014/6/22`
----
####fix bug:（bug解决和程序优化）

 - 登陆多次密码输入错误验证码bug解决
 - 修复漏洞：创建副本加入权限控制。和拖文件拽权限一致
 - 文件上传失败检测
 - 树目录同步优化


###ver2.5 `2014/6/15`
----
####update:
 - 增加创建副本功能 按住ctrl拖拽即可，可以到当前，也可以到文件夹。
 - 多选拖拽优化：剪切到、移动到某个文件夹
 - 创建副本功能
 - 树目录和文件列表一致性保持 更新相互通知

####fix bug:（bug解决和程序优化）
 - 桌面重命名bug
 - 统一对话框部分bug
 - php notice 提示解决
 - ajax返回非json 则展示服务错误的返回
 - 所有入口都加入index.php 解决部分服务器没有设置默认入口问题

###ver2.4 `2014/6/8`
####update:
 - 语言选择
 - 远程下载文件名优化
 - 树目录事件优化
 - 收藏夹点击 undefined   
 - 没权限建立文件夹错误提示 红色 
 - 打开dialog 不显示问题。先显示后打开 
 - ajax error 系统错误  对话框提示内容
 - 懒加载优化


###ver2.3 `2014/6/2`
----
####update:
 - 拖动url——创建ext app
 - 文件管理，树目录变化后（增删改）自动同步到文件列表
 - 文件管理，文件列表变化后（增删改）自动同步到树目录
 - 中文用户名限制
 - 对话框打开关闭动画
 - 其他多处优化                        

####fix bug:（bug解决和程序优化）
 - 文件名限制bug
 - 同目录多个程序cookie bug修复
 - 地址栏 最后显示宽度问题
 - 服务器路径下 编辑器预览404修复
 - 树目录显示优化
 - 登陆记住密码优化

###ver2.2 `2014/5/11`
----
####update:
 - 公共目录支持(多个用户可以共享目录,写权限跟随用户组权限设定)
 - 自动升级优化
 - 文件管理工具栏 增加菜单选项，方便移动设备操作
 - 文件编辑器，文件树目录 上下左右键盘切换  快捷键加入
 - 树目录去掉库,改为个人目录等多处文案修改
 - 默认打开用户目录

####fix bug:（bug解决和程序优化）
 - 桌面任务栏点不中bug
 - 部分文案问题
 - 众多细节优化


###ver2.1 `2014/4/2`
----
####update:
 - 文件夹拖拽上传,完美解决(保持原始目录结构)
 - 解压缩优化;解压中文问题。解压缩整体速度
 - 树目录增加快捷键支持（上下、左右展开树目录；复制、粘贴、剪切、删除、打开、搜索、新建文件(夹)、）
 - pdf预览支持
 - mac快捷键 ctrl 一一对应command    
 - 音乐播放器和视频播放器相互独立
 - 图片懒加载、图片较多的情况下只加载首屏图片缩略图;
 - 编辑文件打开出错,自动关闭标签;文件打开20M限制(大于20M则不处理,浏览器会卡死)
 - 标签关闭提示：检测是否有未保存文件，文件修改实时修改是否修修改的按钮状态

####fix bug:（bug解决和程序优化）
 - 文本文件编辑 文件名含有url编码则出错bug
 - 右键菜单在最下面时，右键位置重叠导致点击菜单问题
 - 编辑器打开文件时光标问题，处理：移动到行尾；编辑器enter建不显示自动提示
 - iframe 打开url 优化。解决canvas问题
 - 文件编辑器,载入loading去掉
 - 删除错误时，或上传错误时也刷新目录。删除提示颜色错误
 - 对话框右键 点击右键菜单隐藏修复
 - 手机端  touch =双击
 - 文件列表  explorer  右键 不清除选才·
 - 树目录中文展开问题。
 - ie 重命名状态textarea不可选则问题
 - 修复mac 下 ctrl连选出现右键菜单。
 - ie 树目录右键兼容性
 - 


###ver2.0 `2014/3/2`
----

####fix bug:（bug解决和程序优化）
 - body右键屏蔽(保留input、textarea)
 - 重命名&新建时  右键（编辑内容系统菜单）
 - 对话框 不显示边框（位移处理,opacity：0）
 - esc 退出程序  屏蔽该功能。
 - 关闭播放器,还在播放bug
 - 增加资源管理器任务栏。任务栏加入右键功能。
 - 对话框增加右键功能
 - guest [三类用户 root/default/guest] guest登陆处加链接。20min
 - 打包程序[update  user_add,admin/demo;  删除webuploader.js thumb less]
 - 编辑添加应用权限只能是root用户才可以。
 - 保存文件不可写提示！
 - 解压缩结果提示。（对话框）

####upload
 - dialog display
 - root登陆 目录修改为服务器路径
 - artdialog 已经打开的窗口 (设了id) 最小化时,再次打开则显示
 - 最小化窗口后,再次打开 dialog display (setting-display)
 - 上传进度加入大小
 - 上传窗口关闭,自动停止所有上传队列
 - 拖拽后,更新上传地址为当前地址。(之前上传队列也会这样。bug)
 - root用户非服务器路径下文件预览（图片、mp3、视频、html、swf、……php代理输出文件内容,http方式）
 - 对话框最小化或关闭,重置最大index为焦点窗口
 - 图片缩略图生成：小于5k则不生成（直接输出）
 - 加载文件列表改为异步方式,数据返回采用回调函数方式。增强体验
 - 选中优化,文件&文件夹重命名、文件&文件夹新建 后自动选中。(f5增加回调。)；
 - 选中保持,选中后如果调整排序等等,保持选中状态。
 - 上传文件选中当前。
 - f5改为异步(加入mask  loading) 优化文件夹打开体验
 - 键盘按键选中文件  增加字符搜索定位功能(单个字符,增加到多个字符选中。两次响应直接延迟250ms)
 - 幻灯片播放[优化成fancybox或者  重写动画部分、打开时关不掉问题]
 - 编辑器backspace、delete时不提示。
 - 编辑器,增加选中效果
 - 增加不自动提示功能,配置项作为全局配置。影响后续建立的文件。选中标记状态。
 - 更换桌面背景图片【load后替换】
 - 更换主题【css load 后载入】
 - 删除。不清除选中。提前准备数据
 - 构建打包,合并压缩。添加版本、版权
 - 自动升级(本地记录版本,服务器js调用 参数  url、###version；忽略此版本。cookie。统计用户)


###ver2.0  debug `2014/3/2`
----
####fix bug:（bug解决和程序优化）
 - 优化文件打开处理
 - 文件&文件夹：含有%、+号的处理(显示不出等问题,encoenURIComponent——rawurldecode)
 - 文件下载,支持大文件下载、断点续传。
 - 解决更改排序方式后 ——对应右键菜单不同步问题。
 - 优化右键更改列表状态,同步保存配置到服务端。
 - 文件浏览器打开(a点击新窗口跳转,a不支持click,用子元素冒泡来实现点击)
 - 优化配置文件存储方案。直接由前端操作后端key,value
 - 修复添加收藏夹问题（已打开设置窗口再添加失败问题）
 - 修复树目录中文文件名bug
 - 优化pic图片幻灯片播放
 - 优化新建文件&文件夹 清空选择状态
 - 对话框组件 ie8 优化；tips不显示任务栏；
 - 优化地址栏过长编辑状态问题
 - 优化新建、重命名文件(夹) 高度自适应问题  
 - firefox ctrl+s 系统对话框屏蔽 
 - 树目录:收藏夹优化(右键绑定)；右键操作优化,拖拽优化（文件管理&编辑器）
 - 收藏夹优化（右键    >编辑删除）

####update:
**新增功能**

 - 多用户、权限控制：
 - 可以建立权限组,将功能分配给权限组
 - 添加用户,选择所属的权限组。
 - 权限按功能划分成颗粒,可以任意配置,例如普通使用者、游客等
 - 搜索：支持递归搜索,可选择是否搜索文件内容。
 - 增加桌面自定义壁纸。
 - 皮肤优化  ok  多色彩支持。
 - 应用商店,root用户可以管理应用。安装、修改、删除。普通用户可以安装应用。
 - 应用添加了图标。对应右键功能。
 - office文档在线预览。
 
**上传下载**

 - 采用全新上传控件,跟安全,更好的体验。
 - 拖拽支持文件夹,多个文件。上传自动过滤不允许的文件类型
 - 拖拽上传 和上统一优化,修复webuploader的文件判断；火狐拖拽上传,ie9+拖拽上传。
 - 上传时自动过滤不合格的文件,上传失败错误返回。

**文件编辑**

 - 编辑器支持多光标
 - 支持几乎所有编程语言的代码高亮
 - 支持代码自动补全（基于文档、或自定义的代码快照）
 - 快速预览功能
 - 优化文件保存完美解决。编码自动识别转换。（字符串转义问题。1&#'[{'"+~%25\\\\ ////）
 - 文件编辑,添加收藏夹
 - 优化音乐播放器,添加音乐后自动播放新添加的第一首；解决之前添加列表后暂停问题。
 - 优化任务栏,多标签；最小化flash问题（left+10000 visiable）
 - ctrl,shift 多选时拖拽优化（按住这两个键时,不能拖动；拖动加入延迟200ms）
 - 编辑器在没打开文件的情况下工具栏不可用问题。
 - 搜索、替换；vim模式
 - ……

**登陆退出**

 - 登陆优化  ok【页面&验证码&记住密码】
 - 三次错误需要输入验证码,保证系统的安全性
 - 优化自动登录安全性,客户端保存cookie自动登录信息。【tooken加入本地ip】

**系统优化**

 - 解决较慢操作,阻塞其他操作问题。（同一个用户session会加锁,入口处做释放)
 - 前后端代码基本全部重构,前端采用模块化方法sea.js|require.js  模块化。
 - 凡是有模板调用的（display——页面部分php解析。并将配置注入到页面js变量,便于js使用）
 - 加入模板机制;通用模块采用懒加载模式；使用artTemplate 对模板绑定数据。
 - kv结构存储
 - 路由权限控制
 - 后端统一json输出。  

###ver1.21  `2013/11/6`
----
####fix bug:
 - 修复文件下载bug
 - 修复编辑器自动补全问题,<aa bb /> ——> <aa bb></a> 
 - 兼容部分服务器问题。

###ver1.2  `2013/10/16`
----
####fix bug:
 - 设置,外部通用调用方式
 - 打包中文乱码问题。
 - simple,default主题,navbar 下拉菜单右边位置问题。
 - 文件管理：有滚动条时,上下超过可视区域框选问题修复,统一和win操作一致。
 - 文件大小写不敏感设置,扩展名获取bug
 - 目录读取权限判断,解决“系统错误”相关问题。

####update:
 - 地址栏宽度自适应优化,支持浏览器窗口调整
 - 增加远程下载功能；上传功能优化,
 - 整体样式风格优化,
 - 右键菜单优化(可持续粘贴,剪切后粘贴清空剪贴板)。
 - 新建文件、文件重命名高度自适应优化
 - 关闭调试状态错误信息
 - 图片播放幻灯片优化,支持浏览器窗口调整,解决事件绑定bug,添加图片倒影；添加关闭按钮,关闭动画等功能
 - 优化桌面,弹出层层级问题；任务栏为最上层
 - 优化多标签,没有标签时不显示标签容器,放至层级覆盖
 - 地址栏超出宽度,自动隐藏最左边内容
 - 右键菜单状态同步,排序方式初始化当前值,设置后标记当前值。
 - 优化编辑器：拖动内容&文件到编辑区,内容处理。
 - 拖拽上传,信息框自动隐出后关闭
 - setting,editor,player最小化时,再次调用则显示出弹出层
 - 优化影音播放器,皮肤及相关配置信息存储于js中,不用之前的服务器请求方式,修改皮肤后可以直接更新到界面上。


###ver1.01 `2013/9/10`
----
####fix bug:
 - 添加到收藏
 - simple,default主题,navbar 下拉菜单右边位置问题。

####update:
 - 添加到收藏夹,修改收藏夹,更新文件管理收藏夹部分。
 - 修改主题,同时修改编辑器主题。【编辑区,文件管理,桌面】
 - 优化setting部分代码,整合为一个整体。
 - 优化debug,增加less编译,导出功能优化,先编译后复制再操作


###ver1.0  `2013.9.1`
----
####update:
 - 代码模块化优化,静态文件分离,可以分开部署
 - 编辑器单独逻辑提取,完整融合到文件管理,树目录融合文件管理,懒加载语法高亮
 - 多标签实现,弹层对话框多标签支持,桌面任务栏实现；编辑器多标签支持
 - 弹层功能优化,实现最大最小化,最小化关联多标签任务栏管理

####fix bug:
 - linux 下浏览器打开文件和文件夹,中文问题
 - 重命名&新建&上传 刷新列表使用动画,当前选中失效问题,不使用动画加载方式。
 - html5拖拽上传优化


###ver0.8 `2013.6.15`
----
####update:
 - 整体优化,实现全部操作ajax本地化 ,进一步提升体验
 - 浏览器强刷新,保持之前最后所在路径
 - 重命名,新建,粘贴操作后添加选中状态
 - 代码主题列表优化,重新设计,提高可配置性
 - 优化代码,添加getTplList模版,简化关联配置获取
 - 增加设置功能,ajax刷新设置。缩略图片增加tips预览(被注释frame/setting.php)
 - 增加重命名只选择名称部分功能
 - 增加iframe js api互操作ie支持。四大浏览器内核皆支持。
 - 文件夹打开,采用ajax实现。包括头部地址栏,父级目录,左边树目录以及收藏夹
 - 历史记录完美实现,前进后退按钮实时变化状态。
 - 快捷键backspace实现后退(left header main 分别加入函数,屏蔽默认history(-1)操作) - 

####fix bug:
 - 完善修改windows以及linux获取文件列表,中文路径属性获取失败问题。
 - 复制,剪切。剪贴板内容覆盖判空处理
 - 修复一些地方ajax线程同步问题,重命名后选中失效问题解决
 - 修复返回上层目录,根目录检测
 - 修复linux下 音视频播放,中文路径问题
 - 修复文件右键菜单位置出错问题
 - 修复ie下frame js相互通信问题
 - ajax更新文件列表下,各种bug修复。进一步提升操作友好性
 - 修复当前目录改变的情况下,播放器消失的问题。现在能使播放器始终保留


## editor
![](https://cloud.githubusercontent.com/assets/3761968/2583309/7fd52f8a-b9cf-11e3-8052-b4f908fd5209.png)

## desktop
![](https://cloud.githubusercontent.com/assets/3761968/2583348/1b260572-b9d0-11e3-8f3e-3004dbbc63c9.png)

## player
![](https://cloud.githubusercontent.com/assets/3761968/2583312/84462bf0-b9cf-11e3-8b00-96fb3fc1610e.png)