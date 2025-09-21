# 计学组4.0网站构建指南README

计学组网站准备采用mkdocs-material构建文档,采用GitHub提供文件存储和页面发布,所有内容使用md格式书写，下面是步骤和格式规范

# 步骤
### STEP1

进入 [我的GitHub主页](https://github.com/weiyihong007) 并点击左侧的的Follow按钮(后续需要设置权限)

### STEP2

fork [计学组4.0网站](https://github.com/weiyihong007/xjtu-cshonor) 项目到自己的GitHub账号下

### STEP3

clone 自己fork的项目到本地并进入目录
clone [xjtu-cshonor-utils](https://github.com/weiyihong007/xjtu-cshonor-utils) 项目到本地并放置在step2之中的项目的/docs/utils/目录下

### STEP4

在conda环境中安装依赖 `pip install mkdocs-material` 并运行 `mkdocs serve` 启动本地服务器

### STEP5

编写你的部分并结合在浏览器中访问 `http://127.0.0.1:8000` 即可查看本地文档直至完成

### STEP6

上传并更新到你的github仓库并向[计学组4.0网站](https://github.com/weiyihong007/xjtu-cshonor)发起Pull Request,注意不要上传经过mkdocs build的文件,仅上传docs以及.yml文件并删除utils目录下的所有内容。

# 格式规范

### 1、目标
网站组的核心工作并非编写具体的资料而是负责整合前人的资料并提供初步的导览实现更好的访问

### 2、项目结构

mkdocs-material是帮助文档构建的框架, [这里](https://www.mkdocs.org/getting-started/) 有详细的文档说明(所有md格式的高级功能也可以参考)
另外具体的资料文件使用独立的存储库进行放置,下载并放置在/docs/utils/目录下面

### 3、资料搜集(重要)

考虑到计试具有大规模的公共课程,搜集其它学辅编写的资料并集成是非常重要的，负责课内资料的同学需要将自己用过的以及觉得非常重要的资料(知识点,历年题目整理)等上传到xjtu-cshonor-utils项目中,并在网站中进行展示(可以放一些b站上面的视频)。
注意所有非文字资源(包括放置在utils之中的pdf,ppt,excel文件,推荐的视频链接等等)都必须使用lazy展开的选项卡进行展示以确保网站只加载文字.
具体实现方式:pdf格式的参考第4点,其它格式参考mkdocs-material的帮助文档进行实现.
如果是其它学辅的资料需要进行引用，引用统一在页面底部实现,下面是标准格式:

下面是高数上的复习资料 [^1]

注意除非不同学辅编写了同一类型的资料，否则不需要在正文中强调编写学辅,另外推荐同一类型的资料(比如真题,知识点梳理)仅保留你认为编写的最好的。
另外所有外置的链接都不要显示链接本身,使用超链接展示.

### 4、内嵌文件

内嵌文件是主要的文件提供形式,包括pdf,xlsx,ppt等文件,图片一般来说可以直接放置,比较大的采用展开模式

PDF 文档的摘要
```
??? note "PDF 文档的标题"
    <iframe loading="lazy" src="PDF 文档的绝对路径（从docs目录开始，如utils\XJTU-CSTE-Mentor-Group-main\竞赛\大学生算法竞赛入门.pdf）"></iframe>
```
这使用一个默认不展开的 note 包裹 pdf 文件。??? note 是 mkdocs 支持的语法，可以查看 MkDocs Material 文档。

注意 loading="lazy" 至关重要。这将懒加载文件，等到读者展开 note 时才会加载。否则较大的 pdf 会严重拖慢网站加载速度。

具体代码参考index.md中的链接

### 5、分工

mkdocs.yml文件列出一个基本的目录,按照你的分工模块设计文件夹以及编写markdown文件,注意！不要删除mkdocs.yml文件的原始结构,可以添加子文件夹
注意现有的xjtu-cshonor-utils之中的文件全部需要被提及到，另外对于一门课程尽量使用一整个markdown文件进行介绍并通过合适的分级标题进行组织

| 人员 | 分工 | 要求 |
| --- | --- | --- |
| 薛岚轩 | 课内资料-大二 | 负责大二的课程(添加所有你认为重要的资料) |
| 李宛辰 | 课内资料-大一 | 负责大一的课程(添加所有你认为重要的资料) |
| 邓健豪 | 课内资料-大三+大四 | 负责大三+大四的课程(添加所有你认为重要的资料) |
| 匡巍嵩 | 研讨班+杂项 | 整理xjtu-cshonor-utils中的杂项文件,设计目录并添加介绍 |
| 刘远浩 | 升学+课内资料-体育+选修 | 升学资料需要额外补充,选修课推荐目录需要放一下 |
| 肖宇晨 | 竞赛+科研 | 尽可能列出所有竞赛并给每个竞赛写一段介绍(每个竞赛使用独立的.md文件),对于科研需要保持中立的态度 |

### 6、其它格式要求
没有更多的格式要求，在本地显示正常的情况下按照你喜欢的格式编写, 确保用户能够快速找到他们想要的东西, [这里](https://www.mkdocs.org/getting-started/)有更多高级语法.

### 6、权限

如果使用git向xjtu-cshonor-utils项目批量添加PDF文件的时候,使用下面的账户和密码

account: weiyihong007
password: 见QQ群

[^1]: 由钱院学辅编写