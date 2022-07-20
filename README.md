# zun语生成器
作为最近入坑东方的新人，我看到在B站有很多人经常模仿东方官方作者ZUN在游戏里的文档风格，并且经常登上热搜（笑）

能不能用一种系统性的方式生成这种“ZUN语”呢？我在想。

于是想法就是这样：我来收集一个包含ZUN语的数据集（目前仅限中文，翻译全部取自[THBwiki](https://thwiki.cc/)），然后在这上面训练一个可以生成ZUN语的机器学习模型就可以啦！

# 数据细节
每条数据包含两个主要部分：一个是输入：形式是“（类型）：（内容）”，以用来提示模型；另一个则是输出。

例：

"音乐：比赤色更红的梦"

"标题画面的主题曲。\n既然是东方，试一下做成和风的。呀，真是的。\n游戏好像不是和风的说(^^;\n不像是ＳＴＧ的曲子。\n说起来，标题画面需要曲子吗（笑）？"

数据集预计会有HuggingFace数据集和普通的csv，json数据文件三种形式~

# 模型细节
由于我们希望从一个给定的主题进行生成（也就是说用几个字作为prompt进行引导），所以任务是conditional language modeling（conditional LM），当前最优的方法是encoder-decoder Transformer-based预训练模型

由于数据是中文的，所以我们要找一个中文的seq2seq模型：我选择用

# 模型性能以及结果展示

# 如何使用模型？

# 如何重新训练你自己的模型？

# 贡献
repo主是一名学生，所以这个项目肯定是断断续续的，收集到一定量的时候就重新训练一个模型然后发布出来~

所以呢，如果你觉得我正在做的事情是有意思的，有意义的，并且你也想参与其中，请不要犹豫：

如果看到了模型或者数据里的问题，请发送issue来指出我的错误，我会第一时间修改！

如果有关于模型或数据有改进的意见，或者有很好的额外数据的来源，请发送issue来告诉我，我很乐意进行改进！

当然了，如果你想要pull request来直接帮助我的工作...非常感谢，tasukarimasu

# 结语
东方自很久以前就是一个优秀的ACGN游戏同人社区了，除了官作之外，铺天盖地的二创：STG或其它游戏，动画，音乐，动漫，插图，MMD，油库里，鬼畜，其他二创视频...应有尽有，私以为这种社区驱动的文化与开源软件宗旨不谋而合。

但是在几个月之前看到的一个[B站视频](https://www.bilibili.com/video/BV1fa411r7xM)开拓了我的想法：东方的社区文化是欢迎任何形式的创作的——因此这吸引我来做一点自己的工作，

让我们一起来建设更多样的东方社区吧！
