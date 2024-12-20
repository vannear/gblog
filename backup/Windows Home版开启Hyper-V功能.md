Windows的家庭版缺少了一些常用的功能，例如组策略，另一个比较重要的组件是Hyper-V功能，在控制面板的添加删除WINDOWS组件当中都无法找到这一功能，需要通过命令行的方式来进行添加。

以管理员模式打开CMD：

```powershell
pushd "%~dp0"
dir /b %SystemRoot%\servicing\Packages\*Hyper-V*.mum >hv.txt
for /f %%i in ('findstr /i . hv.txt 2^>nul') do dism /online /norestart /add-package:"%SystemRoot%\servicing\Packages\%%i"
del hv.txt
Dism /online /enable-feature /featurename:Microsoft-Hyper-V -All /LimitAccess /ALL
pause
```

原理是使用Dism工具在线下载HYPER-V管理器组件。