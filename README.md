# jiayeapp --日志
加急： k3职员需要维护部门（维修部），否则派工选不到（lambda语法问题（inner join——>left join））

1.app与API如何交互
	如何调用API方法—整个流程
	例：http://171.105.64.149:18085/api/ServiceRequest/GetNewRequestModel?type=mainten

2.单据流程	装机等

tsc 
XSym
0021
8cbd85238d8fbeb66a0afc1d79bcd880
../typescript/bin/tsc

2018.7.7
1.报修推送销售负责人

2.批量建单（保养/校准）

3.产品档案 （注册码（很长400个字左右）写到备注）

4.处理单生成PDF报告单，推送到客户邮箱

2018.7.23 删除 node_modules 后安装 （npm install ） 提示：
node-pre-gyp ERR! Tried to download(404): https://fsevents-binaries.s3-us-west-2.amazonaws.com/v1.1.3/fse-v1.1.3-node-v64-darwin-x64.tar.gz 
node-pre-gyp ERR! Pre-built binaries not found for fsevents@1.1.3 and node@10.0.0 (node-v64 ABI, unknown) (falling back to source compile with node-gyp) 

2018-07-25. 操作完成后，记得清缓存，否则会报各种各样的错误。

2018-07-26 服务请求单 服务类型选择 移机 后 派工单 找不到（服务类型归类漏了）

Angularjs input 不可编辑 [readonly] ，注意，中括号必须要有，否则为readonly属性本身。

2018.08-13 . app查看仪器的整个流程情况，从合同到回款
		—服务请求单 录入合同信息。


2018-08-20 仪器安装完成后应用部 培训记录表单。培训完成后才能验收

2018-08-21 产品档案新增合同号必填字段。

ionic 冒泡事件：
<li ng-click="toPage()" >
<span ng-click="action.toPage('tab.user-detail');$event.stopPropagation();">
</span>
</li>

Ionic 禁用右滑返回：
this.navCtrl.swipeBackEnabled = false;  (全局设定)


Sysmex 纸质单编号 录入 处理单 ？ 待与黄工确认。

iOS 版本启动后白屏问题。debug

20180910
v1.0.2 安卓版修复装机单录入选择不了客户和仪器的问题
产品档案 取合同编号 同时带出保修年限, 并在此录入

20180912 — api后台网站 建立模式选择为 ： asp.net v4.0

20180913 —app解决header取不到值 导致验证失败的问题。
	  —新增装机单时，加入年华/佳业合同一起取，并判断是哪个帐套，以确定相应服务主体。

20180914 —加入联网判断/ 全局错误提示/ 极光消息推送（未完成）/
	 —装机单请求单录入 -合同号由通过客户ID和仪器ID改为由客户代码和仪器代码来搜索，并union 借出和投放选项，同时更新服务主体为年华或者佳业（有些合同是年华帐套录的）


20180920 -config.xml —    <engine name="android" spec="^7.0.0” />
改成	    <engine name="android" spec="^5.0.0” />

20180921
错误信息
Without `from` option PostCSS could generate wrong source map and will not find Browserslist config. Set it to CSS file path or to `undefined` to prevent this warning.
解决方法
在“/node_modules/@ionic/app-scripts/dist/sass.js”路径的“sass.js”文件，在postcssOptions参数中添加“from: undefined”。添加后效果如下：


	1	var postcssOptions = {  
	2	    from: undefined,  
	3	    to: path_1.basename(sassConfig.outFile),  
	4	    map: autoPrefixerMapOptions  
	5	};  
	6	

—20180925
sudo npm i ionic3-jpush --save
npm install --save @jiguang-ionic/jpush 


安装安卓版 出现 解析包错误—可能是 需要签名。 改为Android platform5.0.0 解决不了问题。—签名后也解决不了。
	—魅族flyme系统。 华为horno 

安装 ng2-signalr / Jquery  运行报错---找不到 jquery 类库

20181015.  App 权限设计：用户，角色组t_role，用户所属权限组t_role_user，所有权限命名 t_permission,角色拥有的权限t_role_permission；
	      数据隔离问题：分销售和应用；销售按区域可看自己负责的区域的客户（终端客户）；应用按照产品线划分可看范围（一线应用只能看自己负责的项目（不确定性太大）—是否精细到物料来划分数据域）（产品目录？）

20181018 集成百度地图，定位。

220181108 ionic cordova plugin add cordova-plugin-app-version. 
		  sudo npm install --save @ionic-native/app-version
npm install fundebug-javascript --save
sudo npm install --save @ionic-native/in-app-browser
sudo ionic cordova plugin add cordova-plugin-inappbrowser
sudo npm i @ionic-native/toast
sudo npm install --save @ionic-native/app-minimize

1、安装File，用于文件目录读取
$ ionic cordova plugin add cordova-plugin-file$ npm install --save @ionic-native/file
2、安装Version，，用于获取当前app版本
$ ionic cordova plugin add cordova-plugin-app-version$ npm install --save @ionic-native/app-version
3、安装transfer插件，用于下载服务器apk
$ ionic cordova plugin add cordova-plugin-file-transfer$ npm install --save @ionic-native/file-transfer
4、安装opener2，用于打开指定目录的apk进行安装
$ ionic cordova plugin add cordova-plugin-file-opener2$ npm install --save @ionic-native/file-opener

$ ionic cordova plugin add cordova.plugins.diagnostic
$ npm install --save @ionic-native/diagnostic

20181113 build android 报错 AAPT: error: resource android:attr/fontVariationSettings not found.
将下面代码添加到platforms/android/app/build.gradle 和 platforms/android/build.gradle 文件里
configurations.all {
	resolutionStrategy {
		force 'com.android.support:support-v4:27.1.0'
	}
}

20181119 苹果版安装提示 invalid profile,需要进苹果证实管理网页里面的相应证书里的设备删除，下载，重新配置。


20181121 处理单 实际开始和实际结束时间 改为手动录入（在界面加入输入选项）



v1.0.6  处理单 未完成 加入 实际开始时间+实际完成时间。

20181130 修改包名，  解析包错误 问题解决。 应该是包名首字母不能为大写这个问题引起。
              Ionic-Android平台项目调试时出错：The connection to the server was unsuccessful. ==>
在项目中的文件config.xml下，重新设置请求时间：   
 <platform name="android">         <preference name="loadUrlTimeoutValue" value="600000" /> </platform>  
生成 新的providers后需要 删除 httpclient 引用，否则白屏。

客户签名的时候，横屏签名。
ionic cordova plugin add cordova-plugin-screen-orientation
npm install --save @ionic-native/screen-orientation
app.module.ts 的 providers 进行引用 ScreenOrientation。

安卓打包报错 —
* What went wrong:
A problem occurred configuring project ':app'.
> Could not resolve all files for configuration ':app:classpath'.
   > Could not find manifest-merger.jar (com.android.tools.build:manifest-merger:26.0.0).
     Searched in the following locations:
         https://jcenter.bintray.com/com/android/tools/build/manifest-merger/26.0.0/manifest-merger-26.0.0.jar
   > Could not find ddmlib.jar (com.android.tools.ddms:ddmlib:26.0.0).
     Searched in the following locations:
         https://jcenter.bintray.com/com/android/tools/ddms/ddmlib/26.0.0/ddmlib-26.0.0.jar
   > Could not find dvlib.jar (com.android.tools:dvlib:26.0.0).
     Searched in the following locations:
         https://jcenter.bintray.com/com/android/tools/dvlib/26.0.0/dvlib-26.0.0.jar
   > Could not find common.jar (com.android.tools:common:26.0.0).
     Searched in the following locations:
         https://jcenter.bintray.com/com/android/tools/common/26.0.0/common-26.0.0.jar

解决方法：build.gradle 文件内把 maven{…} 属性放到第一个顺序。


极光推送 -安卓版 
couldn't find "libjcore126.so" 
E/art: No implementation found for int cn.jiguang.service.Protocol.GetSdkVersion() (tried Java_cn_jiguang_service_Protocol_GetSdkVersion and Java_cn_jiguang_service_Protocol_GetSdkVersion__)
01-07 11:54:15.754 10373-10801/io.jiayeapp.yun E/JIGUANG-JCore: [JCoreGlobal] Get sdk version fail![获取sdk版本失败!]

解决方法：拷贝 libjcore126.so 文件到对应文件夹内

	  

