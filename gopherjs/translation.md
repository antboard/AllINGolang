# 程序间翻译

### 追溯

其实，最初的所有语言都是翻译成汇编语言的。因为汇编语言和机器指令一一对应，所以大家不把他看做语言。
就忽略了语言之间翻译这个方向了。

后来， 就很多很多年了。中间语言都没有这个需求。各种鄙视链。

直到有了 js， 并且这个胶水还发展的不错的时候。和 js 名称相近的 java 被 google 提出来一个方法，
GWT 这个项目用来翻译。但是翻译出来的直接不可读。我是用过一段的。特别难用。比直接写 js 都恶心。
我就放弃了。后来谷歌也放弃了。

gopherjs， 我查了一下历史，非常早， 感觉和 gwt 差不多一个时代。我一直忙于服务端开发，
等 golang 完善， 根本没注意到这个东西。然后就是 wasm，是我关注的点。 asm.js 这个东西我试验失败之后，
就一直在等 golang 的版本，等 golang 发布之后，又在等他稳定。终于比较稳定了。
我也自己写了自己可用的验证框架。感觉不错。

回到这个原始的方式， 也是迫不得已。最近想 all in golang， 那总要给大家找个理由，说明 golang 的靠谱。
n 年之前， 有一个移动端的 golang 直接调用底层显卡来刷屏幕的例程。很多原生的东西对接不起来。都被忘记了。
那 js 得各种 native 可能就是一个突破口了。如果我把 golang 编译成 js，
把 js 的那一堆 native 复用过来。不就可以了么？

### 惊叹

我看到 gopherjs 封装的时候， 看着和 wasm 的封装如此一致。让我想起很久以前网上在争论 wasm 的实现方式的时候，
很多人不太喜欢这种方式。 但是估计有特殊的权衡。或者是开发成本， 这个 gopherjs 的作者，参与了 wasm 的开发过程。
相同的方法，就被用到了 wasm 上。 这对工程来说。不是坏事。至少一套代码可以更多的使用了。

我觉得 golang-wasm 是靠谱的， golang-js 也是靠谱的。一个人做的啊。但是因为需求量少，作者也基本不更新了。

### 试验

总要试试一个 hello world 吧。 没有开始，就没法体会作者的思路。 
golang 的编译器要求1.12， 而我现在是1.14， 差一点就放弃的时候， 我看见了一个 env 环境变量，
可以给 gopherjs 指定 goroot， 这群家伙很有底蕴的，这种骚操作，从 linux 系统很久前就在使用。
年轻的小盆友们。不太知道。

然后我下载了最新的1.12，然后指定 goroot， 不错。 编译成功了。看了一下编译出来的 js，没有倾向于人可读的 js，
而是倾向于高性能的 js， 通过一些特殊描述，让 js 解释器可以更低成本的去理解编译运行， 性能有些。可能用 golang 的人，
都是这样吧，勤俭节约。

当然， map 文件现在还没用起来。无所谓，不重要， js 文件还是能看懂的。作为一个备份。因为安卓手机并没有锁死 wasm 这条路。只有 ios 不支持。

### 多端
有了 gopherjs ， 就可以构建出可以编译成手机应用的可能。至少不是从0开始了。 也是一件很好玩的事情。
你想啊， react-native ，vue，还有美团之类出的多端框架， 以及小程序， 都是顶级互联网公司在做的事情， 
你可以把他们的抄过来。搞一个 golang 版本的， 就算是 demo，也是一件特么有意义的事情。

地基有了。后面就慢慢玩起来。

golang 是一个高手友好的语言，你来了，可能就不想走了。
可能这些高手经验的开源， 就是一场巨大的风暴。

我就是那只蝴蝶，为大家先跳一只舞蹈。

