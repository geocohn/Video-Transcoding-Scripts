# Video Transcoding Scripts for Linux

These are bash scripts for transcoding video files using the free open source package [ffmpeg](https://ffmpeg.org/). Ffmpeg is used because its efficiency, speed, and encoding quality far surpass anything commercially available. The scripts are structurally similar, but vary by the output screen dimensions, codec, and frame rate of the output videos.

## Getting Started

These instructions will tell you everything you need to know to quickly and easily transcode your videos in preparation for deployment to hosting sites like YouTube or Vimeo, or to HTML5 sites.

### Prerequisities

To use the scripts you will need
* A system such as linux that allows you to run bash from the command line
* ffmpeg
* qt-faststart

### Installing

After cloning the repository, go to the _scripts_ directory and copy the script files to /usr/local/bin

```
sudo cp * /usr/local/bin
```

## Running the scripts

Run the scripts with any number of arguments. All files matching the filespecs given by the arguments will be transcoded. The output filenames will match the bases of input filenames, but with screen dimensions and appropriate filetype endings. For example
 
```
mp4ify1080 video1.mov
```
creates the output file video1.1920x1080.mp4

In a directory containing
```
sequence-a.v1.mov
sequence-a.v2.mov
sequence-b.v2.mov
```

running the following:
```
mp4ify750 *.v2.mov
```
results in the creation of the transcoded video files
```
sequence-a.v2.1280x720.mp4
sequence-a.v2.1280x720.mp4
```

## The scripts

- `mp4ify1080` creates a 1920x1080 23.976 fps h.264 / aac encoding in a .mp4 container
- `mp4ify1080-25` creates a 1920x1080 25 fps h.264 / aac encoding in a .mp4 container
- `mp4ify1080-30` creates a 1920x1080 29.97 fps h.264 / aac encoding in a .mp4 container
- `mp4ify360` creates a 640x360 23.976 fps h.264 / aac encoding in a .mp4 container
- `mp4ify360-25` creates a 640x360 25 fps h.264 / aac encoding in a .mp4 container
- `mp4ify360-30` creates a 640x360 29.97 fps h.264 / aac encoding in a .mp4 container
- `mp4ify360bitc` creates a 640x360 23.976 fps h.264 / aac encoding with burn-in timecode in a .mp4 container
- `mp4ify360bitc-25` creates a 640x360 25fps h.264 / aac encoding with burn-in timecode in a .mp4 container
- `mp4ify720` creates a 1280x720 23.976 fps h.264 / aac encoding in a .mp4 container
- `mp4ify720bitc` creates a 1280x720 23.976 fps h.264 / aac encoding with burn-in timecode in a .mp4 container
- `ogvify720` creates a 1280x720 23.976 fps Theora / Vorbis encoding in a .ogv container
- `ogvify720-30` creates a 1280x720 29.97 fps Theora / Vorbis encoding in a .ogv container
- `webmify720` creates a 1280x720 23.976 fps VP9 / Vorbis encoding in a .WebM container
- `webmify720-30` creates a 1280x720 9.97 fps VP9 / Vorbis encoding in a .WebM container

## Authors

* **George Cohn** - *Initial work* - https://github.com/GeoCohn

## License

Copyright 2016 George Cohn III

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

