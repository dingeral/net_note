# ffmpep

ffmpep 是一个非常好用的视频处理软件。

- 简介

**使用方法**

ffmpeg 命令由五部分构成

```bash
ffmpeg {1} {2} -i {3} {4} {5}
```

1. 全局参数
2. 输入文件参数
3. 输入文件
4. 输出文件参数
5. 输出文件

**FFmpeg 常用的命令行参数**


c：指定编码器  
-c copy：直接复制，不经过重新编码（这样比较快）  
-c:v：指定视频编码器  
-c:a：指定音频编码器  
-i：指定输入文件  
-an：去除音频流  
-vn： 去除视频流  
-preset：指定输出的视频质量，会影响文件的生成速度，有以下几个可用的值 ultrafast, superfast, veryfast, faster, fast, medium, slow, slower, veryslow。  
-y：不经过确认，输出时直接覆盖同名文件。


- 动手做

**查看文件信息**

```bash
ffmpeg -i input.mp4
```

```bash
ffmpeg -i input.mp4 -hide_banner
```

**视频容器转换**

```bash
ffmpeg -i input.mp4 output.mkv
```

**改变分辨率**

```bash
ffmpeg -i input.mp4 -vf scale=480:-1 output.mp4
```

**视频分割**

```bash
ffmpeg -ss 00:00:00 -t 00:01:00 -i input.mp4 -vcodec copy -acodec copy output.mp4
ffmpeg -ss 01:00:00 -t 00:13:00 -i input.mp4 -vcodec copy -acodec copy output.mp4
```

-ss 表示开始切割的时间，-t 表示要切多少


- [FFmpeg 视频处理入门教程](https://www.ruanyifeng.com/blog/2020/01/ffmpeg.html)