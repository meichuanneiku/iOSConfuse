# iOSConfuse

## 1.目录结构

```
- confuseAndBuild.sh # 混淆编译脚本
- [Example]     # 示例项目
- [Framework]   # 编译以后生成的通用framework
- [ConfuseFW]   # 框架源码
- ConfuseFW.xcodeproj
- ConfuseDemo.xcworkspace
- README.md
```

## 2.工程Scheme使用方法
- **DemoTest**   
编译Debug环境framework：只会编译当前设备对应架构，仅供测试用。
- **safeConfuseAndBuild**     
编译Release环境通用framework：编译时混淆代码，编译完去除混淆。
- **safeConfuse**     
安全混淆：备份源文件，然后混淆目标代码。
- **unconfuse**   
去除混淆：将备份源文件恢复。
- **Example**     
示例项目：框架使用Demo。

## 3. safeConfuseAndBuild.sh
修改CONFUSE_PREFIX的值为要被混淆的文件的前缀；例如：PrivateXXXXXX.swift，那CONFUSE_PREFIX=Private
直接在终端cd到confuseAndBuild.sh的目录，然后运行sh confuseAndBuild.sh -c 即可
这是iOS代码混淆及编译的自动化脚本，支持swift、m、c、cpp和h文件类型的混淆，使用编译时混淆的策略，不影响源码阅读，可通过函数实现安全混淆、去混淆、混淆再编译。
