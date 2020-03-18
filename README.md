# MarqueeRecyclerView
自动无限滚动跑马灯、支持横竖屏滚动、支持开关控制、一键接入，无需更多操作

### demo示例
![](https://github.com/zhuozp/MarqueeRecyclerView/blob/master/images/device-2020-03-18-192611.gif)

### 接入步骤

1. 在根目录root的build.gradle添加
```
allprojects {
    repositories {
        google()
        jcenter()

        maven { url 'https://jitpack.io' }
    }
}
```

2. 在相关模块添加依赖
```
implementation 'com.github.zhuozp:MarqueeRecyclerView:v1.0.1'
```

3. 调用,可以使用自定义的MarqueeRecyclerView，也可以直接使用默认的recyclerview，默认的话不会自动滚动，但手动滑动的时候仍然支持循环展示，LooperLayoutManager的实现支持了循环滚动功能
```
recyclerView = findViewById(R.id.recyclerview);
recyclerView.setAutoRun(true);
recyclerView.setAdapter(new SimpleAdapter());
LooperLayoutManager layoutManager = new LooperLayoutManager();
layoutManager.setLooperEnable(true);
recyclerView.setLayoutManager(layoutManager);
recyclerView.start();
```
