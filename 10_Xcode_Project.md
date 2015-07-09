# Xcode 工程

为了避免文件杂乱，物理文件应该保持和 Xcode 项目文件同步。Xcode创建的任何组（group）都必须在文件系统有相应的映射。 为了更清晰，代码不仅应该按照类型进行分组，也可以根据功能进行分组。

如果可以的话，尽可能一直打开 target Build Settings 中 “Treat Warnings as Errors” 以及一些[额外的警告][Xcode-project_1]。如果你需要忽略指定的警告,使用 [Clang 的编译特性][Xcode-project_2] 。

[Xcode-project_1]:http://boredzo.org/blog/archives/2009-11-07/warnings
[Xcode-project_2]:http://clang.llvm.org/docs/UsersManual.html#controlling-diagnostics-via-pragmas

**目录结构参考**

```
> [ProjectName]
    AppDelegate.h               程序主代理头文件
    AppDelegate.m               程序主代理实现文件
    Main.storyboard             程序主Storyboard文件（如果使用Xib，Xib与对应的ViewController/View放在统一目录）
    > ViewControllers           视图控制器
    > Views                     自定义视图
    > Models                    模型类
    > Extensions                自定义拓展类
    > Utils                     工具类
    > Services                  服务类（如网络封装、分享功能封装等）
    > Pods                      第三方库（即使使用CocoaPods，也可能仍然会使用到CocoaPods无法管理的第三方库）
    > [Supporting Files]
        Images.xcassets 
        > Files                 项目中使用到的文件（如配置文件、本地页面、SSL证书等）
        > Images                不适合用 Image Sets 管理的图片（如全屏背景图等）
```
