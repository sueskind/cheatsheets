# FFmpeg cheatsheet

### Change framerate
```
ffmpeg -i <input> -filter:v fps=30 <output>
```

### Cut video from start without re-encoding
```
ffmpeg -ss <hh>:<mm>:<ss> -i <input> -c copy <output>
```
