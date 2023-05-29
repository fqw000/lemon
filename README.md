# lemon  
>
> 测试lemon使用，过度依赖现有运行规则，随时会失效，不保证维护。 
> 

**鉴于Clash的完善，目前对各平台的良好支持，一个配置全平台通用的便利让我不的不考虑全面转战Clash**  
    对个人而言：折腾 > 使用 。


### 一些说明

- 通过提取客户端v2rayNG的订阅链接通过shortcuts自动更新到lemon.site
- extract-lemon-list.yml中没有加入异常处理机制，为确保运行正常，务必确保lemon.site文件内容为单网址，shortcuts里有处理自动提交时可忽略该问题。
- 触发extract-lemon-list.yml
     - 每3个小时更新一次  
     - 读取lemon.site内的订阅链接网址对应的内容
     - 将网址内容同步至lemon.sub，解决v2ray订阅
     - 对lemon.sub进行解码同步至lemon.list，解决loon订阅
     - 修改lemon.site读取的链接网址为客户端提供的Clash的订阅网址，并读取clash订阅到lemon.yaml
     - 提取clash订阅内的proxies内容到lemonnode.yaml
     - 使用lemonlite.yaml保存clash订阅内的proxies内容，并与lemonbanner.yaml合并到lemonliste.yaml形成一个完整的自定义订阅内容
     - 注：lemonbanner.yaml内容为代理集和规则集合。
-  不是最优解，只是能用。

## 关于github action的坑，萌新关注。
   - 涉及到文件提交等操作，需要在repo设置里代开action的读写权限,否则会面临提价失败。即使你是owner
   - > setting-Actions-General-workflow permissions-打开read and write permissions
  
    
  ##   ~~lemonlite.yaml~~ 
   这里使用的是黑名单机制，gfw列表走代理，其余DIRECT,只是对spotify和telegram单独分流。
   没有涉及任何去广告和script操作，去广告交给了AdgurandHome和adbyby。  
  ## lemon-usr.yaml
   舍弃了~~lemonlite.yaml~~.使用了代理集和规则集的引用，只是使用了extract-lemon-list.yml生成的lemonnode.yaml代理集文件。舍弃了没有代理集时的其他繁琐的实现操作。
    
 
