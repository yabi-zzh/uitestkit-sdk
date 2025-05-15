# uitestkit-sdk
  
**使用示例：**  

注意：在官方 com.ohos.uitestkit.api.Hdc 中的 ListDevices 方法在此重命名为 listDevices
```
        // 具体支持的方法请自行查看 com.ohos.uitestkit.api 目录下的类

        Hdc hdc = Hdc.getForDevice("设备udid");
        // 可选项，不设置则自动分配空闲端口
        hdc.setUitestPort(7878);
        hdc.killUiTestServer();
        
        // ==================== 日志配置 ====================
        // Debug级别
        Log.setLogLevel(Level.FINE);
        // Error级别（默认）
        Log.setLogLevel(Level.SEVERE);
        
        // ==================== 控制命令模块 ====================
        CtrlCmds cmds = CtrlCmds.getInstance(hdc);
        
        // ==================== 手势操作模块 ====================
        Gestures gestures = Gestures.getInstance(hdc);
        
        // ==================== 屏幕捕获模块 ====================
        Captures captures = Captures.getInstance(hdc);
        // 先调用下stop，确保新的捕获操作能正确启动
        captures.stopCaptureScreen();
        Captures.ScreenCapOptions options = new Captures.ScreenCapOptions();
        // 缩放比例
        options.scale = 0.5f;
        Captures.ScreenCapCallback callback = new Captures.ScreenCapCallback() {
            public void onData(byte[] data) {
                // 同屏JPEG数据
            }
            
            public void onException(Throwable e) {
                
            }
        };
        captures.startCaptureScreen(options, callback);
```
