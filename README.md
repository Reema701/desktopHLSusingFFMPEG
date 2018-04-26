# desktopHLSusingFFMPEG
Stream the desktop over the internet using ffmpeg, access the player content using html player accessing HLS content.

# Steps
1. Install ffmpeg on the machine, on which you wan to grab desktop.
2. Open the command line, and run the below code (Starts grabbing desktop to hosted server location) :

ffmpeg -f gdigrab -r 30 -i desktop -c:v libx264 -g 25 -c:a libfdk_aac  -ac 2 -hls_time 1 -hls_list_size 4 -hls_wrap 8 -s 1366x768 /
-strict -2 -ab 128k -ar 44100 C:/xampp/htdocs/hls/playlist.m3u8

3. You should already have a server hosted (apache / xampp / abyss )
4. check for content getting created at C:/xampp/htdocs/hls/playlist.m3u8 (you should have playlist as in m3u8, .ts segments)
5. keep the player.html in the location : C:/xampp/htdocs/hls/player.html
6. access the live stream using on your browser : http://localhost/hls/player.html

You should be able to see the livestream.

# Conclusion
You are able to see 5 seconds delay in my screenshot because, I was using the same machine to start ffmpeg (and grabbing desktop), and viewing the livestream.
This delay might get increased by 5 more seconds in case you stream across machines within same network, and by 7 more in case across internet.
