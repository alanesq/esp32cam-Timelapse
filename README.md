NOTE: When using Arduino IDE I find it reboots if no sd card present and the LED stays on full all the time with latest esp32 board manager.  I am using version  1.0.6<br>
known bug: https://github.com/espressif/arduino-esp32/issues/5195<br><br>
      
<h1>ESP32Cam time-lapse video recorder for use with the Arduino IDE or PlatformIO</h1>

<br>I have tried to make this sketch as easy to follow as I can and show how to create web pages with updating information, buttons etc.
<br>It is based on my demo sketch here:   https://github.com/alanesq/esp32cam-demo

<br>It records a series of JPG files to an sd card which can then be combined in to a video file
<br>I use this software to do this:  https://www.ffmpeg.org/
<br>with the command:    ffmpeg -framerate 10 -pattern_type glob -i '*.jpg' -c:v libx264 -profile:v high -crf 20 -pix_fmt yuv420p timelapse.mp4

If it is unable to attach to the supplied wifi then it creates it's own access point called 'timelapse' with password '12345678'.


<br><table><tr>
  <td><img src="/misc/tl.png" /></td>
</tr></table> 

Notes:

When starting it counts how many files are already in /img on the sd card, if there are a lot then this can take a long time


<br><br>sketch location: https://github.com/alanesq/esp32cam-Timelapse
