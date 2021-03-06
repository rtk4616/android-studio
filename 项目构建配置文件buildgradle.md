# 项目构建配置文件build.gradle

Project:build.gradle是用来配置项目的构建任务.
默认的build.gradle内容如下:

```
//项目构建文件，你可以到各子项目/模块添加常用的配置选项.

buildscript {

//Android插件从这个仓库中下载

repositories {

jcenter() // 依赖仓库源的别名,兼容maven的远程中央仓库

}

//依赖

dependencies {

// android gradle插件

classpath 'com.android.tools.build:gradle:2.2.0-alpha1'

// 提示:

//请不要在此处添加应用程序依赖;它们应该在单个Module(模块)build.gradle文件中添加

//这里添加的应该只是Project的依赖

}

}

//此处配置Project中默认的仓库源,包括每个module的依赖

//这样每个module就不用单独配置仓库了

allprojects {

 repositories {

 jcenter()

 }

}

// 打包前执行clean任务

// 任务类型是 Delete

// clean任务就是删除项目根目录下的build目录(build为输出目录)

task clean(type: Delete) {

 delete rootProject.buildDir

}

```

buildscript中的repositories是指定Android插件的仓库源.

allprojects中的repositories是指定整个Project中默认的仓库源.

### 在Project Structure中设置

我们可以在Project Structure —> Project中设置Gradle和Android插件的版本,以及Android插件和默认第三方库的仓库源.

Project Structure和Project build.gradle对应的关系:
