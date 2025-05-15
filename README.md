# uitestkit-sdk
  
**因包名和方法名等同官方一致，所以此处只列出新增方法的使用示例：**

```
Hdc hdc = Hdc.getForDevice("2PN6R24307001422");  
hdc.setUitestPort(7878);
hdc.killUiTestServer();

// Debug级别
Log.setLogLevel(Level.FINE);
// Error级别
Log.setLogLevel(Level.SEVERE);

CtrlCmds cmds = CtrlCmds.getInstance(hdc);
cmds.inputText("xxxx");
```
