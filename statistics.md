# ffprobe & ffmpeg for audio spectrogram analysis

ffprobe -print_format json -show_format -show_streams audio_1.mp3

sample_rate

ffmpeg -ss 00:00:00 -i audio_1.mp3 -t 00:00:00 -f f32le -

ffmpeg -formats


ffmpeg -i audio_1.mp3 -f f32le output.raw

ffmpeg -y  -i audio_1.mp3  -acodec pcm_s16le -f s16le -ac 2 -ar 48000 output.pcm

Lavf58.76.100
Lavc58.13

ffmpeg -y -i audio_1.mp3 -acodec pcm_s16le -f s16le -ac 1 -ar 1 -v quiet out.pcm

ffmpeg -y -i audio_1.mp3 -acodec pcm_s16le -f s16le -ac 1 -ar 1 out.pcm

## ffmpeg -i file.wav -f s16be -ar 8000 -acodec pcm_s16be file.raw

> ffmpeg -i audio_1.mp3 -f f32le -ar 48000 -acodec pcm_f32le file.raw

https://gist.github.com/pwenzel/f0b7589fd548c3ec4aad2842eb8d66b7


https://stackoverflow.com/questions/62242044/how-to-get-audio-peaks-with-ffmpeg

ffmpeg -i audio_1.mp3 -s 00:00:00 -t 00:00:10 -f f32le -ar 48000 file2.raw


ffmpeg -y -i audio_1.mp3 -f f32le -ac 2 -ar 48000 out.pcm

ffmpeg -y -i audio_1.mp3 -acodec pcm_s16le -f s16le -ac 2 -ar 48000 out4.pcm -> 210MB


ffmpeg -y -i audio_1.mp3 -acodec pcm_s16le -f s16le -ac 2 -ar 1 out5.pcm -> 4.49kb


ffmpeg -hide_banner -i audio_1.mp3 -filter:a volumedetect -f null -


ffmpeg -i audio_1.mp3 -af silencedetect=noise=0.0001 -f null -


lavfi.astats.Overall.Peak_count


ffmpeg -i audio_1.mp3 -af astats=metadata=1:reset=1,ametadata=print:key=lavfi.astats.Overall.RMS_level -f null - 2>result.txt


ffmpeg -i audio_1.mp3 -af astats=metadata=1:reset=1,ametadata=print:key=lavfi.astats.Overall.RMS_level -f null - > meta.txt


ffmpeg -i audio_1.mp3 -af astats=metadata=1:reset=1,ametadata=print:key=lavfi.astats.Overall.RMS_level:file=- 2> meta.txt



ffmpeg -i audio_1.mp3 -af astats=metadata=1:reset=1,ametadata=print:key=lavfi.astats.Overall.RMS_level:file=- -f null - > meta2.txt


ffmpeg -i audio_1.mp3 -af asetnsamples=48000,astats=metadata=1:reset=1,ametadata=print:key=lavfi.astats.Overall.RMS_level:file=- -f null - > meta4.txt

ffmpeg -i audio_1.mp3 -af asetnsamples=48000,astats=metadata=1:reset=1,ametadata=print:key=lavfi.astats.Overall.RMS_level:file=- -f null - > meta4.txt

##  print all metadata values available in frame.
> `ffmpeg -i audio_1.mp3 -af asetnsamples=48000,astats=metadata=1:reset=1,ametadata=print:file=- -f null - > meta6.txt`

ffmpeg -i audio_1.mp3 -filter:a volumedetect -f null /dev/null

## Resource
* [convert-a-set-of-images-into-a-video](https://hamelot.io/visualization/using-ffmpeg-to-convert-a-set-of-images-into-a-video)
* [audio types](https://trac.ffmpeg.org/wiki/audio%20types)
* [ffmpeg-wiki](https://trac.ffmpeg.org/wiki/audio%20types)
* [ffmpeg-filters](https://ffmpeg.org/ffmpeg-filters.html#astats)
* [ffmpeg-ametadata](https://ffmpeg.org/ffmpeg-all.html#metadata_002c-ametadata)
* [audiowaveform](https://github.com/bbc/audiowaveform#data-formats)
* [seewav](https://github.com/adefossez/seewav)
