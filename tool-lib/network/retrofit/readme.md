Retrofit 源码解析
====================================
> 本文为 [Android 开源项目源码解析](https://github.com/android-cn/android-open-project-analysis) 中 Retrofit 部分  
> 项目地址：[Retrofit](https://github.com/square/retrofit)，分析的版本：[2f4caa6](https://github.com/square/retrofit/tree/2f4caa6f5df8e7f47a881266bbfc723f537b0b47)，Demo 地址：[Retrofit Demo](https://github.com/aosp-exchange-group/android-open-project-demo/tree/master/retrofit-demo-guogavin)    
> 分析者：[guoGavin](https://github.com/guoGavin)，校对者：[lightSky](https://github.com/lightSky)，校对状态：未完成 


###1. 功能介绍  
####1.1. Retrofit
Retrofit是由Square在github上牵头开源开发的网络访问框架，使用方便，速度快，安全稳定，定制灵活。
> 官方介绍为：Type-safe REST client for Android and Java by Square, Inc.