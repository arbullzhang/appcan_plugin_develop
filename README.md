# appcan_plugin_develop
AppCan插件开发环境

这是开发AppCan插件的工程。这个工程里面目前包含一个从相册和相机中获取照片的例子。

先介绍几个目录   
1. PluginSource：存放插件的功能文件，开发的时候，只需要在这个目录下修改即可；      
2. Product：工程target生成存放的路径；     
3. DynamicLibraryProject：生成AppCanIDE所需要的动态库（uexPluginName.dylib）；       
4. StaticLibraryProject：生成AppCan云打包平台所需要的静态库（libuexPluginName.a）；        
5. PluginDebugProject：调试插件的工程；        
6. AppCanEngine:引擎工程，开始开发插件时先运行AppCanEngine.xcodeproj，生成静态库libAppCanEngine.a。        
   AppCanEngineDebugProject.xcodeproj基于PluginSource代码对AppCanEngine进行源码调试学习。       


开发新功能插件的时候，只需要做以下几步：      
1. 把PluginSource目录下的EUExPluginName类名中的PluginName替换为新插件的名字；       
2. 把DynamicLibraryProject和StaticLibraryProject工程的target的Product Name修改新插件的名字，只需替换其中的PluginName；       
3. 把Product目录下的info.xml和plugin.xml中的PluginName替换为新插件名字。        

关于插件在AppCanIDE的调试，把DynamicLibraryProject生成的uexPluginName.dylib，和info.xml、plugin.xml压缩成一个zip包，然后传到IDE里面即可。
