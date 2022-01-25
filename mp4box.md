## Gpac MP4Box

> sudo apt install gpac

> MP4Box -dash 4000 -segment-name folder/mysegs_%s -url-template -out manifest.mpd input_audio_128k.mp4 input_video_160x90_250k.mp4

> MP4Box -dash 4000 -segment-name folder/mysegs_%s -url-template -out manifest.mpd input_audio_128k.mp4 input_video_160x90_250k.mp4 input_video_640x360_750k.mp4  input_video_1920x1080_1500k.mp4

## Local machine build file location
> /home/mostain/go/src/master_academy/gpac_public/bin/gcc


```mp4box -dash 4000 \
  -out gpac_segment/myvideo \
  -segment-name '$RepresentationID$_$Number%03d$' \
  myvideo_1920x1080.mp4 \
  myvideo_1280x720.mp4 \
  myvideo_640x360.mp4 \
  myvideo_320x180.mp4
  ```
  
https://stackoverflow.com/questions/67181403/how-to-generate-hex-strings-for-clearkey-drm

https://stackoverflow.com/questions/3451670/java-aes-and-using-my-own-key/3452620#3452620

https://www.instructables.com/Making-Your-Own-Simple-DASH-MPEG-Server-Windows-10/

https://8gwifi.org/sshfunctions.jsp


div, button, img, svg, path, span, input, a


sudo apt install gpac

https://github.com/gpac/gpac/wiki/MP4Box


MP4Box -dash 1000 file.mp4 -out live.m3u8:dual:cmaf
MP4Box -dash 1000 file.mp4 -out live.mpd --dual --cmaf


https://developer.mozilla.org/en-US/docs/Web/Media/DASH_Adaptive_Streaming_for_HTML_5_Video


## Encoding the video:
You are going to write the commands to transform the input video into multiple bitrates and resolutions, so a DASH video player can switch between bitrates depending on the current download speed of the playback device
 
 
 ffmpeg -i input.avi -s 160x90 -c:v libx264 -b:v 250k -g 90 -an input_video_160x90_250k.mp4
 
 ffmpeg -i in.video -c:v libvpx-vp9 -keyint_min 150 -g 150 -tile-columns 4 -frame-parallel 1  -f webm -dash 1 \
-an -vf scale=160:90 -b:v 250k -dash 1 video_160x90_250k.webm

ffmpeg -i in.video -c:v libvpx-vp9 -keyint_min 150 -g 150 -tile-columns 4 -frame-parallel 1  -f webm -dash 1 \
-an -vf scale=160:90 -b:v 250k -dash 1 video_160x90_250k.webm


# In DASH you want to stream audio separate from video. To do that we use the following command: 
ffmpeg -i input.avi -c:a aac -b:a 128k -vn input_audio_128k.mp4 


## Dashifying the Encoded Files:
Now you can turn them (encoded files) into DASH compatible files.

This process will generate MPEG-4 initialization files that the DASH player reads at load time and a manifest file that tells the player where all the necessary files are and how to read them.


> mp4box -dash 4000 -rap -profile dashavc264:onDemand -mpd-title BBB -out manifest.mpd -frag 2000 input_audio_128k.mp4 input_video_160x90_250k.mp4 input_video_320x180_500k.mp4 input_video_640x360_750k.mp4 input_video_640x360_1000k.mp4 input_video_1280x720_1500k.mp4


>> mp4box -dash 4000 -rap -profile dashavc264:onDemand -mpd-title BBB -out manifest.mpd -frag 2000 input_audio_128k.mp4 input_video_320x180_500k.mp4 input_video_1280x720_1500k.mp4

-segment-name '$RepresentationID$_$Number%03d$'
-segment-ext m4s


* Building PSSH box for Widevine
* Building PSSH box for CENC

### https://www.w3.org/TR/eme-initdata-cenc/
> to generate pssh data and/or pssh box to use in our workflow. This tools helpful to easily provide the base64 pssh data for Widevine and PlayReady.


### https://installati.one/ubuntu/20.04/gpac
> sudo dpkg -i gpac_1.1.0-DEV-rev1663-g881c6a94-master_amd64.deb

> sudo apt --fix-broken install

## Resource
* https://github.com/gpac/gpac/wiki/GPAC-Build-Guide-for-Linux
* https://tools.axinom.com/generators/PsshBox
* https://issueexplorer.com/issue/google/ExoPlayer/9466
* https://ottverse.com/mpeg-dash-packaging-using-gpac-mp4box-live-vod
* https://github.com/gpac/gpac/wiki/Common-Encryption
