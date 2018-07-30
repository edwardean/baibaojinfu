### 安装配置Charles
	
##### Charles是抓包软件，可以抓App的网络请求，进一步可以修改网络请求的数据。

1. 下载安装Charles
	* Charles下载地址 [百度搜索'Charles windows 破解版下载']
	* 下载Charles之后进行安装

2. Charles安装后电脑端进行配置
	* 安装Charles的证书到电脑上
	
	![A302BBD0A088E3027022D2295A522AC5.jpg](https://i.loli.net/2018/07/30/5b5f210f9cefd.jpg)


	![E644C239705A0F35D1428A796EAA7681.png](https://i.loli.net/2018/07/30/5b5f210f9ca99.png)


3. 手机链接Charles（以iPhone为例）
	* 手机链接电脑
		* 注意要保证电脑跟手机处于同一个Wifi下。比如手机和电脑都连接到某个叫XX的wifi上。
		* 打开系统设置-局域网设置，点击当前连接wifi最右边的感叹号，划到页面最底部的配置代理。
		
		![IMG_6861.PNG](https://i.loli.net/2018/07/30/5b5f21ab997bf.png)

		![IMG_6862.PNG](https://i.loli.net/2018/07/30/5b5f21ab9b53e.png)

		* 在配置代理中选择手动。
		* 服务器一栏写你要连接的电脑的ip地址。
		* 端口一栏写8888

		![IMG_6863.PNG](https://i.loli.net/2018/07/30/5b5f21ab9d3ea.png)

	* 在手机上安装并信任Charles的证书（不安装证书的话无法抓包）
		* 如果上一步手机连接电脑成功后这一步只需要在系统Safari浏览器中访问http://charlesproxy.com/getssl 就会提示你安装证书文件了。

		![IMG_6864.PNG](https://i.loli.net/2018/07/30/5b5f225693eb1.png)

		* 证书安装后还需要手动信任以下。打开系统设置-通用-关于本机-证书信任设置，把里面没有打开的开关全打开就行了。
		
		![IMG_6865.PNG](https://i.loli.net/2018/07/30/5b5f2256a266e.png)


4. 开始抓包了（下面的截图都是在苹果电脑上的截图了，具体Charles的操作苹果和Windows其实都差不多）
	* 这时候你在手机上打开佰宝金服后在Charles中就能看到网络请求了，有https://app.baibaojinfu.com字样的请求就是佰宝金服App的网络请求，其余的忽略即可。
	* 删除其他多余的网络请求直接点Charles工具栏里面的垃圾桶的图标就可以删除了
	
	![1532961479911-image.png](https://i.loli.net/2018/07/30/5b5f22d92ca3c.png)

	* 怎么让首页里的佰宝盈的"立即出借"的按钮变成可以点击状态呢？ 答案：需要修改首页的网络请求数据。
	每次在首页刷新可以看到如下图所示的一条网络请求：

	![1532961784079-image.png](https://i.loli.net/2018/07/30/5b5f2405e95c7.png)
	
	修改这个网络请求的操作：
	右键单击这条网络请求，在弹出的菜单中选择最下面的"Map Local"
	
	![1532962000364-image.png](https://i.loli.net/2018/07/30/5b5f2589b8772.png)

	![1532962066660-image.png](https://i.loli.net/2018/07/30/5b5f25a61f94c.png)
	
	注意这个界面中的Query这一栏中的东西需要全部删掉，包括后面的Map Local操作也是。
	
	上图中红框里点Choose，选择下面附件中的"首页数据.json"
	
	![1532962093931-image.png](https://i.loli.net/2018/07/30/5b5f25f936646.png)

这时候再重新刷新首页的话，"立即出借"按钮应该已经可以点击了。


5. 修改详情页数据
	* 到详情页之后会看到这么一条网络请求：
	
	![1532962437823-image.png](https://i.loli.net/2018/07/30/5b5f26d2debdb.png)

	* 同样右键单击，选择"Map Local", 这次选择的文件是附件中的"详情页.json"
	
	![1532962108085-image.png](https://i.loli.net/2018/07/30/5b5f27216e41e.png)

	* 这么操作之后重新下拉详情页的话页面底部的"立即出借"按钮应该已经是可以点击状态了
	
6. 上面一步操作完一点击"立即出借"，我靠会出现一个"该标不可投"的报错。

	![1532962730511-image.png](https://i.loli.net/2018/07/30/5b5f27b73a883.png)

这个就是点击详情页"立即出借后的这条网络请求，修改方式同样是右键单击，"Map Local"选择附件中的"立即出借.json", 这么操作之后就可以到最后的页面了。

![IMG_D6DB0AA5BED3-1.jpeg](https://i.loli.net/2018/07/30/5b5f2841f2049.jpeg)




### [我就是上面说的传说中的附件](https://pan.baidu.com/s/10s2xcyCSRgXXHOJbgKhj1A)
