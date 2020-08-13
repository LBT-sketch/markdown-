# 快快送SSL证书安装/更新流程</br> #
> 项目的SSL证书快过期时，需要及时更新，否则外网无法正常访问部署在服务器上项目。
## 注册/登录自己的阿里云账号 ##
> 也可以用工作室的阿里云账号

## <br>1.找到产品与服务---->ssl证书
![image](https://raw.githubusercontent.com/LBT-sketch/markdown-/master/ssl%E8%AF%81%E4%B9%A6%E5%AE%89%E8%A3%85%E6%88%96%E6%9B%B4%E6%96%B0%E6%AD%A5%E9%AA%A4/0.jpg)

## <br>2.购买免费的证书
![](https://raw.githubusercontent.com/LBT-sketch/markdown-/master/ssl%E8%AF%81%E4%B9%A6%E5%AE%89%E8%A3%85%E6%88%96%E6%9B%B4%E6%96%B0%E6%AD%A5%E9%AA%A4/1.jpg)

## <br>3.绑定项目域名
![](https://raw.githubusercontent.com/LBT-sketch/markdown-/master/ssl%E8%AF%81%E4%B9%A6%E5%AE%89%E8%A3%85%E6%88%96%E6%9B%B4%E6%96%B0%E6%AD%A5%E9%AA%A4/2.jpg)
![](https://raw.githubusercontent.com/LBT-sketch/markdown-/master/ssl%E8%AF%81%E4%B9%A6%E5%AE%89%E8%A3%85%E6%88%96%E6%9B%B4%E6%96%B0%E6%AD%A5%E9%AA%A4/3-1.jpg)

## <br>4.验证域名
> a.验证方式选择文件验证，把对应的文件下载到本地，解压得到一个txt文件</br>
> ![](https://raw.githubusercontent.com/LBT-sketch/markdown-/master/ssl%E8%AF%81%E4%B9%A6%E5%AE%89%E8%A3%85%E6%88%96%E6%9B%B4%E6%96%B0%E6%AD%A5%E9%AA%A4/4.jpg)
> b.然后用Winsp连接快快送正式服（域名指向的服务器）</br>
> c.把之前的txt文件放到/usr/tomcat/tomcat8/webapps/.well-known/pki-validation目录下</br>
> ![](https://raw.githubusercontent.com/LBT-sketch/markdown-/master/ssl%E8%AF%81%E4%B9%A6%E5%AE%89%E8%A3%85%E6%88%96%E6%9B%B4%E6%96%B0%E6%AD%A5%E9%AA%A4/5.jpg)
> 注：.well-known文件夹一般是隐藏着的，怎样让它显示出来，自行百度</br>
> d.打开/usr/tomcat/tomcat8/bin目录启动tomcat,运行命令如下</br>
> `sh startup.sh`
> e.回到阿里云验证页面，点击验证，完成验证，关闭tomcat</br>
> `sh shutdown.sh`

## <br>5.下载证书文件，更新到项目中
> a.选择tomcat类型的证书下载</br>
> ![](https://raw.githubusercontent.com/LBT-sketch/markdown-/master/ssl%E8%AF%81%E4%B9%A6%E5%AE%89%E8%A3%85%E6%88%96%E6%9B%B4%E6%96%B0%E6%AD%A5%E9%AA%A4/6.jpg)
> ![](https://raw.githubusercontent.com/LBT-sketch/markdown-/master/ssl%E8%AF%81%E4%B9%A6%E5%AE%89%E8%A3%85%E6%88%96%E6%9B%B4%E6%96%B0%E6%AD%A5%E9%AA%A4/7.jpg)
> b.下载下来后，解压得到一个pfx文件和txt文件,他们分别是证书文件和密码文件</br>
> c.将pfx文件放到项目的cert文件夹下，最后修改yml配置文件

## <br>6.打包更新到服务器上
