
# FFMPEG PCM F32LE ENCODER

Expected Input File format: PCM F32LE

GENERATING PCM F32LE TEST FILE:

ffmpeg -i file_example_MP3_700KB.mp3 -f f32le -acodec pcm_f32le input.pcm_f32le

COMPILING:

gcc f32le_transcode.c -o f32le_transcode -I/opt/local/include -L/opt/local/lib -lavformat -lavcodec -lavfilter -lavresample -lswresample -lavutil
usage examples:

CONVERTING F32LE TO AAC OUTPUT FILE:

./f32le_transcode input.pcm_f32le output.aac


[f32le @ 0x7fd0ff80a200] Estimating duration from bitrate, this may be inaccurate
[aac @ 0x7fd0ff814600] Qavg: 512.950
[aac @ 0x7fd0ff814600] 1 frames left in the queue on closing

VERIFY F32LE TO AAC OUTPUT FILE: :

ffprobe output.aac

[aac @ 0x7f856480d000] Estimating duration from bitrate, this may be inaccurate
Input #0, aac, from 'output.aac':
Duration: 00:00:32.72, bitrate: 60 kb/s
Stream #0:0: Audio: aac (LC), 44100 Hz, stereo, fltp, 60 kb/s

CONVERTING F32LE TO AAC WITH MP4 CONTAINER OUTPUT FILE:

./f32le_transcode input.pcm_f32le output.mp4

[f32le @ 0x7f8b99004e00] Estimating duration from bitrate, this may be inaccurate
[aac @ 0x7f8b97801800] Qavg: 512.950
[aac @ 0x7f8b97801800] 1 frames left in the queue on closing

VERIFY F32LE TO AAC WITH MP4 CONTAINER OUTPUT FILE:

ffprobe output.mp4

Input #0, mov,mp4,m4a,3gp,3g2,mj2, from 'output.mp4':
Metadata:
major_brand : isom
minor_version : 512
compatible_brands: isomiso2mp41
encoder : Lavf57.83.100
Duration: 00:00:39.47, start: 0.000000, bitrate: 49 kb/s
Stream #0:0(und): Audio: aac (LC) (mp4a / 0x6134706D), 44100 Hz, stereo, fltp, 48 kb/s (default)
Metadata:
handler_name: SoundHandler