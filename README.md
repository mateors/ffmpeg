# How can i reduce my video size?
> use the ffmpeg software to reduce any video format
> in my case it reduces from 700MB to 100MB almost 7 times lower than the original.

> use the command below todo so..

`> ffmpeg -i videofile.mp4 -vcodec libx264 -crf 28 output.mp4`

### References:

*[Github](https://gist.github.com/dvlden/b9d923cb31775f92fa54eb8c39ccd5a9)

*[Stack](https://unix.stackexchange.com/questions/28803/how-can-i-reduce-a-videos-size-with-ffmpeg)
