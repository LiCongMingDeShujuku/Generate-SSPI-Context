![CLEVER DATA GIT REPO](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/0-clever-data-github.png "李聪明的数据库")

# POST TITLE
#### SECONDARY TITLE
**发布-日期: 2007年03月22日 (评论)**

## Contents

- [中文](#中文)
- [English](#English)
- [Build Info](#Build-Info)
- [Author](#Author)
- [License](#License) 


## 中文
无法生成SSPI上下文

注意： sspi错误有时是固定的（至少在2005年），只需调整帐户到“本地系统” 服务登录即可，这在许多在sql server和分析服务之间的连接问题情况下都有效。 
在其他情况下，以下是如何通过2个简单步骤修复SSPI上下文错误。

* 步骤1：
你需要微软的Setspn实用程序，你需要域管理员权限来运行它。
你在哪里获得Setspn工具？你可以从这里下载它
链接：
http://www.microsoft.com/downloads/...laylang=en
或者你可以从Windows 2003 Server SP1 CD获取它。
它被称为：SP1.exe的支持工具
你可以搜索suptools.msi，或者setspn.exe。
一旦你在工作站上或者在服务器上安装了支持工具，你可以在以下位置找到Setspn.exe实用程序：
c：\ program files \ support tools
Setspn实用程序只能在命令提示符中使用。

* 第2步：
转至：开始 - >运行并输入CMD
输入：cd程序文件\支持工具
从这里开始，你需要指定用于从Management Studio或Enterprise Manager进行连接
的域用户帐户
输入：
setspn -L MyDomain \ MyUserName
现在你应该看到类似于以下内容的输出：
`C:\Program Files\Support Tools>setspn -L MyDomain\MyUserName
Registered ServicePrincipleNames for CN=MyUserName Service Account, OU=Service Accounts,
DC=MyDomain,DC=com:
mssqlsvc/MyServer1.MyDomain.com:MyPort
mssqlsvc/MyServer2.MyDomain.com:MyPort
mssqlsvc/MyServer3.MyDomain.com:MyPort
mssqlsvc/MyServer4.MyDomain.com:Myport
`
从结果中，你应该能够看到SQL SPN具有的服务器列表已成功注册到DNS。
注意：并非所有服务器都会在此处显示，而是你要查找的内容是收到SSPI错误的服务器。
你能看到你正在使用的服务器的SSPI上下文错误为是什么吗？
如果不能，只需键入以下内容：


`setspn -a mssqlsvc MyServer MyDomain\MyUserName`
if this syntax does not work for you. try this:
`setspn -A MSSQLSvc/MyServer.MyDomain.com:1433 MyAccount`
once this is done check again to see if your Server is in the list
by running the following:
`setspn -L MyDomain\MyUserName`


现在你应该可以看到你的服务器。 
尝试返回管理工作室或企业管理器连接到服务器。
完成。

## English
Cannot Generate SSPI Context

Note:
sspi errors are sometimes fixed (at least in 2005) simply by adjusting the service login
account to “local system” this has worked in many situations regarding connectivity issues
between sql server, and analysis services.
moving on… in other cases..
here is how to fix the SSPI Context error in 2 easy steps.

* STEP 1:
you will need the Setspn utility from Microsoft, and you’ll need
domain admin rights to run it.
where do you get the Setspn utility? you can download it from this
`link:
http://www.microsoft.com/downloads/…laylang=en`
or you can get it from the Windows 2003 Server SP1 CD.
it’s called: Support Tools for SP1.exe
you could always google for the suptools.msi, or setspn.exe if
you need.
once you get the Support Tools installed either on your workstation,
or on the server it’s self you can find the Setspn.exe utility in the
following location:
`c:\program files\support tools`
the Setspn utility can only be used from the Command Prompt.

* STEP 2:
Go to: Start -> Run & type in CMD
type in:
`cd program files\support tools`
from here you will need to specify the domain user account that you are
using to connect from Management Studio, or Enterprise Manager
type in:
`setspn -L MyDomain\MyUserName`
now you should see the output which looks something like the following:
`C:\Program Files\Support Tools>setspn -L MyDomain\MyUserName
Registered ServicePrincipleNames for CN=MyUserName Service Account, OU=Service Accounts,
DC=MyDomain,DC=com:
mssqlsvc/MyServer1.MyDomain.com:MyPort
mssqlsvc/MyServer2.MyDomain.com:MyPort
mssqlsvc/MyServer3.MyDomain.com:MyPort
mssqlsvc/MyServer4.MyDomain.com:Myport
`

From the results you should be able to see a list of servers who’s SQL SPN has
been successfully registered to the DNS.
Note: not all your servers will be represented here, but what you are looking for
is the Server that you are getting the SSPI error on.
Do you see the Server that you are having
the SSPI Context error for?
If not… Just type in the following:

`setspn -a mssqlsvc MyServer MyDomain\MyUserName`
if this syntax does not work for you. try this:
`setspn -A MSSQLSvc/MyServer.MyDomain.com:1433 MyAccount`
once this is done check again to see if your Server is in the list
by running the following:
`setspn -L MyDomain\MyUserName`
now you should see your Server in there.
try going back to your Management Studio or Enterprise Manager and
connecting to the server.
Thats it.




[![WorksEveryTime](https://forthebadge.com/images/badges/60-percent-of-the-time-works-every-time.svg)](https://shitday.de/)

## Build-Info

| Build Quality | Build History |
|--|--|
|<table><tr><td>[![Build-Status](https://ci.appveyor.com/api/projects/status/pjxh5g91jpbh7t84?svg?style=flat-square)](#)</td></tr><tr><td>[![Coverage](https://coveralls.io/repos/github/tygerbytes/ResourceFitness/badge.svg?style=flat-square)](#)</td></tr><tr><td>[![Nuget](https://img.shields.io/nuget/v/TW.Resfit.Core.svg?style=flat-square)](#)</td></tr></table>|<table><tr><td>[![Build history](https://buildstats.info/appveyor/chart/tygerbytes/resourcefitness)](#)</td></tr></table>|

## Author

- **李聪明的数据库 Lee's Clever Data**
- **Mike的数据库宝典 Mikes Database Collection**
- **李聪明的数据库** "Lee Songming"

[![Gist](https://img.shields.io/badge/Gist-李聪明的数据库-<COLOR>.svg)](https://gist.github.com/congmingshuju)
[![Twitter](https://img.shields.io/badge/Twitter-mike的数据库宝典-<COLOR>.svg)](https://twitter.com/mikesdatawork?lang=en)
[![Wordpress](https://img.shields.io/badge/Wordpress-mike的数据库宝典-<COLOR>.svg)](https://mikesdatawork.wordpress.com/)

---
## License
[![LicenseCCSA](https://img.shields.io/badge/License-CreativeCommonsSA-<COLOR>.svg)](https://creativecommons.org/share-your-work/licensing-types-examples/)

![Lee Songming](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/1-clever-data-github.png "李聪明的数据库")

