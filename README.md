说明文档
==
##一. 环境需求
python == 3.7.3<br>
opencv-python == 4.2.0.32	<br>
numpy == 1.18.1<br>
tensorflow == 1.14.0<br>
scikit-image == 0.16.2<br>
argparse==1.4.0<br>

##二. 流程
#####1. 控制台输入命令<br>
```
    echo %PATH%
```
将所有包含anaconda的路径添加到系统环境变量中系统变量的Path中；<br>
<br>
#####2. 打开控制台，输入:
```
    python
```
然后输入：
```
    import pythoncom
    print(pythoncom.CreateGuid())
```
将输出的id（类似如下格式）替换掉COM.py文件第22行的id；
```
    {52730D43-A6AD-4D21-93D4-14A679BD00C8}

```

#####3. 打开控制台，进入COM.py文件所在路径，输入:
```
    python COM.py
```
运行COM.py文件；
直到出现如下结果即为顺利运行：
```
    Registering COM server
    Registered:MaskRCNN.Detector
```
保留此控制台窗口，重新打开另一个控制台窗口，进入下一步操作；

#####4. 在新的控制台窗口进入COM.py文件所在路径，输入：
```
    python
```
再输入：
```
    import win32com.client
    s = win32com.client.Dispatch('MaskRCNN.Detector')
    s.detect_folder('images')
```
其中
```
    'images'
```
为包含待检测图像的文件夹名，即开始进行检测；

#####5. 退出
在步骤3.中保留的控制台输入：
```
    python COM.py --unregister
```
出现如下结果即为成功退出：
```
    Unregistered: MaskRCNN.Detector
```
