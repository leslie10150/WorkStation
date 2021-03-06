
# WorkStation 队列工作站
[![](https://jitpack.io/v/kayoSun/WorkStation.svg)](https://jitpack.io/#kayoSun/WorkStation) ![](https://img.shields.io/badge/Support-androidx-red.svg) ![](https://img.shields.io/badge/Apache-License2.0-green.svg)

2019年了，开年一直想写一个任务队列，满足日常的任务调度，
![](https://upload-images.jianshu.io/upload_images/4717230-bb7fa3d8c701ef5e.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 1、为什么要写个队列
作为程序员，日常就是和产品妹妹“聊天”，但是聊天是美好的，内容是残酷的！-！
产品妹妹：“程序员小哥哥，我这里有个小需求你给看下呗！”
我：“嗯”
产品妹妹：“是这样的，我这里有十张图片需要上传，上传的时候 只能是第一张传完了，在传第二张，依次，不能打乱顺序，你看看。。。”
我：（当场喷血。。。）

日常开发中，这样的实例、这样的使用场景还是有很多的，
so...
我就实现了一个这样的列队。。。

### 2、我的队列能够干什么
你可以实现
(1)并行任务，就是多个任务可以一起进行
![](https://upload-images.jianshu.io/upload_images/4717230-6a0bb4a9e7e339ca.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
此时任务1和任务2是同时进行，与结果无关

(2)串行任务，就是任务根据一定的规律一个一个的进行
![WX20190113-212840.png](https://upload-images.jianshu.io/upload_images/4717230-b2c9de0adad55b47.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

(3)条件任务，就是先做哪几个任务，后做哪几个任务
![](https://upload-images.jianshu.io/upload_images/4717230-bdc87401e8d0a6b9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

主任务和从任务一起执行，当主从任务都执行完成以后，在执行次要任务，所有任务都可以有多个，其中只有一个主任务，每个主任务以下的都是此主任务的附属任务

(4)延迟任务，就是可以在多久后开始任务

![](https://upload-images.jianshu.io/upload_images/4717230-763b34ecba071cbf.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

此时SimpleTask会在1000毫秒之后开始执行

(5)主线转换，就是可以把任务结果在主线程中进行
![](https://upload-images.jianshu.io/upload_images/4717230-6b0e9cb41c5b5a91.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

此时当任务完成会，会将更新结果发送的主线程

是不是很强大，是不是很想用起来 ^~^ !

### 3、怎么用我的队列
第一步

```groovy

    repositories {
        maven { url "https://jitpack.io" }
    }


```

第二步

```groovy

    dependencies {
    	implementation 'com.github.kayoSun:WorkStation:lastversion'
    }


```

##  版本注意事项

| version | min sdk|note |
|--------------|---|------------------|
| 0.0.1        | 14 |  |
| 0.0.2        | 14 |  |
| 0.0.3        | 21 | support androidx |

完美，您可以进行的使用了

## 联系作者

欢迎提issue<br>


## License
```
Copyright 2018 Kayo

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```