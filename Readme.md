# ABANDONED

Youtube has a quota of 10 000,
which means you can only uplaod 4 vidoes with api's a day.

I may come back to this some day to do automated editing.
I want to cut videos based upon audio being there or not.
But abandoned for now.

# Stream too youtube

Automatically edit video files and publishes them to youtube.

Youtube has different requirements from streams then twitch does.
We for example want to make the videos be chopped up into
small segments and schedules them into a future.

Runs:

```bash
ffmpeg -i $IN_FILE.mp4 -c copy -map 0 -segment_time 00:$SEG_SIZE:00 -f segment -reset_timestamps 1 $OUT_FILE-%03d.mp4
```

And then per segment an uploader:
https://github.com/tokland/youtube-upload

Where the publish date starts at $DATE and is incremented by $SEG_HOUR.

## TODO

In future I also want to do some auto editing such
as cutting out segments where audio levels are below a treshold.


# Resoures

## I found a project that does it for me~
https://github.com/carykh/jumpcutter

## Matroska
This is the container for a video. It has one or more audio tracks and a
video track.
We'll try using this first cause it's default in obs
(I know atm nothing about codecs, I imagine this will change soon).

+ https://www.matroska.org/technical/specs/index.html
+ https://github.com/vi/HsMkv

