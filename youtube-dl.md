
# youtube-dl/yt-dlp cheatsheet

Arguably better: [yt-dlp](https://github.com/yt-dlp/yt-dlp)

**Default download**
```bash
export PLAYLIST=""
yt-dlp --get-id "$PLAYLIST" | xargs -I '{}' -P 16 yt-dlp -f 'bestvideo[height<=720]+bestaudio/best[height<=720]' 'https://youtube.com/watch?v={}'
```

**Download playlist in parallel**

5 parallel workers:
```bash
youtube-dl --get-id "<playlist-url>" | xargs -I '{}' -P 5 youtube-dl 'https://youtube.com/watch?v={}'
```

**Select maximum quality**

Maximum quality 720p:
```
-f 'bestvideo[height<=720]+bestaudio/best[height<=720]'
```
