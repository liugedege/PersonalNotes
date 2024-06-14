# ABP学习

## DDD分层

- 领域层
- 基础设施层
- 应用层
- 表示层

## 实体

- 充血模型 贫血模型

## 值对象

值对象和实体恰好相反，它不需要唯一标识，并且它不可以被改变

## 模块

通用模块和业务模块在代码组织上没有任何区别，按模块用途划分，继承ABPModule

- 通用模块
- 业务模块
- 插件式模块  不需要在解决方案中进行以来，作为插件加载进来

**模块开发：**

1. 打包  将一个标准的ABP模块打包成Nuget包

   将一个模块打包成多个nuget包

2. 引用  将nuget包引用到解决方案中

   在解决方案 .sln 文件路径下，使用cmd命令  `abp add-module [模块名称]`    abp add-module Volo.Docs

开发流程：



### DependsOn的作用

- 控制加载顺序

## 权限模块

## Abp Cli

- abp new 
- abp add-module [模块名称]  
- -u none 配置UI类型  none 表示不用UI

## 修改默认表前缀

- EntityFrameworkCore项目中DbContextFactory .cs文件中，CreateDbContext方法中增加 `AbpCommonDbProperties.DbTablePrefix = "Chaint_"` 

- 在API程序的入口方法处也需要增加`AbpCommonDbProperties.DbTablePrefix = "Chaint_"`

## 创建项目脚手架

1. `Microsoft.TemplateEngine.Authoring.Templates`模板包创建模板，`dotnet new templatepack --output "FeiAbpTemplate"`，创建.template.config文件夹，在文件加下创建template.json文件     

   FeiAbpTemplate

   ​        - FeiAbpTemplate.csproj

   ​        - Content

   ​           - 模板内容

   ​              - 解决方案路径（以及其他要打包的内容文件夹）  （要打包的内容，和.template.config文件夹同路径）

   ​              - .template.config  一个配置文件对应一个项目模板 **注意这个文件夹名称是以 . 符号开始的**

   ​                 template.json

   ```json
   {
     "$schema": "http://json.schemastore.org/template",
     "author": "Me",
     "classifications": [ "Common", "Console" ],
     "identity": "ExampleTemplate.AsyncProject",
     "name": "Example templates: async project",
     "shortName": "consoleasync",
     "sourceName":"ExampleTemplate.AsyncProject",
     "tags": {
       "language": "C#",
       "type": "project"
     }
   }
   ```

2. 打包上传  dotnet pack  通过nuget package explorer上传到nuget服务器即可

3. 安装包  `dotnet new install [nuget包名称] `  --force(**强制搜索10.113.0.30服务器， 10.113.0.30这个服务器必须加上这个**)  

4. 使用模板   `dotnet new [模板名称]--name [实际项目名称]` 

5. 微软教程地址 [为 dotnet new 创建模板包 - .NET | Microsoft Learn](https://learn.microsoft.com/zh-cn/dotnet/core/tutorials/cli-templates-create-template-package?pivots=dotnet-8-0)

4. 参考教程 [asp.net core 将整个解决方案打包，做成脚手架，可直接安装使用 - 黄明辉 - 博客园 (cnblogs.com)](https://www.cnblogs.com/fei686868/p/17722056.html)
