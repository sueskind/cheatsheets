
# youtube-dl cheatsheet

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
