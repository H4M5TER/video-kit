# Scripts

一些自用的脚本 用于视频处理

## TODO

### 视频分割&合并

轻量级二刀流视频剪辑解决方案

#### 时间计算

FFmpeg要求开始时间+持续时间的格式 有自动计算时间再输入FFmpeg的需求 甚至考虑做一个拖进度条取时间点的GUI

#### 精确时间点切除

FFmpeg无法seek到非关键帧 不重编码的情况下 如果结束时间不处于关键帧 视频结尾将会是空白  
可以通过`-avoid_negative_ts 1`解决 将会找到结束时间后的第一个关键帧以补全视频 但如此一来视频会出现重叠 无法精确裁剪  
因此只使用FFmpeg只有重编码能解决问题 但开销过大 考虑CPP手撕视频

#### 解决时间戳错误

解决视频分割后合并的时间戳错误 考虑音画不同步问题

#### 队列功能

允许按顺序压制

### GitHub Action

1. win32+win64
2. 自动拉取和备注FFmpeg版本
3. 编译C++代码

### 解决FFmpeg输出乱码问题

考虑改代码编译？

### 可配压制参数

使用可配置的压制参数并且提供默认参数

### 更智能的选项复用

文件拆太多了 但是让用的人在命令行里打字又很啥b
