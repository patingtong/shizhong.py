# shizhong.py
timer 变量设置了计时器时间，这里设定为25分钟，即1500秒。 divmod() 函数将剩余时间分成分钟和秒钟，并打印出来。 使用 来格式化字符串，并使用 参数实现动态刷新显示。{}end='\r' time.sleep() 函数使程序等待1秒钟。 每次循环减少计时器的时间，直到计时器变为0。 最后，使用 函数播放系统默认声音文件，提醒您停止工作。os.system()
import time
import os

# 设置计时器时间（单位：秒）
timer = 1500

while timer > 0:
    # 将剩余时间转换为分钟和秒钟
    minutes, seconds = divmod(timer, 60)

    # 格式化并打印剩余时间
    timer_display = '{:02d}:{:02d}'.format(minutes, seconds)
    print(timer_display, end='\r')

    # 等待1秒钟
    time.sleep(1)

    # 减少计时器时间
    timer -= 1

# 完成后播放声音
os.system('afplay /System/Library/Sounds/Glass.aiff')
print("Time's up!")
