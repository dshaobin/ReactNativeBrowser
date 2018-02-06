# React Native Browser
  
 实现一套基于React Native为基础的类似浏览器功能的模块，使App可以很容易集成进该功能，达到和Web一样的效果，当后端页面改动了前端自动显示最新的内容。跟离线推送比，有啥优势和劣势呢？    

  优势    
  1. 改动时时生效
  2. 维护成本较低      
  3. 跟Web一致的流程

  劣势
  1. 加载时页面有loading过程
  2. cache管理更高的成本

## Web 历史回顾  

第一个 Web Server 是 1990 年 Tim Berners-Lee 在 CERN 写出来的，那个时候已有一个浏览器，但是那浏览器是命令行的浏览器（ line by line 的 browser），那种浏览器是只有非常少数的人可以用的。到了 1992 年的时候，另外一个工程师写出来这个浏览器 Erwise，图形界面基于 X-window 的。到了 1993 年的时候，有了 Mosaic 后来演变成了 Netscape。
实际上 Internet 并不新，60 年代就已经有 Internet；超文本也不新，80 年代就已经有了超文本，但为什么一直到了 1994 年（那年全球也只有 3000 个网站），Web 才真正成为一个现象级的工具？因为在这之前没有这样的应用。像Browser 就是这样的应用，所以说我们看 1993 年有了 Mosaic，1994 年就有了 Amazon。    
当我们回来看 Web 本身，实际上 Web 是因特网（ Internet） 的一个应用，但现在在大众媒体上，可能大家不会区别。大家都说“互联网”，大家谈互联网的时候，通常实际上在谈万维网（Web）。那么底层的从数据链路层，到 IP 层，到传输层到表现层，大家在日常的媒体中是不会看到这些区别的，Web 只是最上面的这么一些协议：HTTP，HTML，URI。这三个协议构成了 Web的基础。
Web的目标：互联、开放和自由

从1993年2018年，Web经历了25年的发展和演化, 从刚开始的只有文字，接着随之而来的图文结合，一直到后来的大量的流媒体，知道现在的大量基于Web页面交互的网游, Web一直持续的发展到了现在的无所不在。

## 为什么Web可以成功
Web是非常成功的。但是为什么会成功呢？
1. 跟他的目标密不可分，开发、自由、互联，一直是人们追求的目标
2. 基金会的运作方式，使得Web不被某些利益集团把持
3. PC电脑的处理能力稳步提升，用户体验与客户端相差不大
4. 用户操作方式没有发生很大的变化，鼠标和键盘，给了Web标准化足够的时间来推进项目
5. 人类持续受教育水平在提高（尤其是我党带领下的中国） 
7. 对高效率的追求

## 移动互联网时代的Web
2007年6月 第一代 iPhone 发售，开辟了新的智能手机市场。

2008年7月 iOS App Store 上线，10月 Android Market 上线，标志着新的移动互联网到来。

过去的 10年，发达国家和以中国为代表的部分发展中国家，共同推进了移动互联网的发展。移动互联网已经改变了和正在改变中国的各行各业，从出行、旅游、健身、广告、新闻、金融到培训、移民行业。相似的发展轨迹正在新兴国家上演，移动出海已经是国内创业者重要的选择。

从2007年，以iphone为例子看一下，手机的发展和硬件变化

2007年1月9日 iphone第一代    
硬件：
1. 摄像头
2. 存储
3. 多点触屏
4. 音频

2007年6月29日 iphone 2G    
硬件：
1. 摄像头
2. 存储
3. 多点触屏
4. 音频

2008年7月11日 iphone 3G    

新增硬件：
1. GPS

2009年6月9日  iPhone 3GS    

新增硬件
1. 蓝牙
2. WIFI
3. 电子罗盘
4. 重力感应器
5. 加速传感器
6. 光线传感器
7. 距离传感器

2010年6月7日 iphone 4

新增硬件：
1. 高分屏

2011年10月4日 iphone 4s
新增硬件：
1. 无

2012年9月 iphone 5 
新增硬件：
1. 无

2013年9月10日 iphone 5s  
新增硬件：
1. 无

2014年9月10日 iphone 6 和 iphone 6 plus
新增硬件：
1. NFC
2. 指纹识别传感器
3. iBeacon
4. 气压计
5. 三轴陀螺仪

2015年9月10日 iphone 6s 和 iphone 6s plus
新增硬件：
1. 无

2017年3月21日 iphone 7 和 iphone 7 plus

新增硬件：
1. 无

2017年9月13日 iphone 8 和 iphone 8 plus
新增硬件：
1. 无

2017年9月13日 iphone x
新增硬件：
1. FaceID
2. AR

硬件支持的能力从 4个到最新的 iphone x版本 到20个，增加了16个，Web的发展标准化的推进十分缓慢，更不用说各个浏览器厂商的支持情况，厂商想要为用户提供更优秀的体验使用App是明智的选择，哪怕会有更大的成本投入。

## App Vs Web

在PC时代，随着电脑性能不断的提升，并且没有额外的硬件加入进来，只有鼠标、键盘、音频，10年前也是这样，这给了Web标准化足够的时间，并且随着PC端性能的提升，浏览器上几乎能满足大部分需求，为了降低成本越来越多的厂商使用浏览器作为客户端来开发应用, Web就成为了趋势。

随着移动互联网的兴起，前期以App主导很容易解释，刚开始手机性能不够好，随着移动互联网的发展将近10年过去了，手机性能也一次次提高甚至超过了普通的PC，但是个大厂商还是以App为主，虽然Web标准在稳步推进，浏览器也快速迭代，但是还是无法满足大部分厂商的需求，主要原因是这段时间手机的硬件设备更新太快了，Android 和 IOS 阵营也没有统一标准，导致Web标准远远滞后于硬件的更新，更不用说个个浏览器厂商的实现了，在移动互联网世代Web逐渐沦为了导流工具，很多场景甚至连整套业务都无法实现。毫无悬念 如果 手机以这样快的速度更新 App依然是主导，Web的市场可能会越来越小。

但是Web的开发方式比其他的开发方式效率要高的多，尤其对界面的开发。另外Web不需要升级应用系统就可以更新。这对目前的应用来说非常重要，因为发布一个新版本的App是一个很繁琐的过程。

在移动互联网发展的过程中出现了混合方案，目的是既可以利用Web的开发优势又可以使用App的大多数能力和性能。前期方案以 cordova 最著名的 Html + Js + App的形式的开发架构，慢慢的这种方案被大家抛弃了，原因是可以使用App的能力，但是WebView的性能太差。后期出现了以React Native最为著名的混合方案，这个方案的核心是使用JS开发的组件，翻译成Native的组件，使Web开发
优势，同时可以利用Native的能力，这种方案在性能上比Webview要高很多。好像是解决了开发、性能、能力的问题，但是这种方式并不能代表Web，原因是他跟Web的目标不符合，他并不满足开放、自由、互联。

这样的情况下有没有可能在浏览器上实现一个解析器，这个解析器只是HTML的子集，在该解析器中把HTML的元素解析成Native的组件同时保持高性能，也可以使用Native的全部能力，因为是HTML的子集在普通的浏览器上也是可以展示，对于浏览器的不支持的能力做降级处理。加入搜索引擎拿到了这个页面也是可以解析的因为这就是一个HTML页面。同时里面的链接也是可以跳转的，跟现有的标准兼容，随着社区的发展不断完善该解析器的能力。

这个方案跟现有的基于React Native的三端合一的方案有什么不同呢？现在一般三端合一的方案大多数是基于打包工具，并没有解决Web面临的问题。

这个方案跟 cordova 有啥不同呢？该方案并没有使用WebView渲染，性能要优于 cordova。

有没有实现思路：
1. 实现一套解析工具，基于React Native开发一套Web组件（div、span、a、iframe等等）
2. 实现一套解析工具，重构React Native组件以Web标准的方式
3. 从开始实现

貌似方案1的成本是相对最低的。

稍后开发一个简单的Demo然后逐步完善直到达到最终的效果
