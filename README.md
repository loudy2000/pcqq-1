# PCQQ-Protocol
PCQQ协议
简单实现某版本QQ登录与收发消息的功能


如果对你有用，希望你能留下Star


源码仅供参考，欢迎吐槽
------------------------------------------
2018-9-1 @sgkoishi<br/>
移除ByteBuffer，使用BinaryReader和BinaryWriter进行读写。

发送数据包的方式变更<br/>
原方式<br/>
var buf = new ByteBuffer();<br/>
new Send_0x0000().Fill(buf);<br/>
Send(buf);<br/>
新方式<br/>
Send(new Send_0x0000().WriteData());<br/>
使用以下方法替换原有的ByteBuffer.Put和Get<br/>
若类型为byte或byte[]<br/>
BinaryReader.ReadByte()<br/>
BinaryReader.ReadBytes(int count)<br/>
BinaryWriter.Write(byte) 注意：需要进行类型转换，如Write((byte)1);<br/>
BinaryWriter.Write(byte[])<br/>
对于其他类型(char, ushort, int, long)<br/>
BinaryReader.BEReadChar()<br/>
BinaryReader.BEReadUInt16()<br/>
BinaryReader.BEReadInt32()<br/>
BinaryWriter.BEWrite(ushort)<br/>
这些扩展方法定义于Utils.Util.cs内。

2018-8-31
<br/>
合并Core和Framework到同一个文件夹@sgkoishi（如果编译出错删除bin、obj和.vs重新编译）
<br/>
添加发送系统表情(格式为“[face{num}.gif]”)，num为系统表情对应索引

2018-8-30
<br/>
新增长文本分段发送@sgkoishi
<br/>
修改为项目为.Net Core
<br/>
以一种我也不知道会不会出问题的方式兼容了Core和Framework了

2018-8-29
<br/>
新增验证码处理

联系方式
------------------------------------------
我的TOXID：536F06809AAE9F29B8440B308E310AF8A26B9F93ADB60CAE086EEB26AB8F0D167486F38F39ED
<br>
<!--img src="/tox_save.png?raw=true" style="width:275px;" alt="联系方式"-->
<br>
