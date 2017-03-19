1、说明：
userData行为通过将数据写入一个UserData存储区（UserData store）来保存数据，userData可以将数据以XML格式保存在客户端计算机上，如果你用的是 Windows 2000 或者 Windows XP，是保存在C:\Documents and Settings\Liming\UserData\文件夹下（如果操作系统不是安装在C盘，那么C就应该是操作系统所在的分区）。

该数据将一直存在，除非你人为删除或者用脚本设置了该数据的失效期。

userData行为提供了一个比Cookie更具有动态性和更大容量的数据结构。每页的UserData存储区数据大小可以达到64 Kb，每个域名可以达到640 Kb。
userData行为通过sessions为每个对象分配UserData存储区。使用save和load方法将UserData存储区数据保存在缓存（cache）中。一旦UserData存储区保存以后，即使IE浏览器关闭或者刷新了，下一次进入该页面，数据也能够重新载入而不会丢失。
出于安全的考虑，相同协议使用同一个文件夹保存UserData存储区数据。

在HTML、HEAD、TITLE和STYLE标记上应用了userData行为后使用save和load方法将会出错.

必须在行内或者文档的HEAD部分宣告如下样式：

<STYLE>
.userData {behavior:url(#default#userdata);}
</STYLE>

userData行为可用于Microsoft? Win32?和Unix平台上的IE 5.0以上版本，不支持Netscape。

2、语法：
HTML <ELEMENT STYLE="behavior:url('#default#userData')" ID=sID>
Script object.style.behavior = "url('#default#userData')"
object.addBehavior ("#default#userData")
注：sID参数是一个可以描述该标记的唯一id。ID是可选的，但如果有，可以在脚本中方便地对该标记加以控制。

3、成员：

expires
设置或取得使用userData行为保存数据的失效日期。
脚本语法：对象ID.expires = 参数
参数是一个使用UTC（Universal Time Coordinate，世界调整时间）格式表示失效日期的字符串。该属性可以读写，没有默认值。浏览器会对比这个日期和当前日期，如果到期，该数据就自动失效。

getAttribute()
取得指定的属性值。

load(存储区名)
从UserData存储区载入存储的对象数据。

removeAttribute()
从对象中删除指定的属性值。

save(存储区名)
将对象数据存入一个UserData存储区。

setAttribute()
设置指定的属性值。

XMLDocument
取得存储该对象数据的XML DOM引用。

具体用法可以查看MSDN（http://msdn.microsoft.com） 
