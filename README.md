# MOVIE MAX Railway Broadcaster — moviemaxlivetv edition

Opens your MOVIE MAX `/output` page on Cloudflare (https://moviemaxlivetv.nexusplatformafrica.workers.dev/output) in a hidden browser (picture + on-screen graphics + sound)
and sends it 24/7 to your HostHerb server. Viewers watch:

- HLS: https://watch.hostherb.com/tv-257/index.m3u8
- Player: https://watch.hostherb.com/player/tv-257/

The HostHerb server address, stream key and your output page are already built in, so no
Railway variables are needed. If the browser or the sending stops, it starts again by itself.

## Deploy
1. Replace the files in the GitHub repository your Railway service uses with these files and push.
2. Railway rebuilds automatically (or press Deploy). Remove any old `OUTPUT_URL` variable that points to another site.
3. Open your Railway domain: Status should say **sending**. Within a minute the HostHerb watch link plays.

## Optional Railway variables
- `OUTPUT_URL` — another page to capture (default https://moviemaxlivetv.nexusplatformafrica.workers.dev/output)
- `RTMP_URL`, `STREAM_KEY` — another streaming server
- `SCREEN_WIDTH`, `SCREEN_HEIGHT`, `FPS`, `VIDEO_BITRATE`, `AUDIO_BITRATE`

Give the service at least 1 GB of memory. Railway charges by usage, so 24/7 sending is not free.
Only run one broadcaster (or the playout engine) at a time — two senders on one stream key fight each other.
