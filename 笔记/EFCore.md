# EFCore

## 安装包

- Tool
- Design
- SqlServer

## 基本指令

- add-migration Initial   生成迁移的代码   Initial 生成cs文件名称
- update-database  执行迁移的代码 以CodeFirst的方式生成表到数据库中

## CodeFirst 数据库迁移

```
var context = new DbContext();  
context.Database.EnsureDeleted();
context.Database.Migrate();

context.Database.EnsureCreated();   // 如果数据库不存在 则创建数据库
EF模块增加一个HostedService来进行数据库自动迁移

```

 
