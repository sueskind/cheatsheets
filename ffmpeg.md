# FFmpeg cheatsheet

### Change framerate
```
ffmpeg -i <input> -filter:v fps=30 <output>
```

### Cut video without re-encoding starting from timestamp
```
ffmpeg -i <input> -ss <hh>:<mm>:<ss> -c copy <output>
```

### Cut video without re-encoding until timestamp
```
ffmpeg -to <hh>:<mm>:<ss> -c copy <output>
```
