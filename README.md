2017-12-11因为项目需要,又对插件进行了修改，修正了android6+权限带来的问题以及添加package.json文件解决cordova高版本导致无法安装的问题



# 安装方式如下  

D:\liangzhenghui\testcordova>cordova plugin add https://github.com/liangzhenghui/cordova-qdc-baidu-location --variable API_KEY="你的百度key"



比如我的key 是ByQozv2BPSjoERC0RO7QS6qYp3pGNMGT 你可以拿来试下。



如果安装出现git相关问题就配置git环境再安装。


或者直接将项目下载到本地之后解压然后安装 
cordova plugin add D:\cordovademo\cordova-qdc-baidu-location-master --variable API_KEY="你的百度key"


D:\cordovademo\cordova-qdc-baidu-location-master是我插件所在在的根目录

# 调用方式
```javascript
baidu_location.getCurrentPosition(function(data){
                console.log("success");
                alert(JSON.stringify(data));
               console.log(JSON.stringify(data));
  }, function(data){
      console.log("fail");
      console.log(data);
      alert(JSON.stringify(data));
  });
```
  成功返回json对象如下
```javascript
                time : 2017-12-11 17:15:55
                error code : 161
                latitude : 23.13229
                lontitude : 113.377591
                radius : 40.0
                addr : null
                operationers : 0
                describe : 网络定位成功
  ```    
失败返回字符串如下
                "定位权限没开启,功能没法使用"
# 版本
1.0.0版本适合在gradle3以下使用
近期发现gradle3以后,项目的路径调整了,所以升级到2.0.0版本才解决了由于androidstudio升级后带来的问题。
ionic3适用2.0.0版本
部分人反映在ionic3下安装会出错,找到2种解决方式：
方式1：npm降下来到4或者3，
方式2：删掉ionic3中package-lock.json文件, 删掉node_modules目录
# 打赏可以点击我头像支付
           
                
                
