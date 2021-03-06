# Kotlin 1.1 Beta 2 重点更新

## 1 协程改包名风波

说真的，看到这个标题的时候我还挺兴奋，离 release 又近了一步。不过，看了这篇文章的时候，我就觉得也是醉醉的。发生了啥呢？

原来，协程相关的依赖统统被标记为 experimental 了，以前叫：

```kotlin
 package kotlin.coroutines 
```
现在呢？

```kotlin
 package kotlin.coroutines.experimental 
```

这意味着啥？意味着我们在这次更新之后，还得把原来的协程代码的包重新导入一遍，另外，如果你想使用协程，那么你还需要在配置当中呢启用它，例如 gradle 配置需要加入：

```gradle
 kotlin { 
     experimental { 
         coroutines 'enable' 
     } 
 } 
```

你在升级所有的依赖的时候，确保它是兼容 1.1.0-beta-38 的，这一点很重要，不然等着报错吧！

话说，为啥要这么搞呢？按照官方的说法就是，协程这个特性目前已经实现的非常不错了，内置 API 非常少，灵活扩展性也强，不过他们觉得这个东西还有很大的潜力，也不能就这样作为最终版本给大家放出来，而作为实验特性交给大家使用呢，更多地还是希望大家能提提意见啥的。嗯，说实在的，协程这个特性真不是个小特性。

## 2 兼容 1.0

话说，1.1 的编译器终于声称兼容 1.0 的源码了，这表明我们再也不用搞两个 IntelliJ 分别装 1.0 稳定版的插件和 1.1 Beta 版的插件了。

是的，就算你不用 1.1 的特性，你装 1.1 的插件，用 1.1 的编译器，写 1.0 的代码毫无压力！！

什么？你问我试了没？当然，我一直用最新的插件，折腾地挺苦的 T T，劝诸君还是装稳定版吧，吃螃蟹要做好心理准备~！

## 3 小结

浏览了一下 1.1Beta 2 的主要特性，其实就是改改包名，修几个小 Bug，大的改动基本没有了。如果大家想要尽早上手 1.1 的特性，那么就从现在开始吧~

