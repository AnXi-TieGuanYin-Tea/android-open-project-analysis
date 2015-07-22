Retrofit 源码解析
====================================
> 本文为 [Android 开源项目源码解析](https://github.com/android-cn/android-open-project-analysis) 中 Retrofit 部分  
> 项目地址：[Retrofit](https://github.com/square/retrofit)，分析的版本：[2f4caa6](https://github.com/square/retrofit/tree/2f4caa6f5df8e7f47a881266bbfc723f537b0b47)，Demo 地址：[Retrofit Demo](https://github.com/aosp-exchange-group/android-open-project-demo/tree/master/retrofit-demo-guogavin)    
> 分析者：[guoGavin](https://github.com/guoGavin)，校对者：[lightSky](https://github.com/lightSky)，校对状态：未完成 


###1. 功能介绍  
####1.1. Retrofit
Retrofit是由Square在github上牵头开源开发的网络访问框架，使用方便，速度快，安全稳定，定制灵活。
> 官方介绍为：Type-safe REST client for Android and Java by Square, Inc.

与很多框架不同的是，Retrofit使用annotations来标记当前请求的方式，设置相对url，设置访问参数等，比如@GET表示当前请求为get方式等。在Retrofit中可以设置的方式有：
>GET，POST，PUT，DELETE，当然还有HEAD用来设置request的headers等。

Retrofit框架定制也很灵活，提供了比较多的基础类用于开发者进行自定义，比如：
>1.可以实现Converter接口，来自定义数据转换器。   
>2.可以实现ErrorHandler接口，来自定义错误处理器，在异常抛出框架层之前（比如到达你的回调函数之前），给你一个自定义的机会。   
>3.可以RequestInterceptor对象，在请求发出去之前，拦截一次，给一个统一处理的机会，比如添加header。   
>4.可以设置RestAdapter.LogLevel，来设置是否在logcat上打印出来相关的log信息。

Retrofi在返回值和同步异步处理上也很棒：
>1.可以根据Gson（默认数据转换器是GsonConverter）框架，返回你自定义的对象。   
>2.可以同步执行，也可以异步执行。   
>3.也可以直接返回Response。   
>4.也支持RxJava，返回Observable。   
>5.如果你自定义了一个数据转换器，那么你想返回什么都是可以的，比如String？IO流？等。

以上就是Retrofit的主要功能，也可以完成我们所有的网络需求。