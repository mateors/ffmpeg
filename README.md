# How can I reduce my video file size?
> use the ffmpeg software to reduce any video format
> in my case it reduces from 700MB to 100MB almost 7 times lower than the original.

> use the command below todo so..

> `ffmpeg -i videofile.mp4 -vcodec libx264 -crf 28 output.mp4`

## Trim video files using FFmpeg
> A much better solution is to perform “lossless” trimming. Fortunately, there is a way to do this with the wonderful command-line utility FFmpeg

> `ffmpeg -i input.mp4 -ss 01:19:27 -to 02:18:51 -c:v copy -c:a copy output.mp4`\
> This will cut out the section from about 1h19min (after the -ss command) to 2h18min (after the -to command).The copy parts of the command are meant to copy both the original audio and video content without recompressing. This means that the above command only takes a few seconds to run.

> `ffmpeg -ss 00:00:06 -i input.mp4 -c copy output.mp4`\
> Above command will start copying from 06 seconds to the end of the video

## Convert-a-set-of-images-into-a-video

```
ffmpeg -framerate 1 -i frame_%d.png -c:v libx264 -vf "pad=ceil(iw/2)*2:ceil(ih/2)*2" -pix_fmt yuv420p slide.mp4

ffmpeg -framerate 16 -i frame_%d.png -c:v libx264 -vf "pad=ceil(iw/2)*2:ceil(ih/2)*2" -pix_fmt yuv420p slide4.mp4

ffmpeg -framerate 12 -i frame_%d.png -c:v libx264 -vf "scale=1920:1080:force_original_aspect_ratio=decrease:eval=frame,pad=1920:1080:-1:-1:eval=frame"  -pix_fmt yuv420p -crf 20 slide9.mp4
```


## Concat multiple videos into one video file
> ffmpeg -f concat -i `data3.txt` -c copy output.mp4

### `data3.txt` content:
```
file '1_1_1__1_Introduction.mp4' 
file '1_1_2__2_Who_This_Course_Is_For.mp4' 
file '1_1_3__3-_What_You_Need.mp4' 
```

### References:

* [Sample Video files](https://file-examples.com/index.php/sample-video-files/sample-webm-files-download)
* [Github](https://gist.github.com/dvlden/b9d923cb31775f92fa54eb8c39ccd5a9)
* [Stack](https://unix.stackexchange.com/questions/28803/how-can-i-reduce-a-videos-size-with-ffmpeg)
* [Chaet Sheet](https://gist.github.com/steven2358/ba153c642fe2bb1e47485962df07c730)
* [FFMPEG VIDEO MANIPULATION](https://api.video/blog/video-trends/ffmpeg-for-beginners-processing-converting-and-streaming-video)
* [ffmpeg Introduction](https://programminghistorian.org/en/lessons/introduction-to-ffmpeg)
* [ffmpeg-libav](https://www.lhsz.xyz/read/ffmpeg-libav-tutorial/spilt.4.spilt.1.blank)
* [convert-a-set-of-images-into-a-video](https://hamelot.io/visualization/using-ffmpeg-to-convert-a-set-of-images-into-a-video)
