## Purpose

This command is used to export files (especially movies) via `vlc` and apply some effects to them.
In this example I wanted to sync the audio track of a given `.mp4` since it was shifted by about 8 sec.

## Code

```bash
inputFile="MovieWithAudioShift.mp4"
audioShiftTime=8650 # in ms
"C:\Program Files\VideoLAN\VLC\vlc.exe" -vv "${inputFile}" --audio-desync=${audioShiftTime} --sout="#transcode{vcodec=h264,vb=1024,acodec=mp4a,ab=192,channels=2,deinterlace}:standard{access=file,mux=ts,dst=MyVid.mp4}"
```

## Example

```bash
┌─[23:37:39]-[:)]-[jeman@Asterix]-[/c/Users/jeman/Downloads/]-[29s]
└──> "C:\Program Files\VideoLAN\VLC\vlc.exe" -vv "Die Tribute von Panem.mp4" --audio-desync=8650 --sout="#transcode{vcodec=h264,vb=1024,acodec=mp4a,ab=192,channels=2,deinterlace}:standard{access=file,mux=ts,dst=MyVid.mp4}"

┌─[23:52:24]-[:)]-[jeman@Asterix]-[/c/Users/jeman/Downloads/]-[14m 41s]
└──>
```
The exporting of the about 1.5h movie took about 15 minutes.

## Additional notes

- [Here](https://wiki.videolan.org/VLC_command-line_help) are the possible cli options