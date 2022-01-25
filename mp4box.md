> MP4Box -dash 4000 -segment-name folder/mysegs_%s -url-template -out manifest.mpd input_audio_128k.mp4 input_video_160x90_250k.mp4

> MP4Box -dash 4000 -segment-name folder/mysegs_%s -url-template -out manifest.mpd input_audio_128k.mp4 input_video_160x90_250k.mp4 input_video_640x360_750k.mp4  input_video_1920x1080_1500k.mp4

```mp4box -dash 4000 \
  -out gpac_segment/myvideo \
  -segment-name '$RepresentationID$_$Number%03d$' \
  myvideo_1920x1080.mp4 \
  myvideo_1280x720.mp4 \
  myvideo_640x360.mp4 \
  myvideo_320x180.mp4
  ```
