# ByteTrack

+ 多目标跟踪
+ 基于检测的跟踪，先检测在跟踪
+ 基于YOLOX网络
+ 两次跟踪
  + 大图片——YOLOX——>人的位置（纯检测）output[x,y,w,h,class,confidence]——跟踪——>