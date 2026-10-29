You will need the **yt-dlp** library, as it is currently the most reliable and actively maintained tool for downloading YouTube videos in Python.

Step 1:

```bash
pip install yt-dlp
```

Step 2:
Save the following code in a Python file (e.g., downloader.py) and run it:

```python
import yt_dlp

def download_youtube_video(video_url):
    # Options for the downloader: requests the best quality mp4 format
    ydl_opts = {
        'format': 'bestvideo[ext=mp4]+bestaudio[ext=m4a]/best[ext=mp4]/best',
        'outtmpl': '%(title)s.%(ext)s', # Saves the file with the video's title
        'quiet': False
    }

    try:
        print(f"Starting download for: {video_url}")
        with yt_dlp.YoutubeDL(ydl_opts) as ydl:
            ydl.download([video_url])
        print("Download completed successfully!")
    except Exception as e:
        print(f"An error occurred during download: {e}")

if __name__ == "__main__":
    url = input("Enter the YouTube video URL: ")
    download_youtube_video(url)

```


How it works:

- The script asks you to paste the YouTube URL.
- It sets options (ydl_opts) to automatically fetch the best available video and audio streams and merge them into an MP4 file.
- The downloaded file will be saved in the same folder where you run the script, named exactly after the YouTube video's title.


## Resolving some of errors while running above code

### 1. WARNING: [youtube] No supported JavaScript runtime could be found. Only deno is enabled by default; to use another runtime add  --js-runtimes RUNTIME[:PATH]  to your command/config. YouTube extraction without a JS runtime has been deprecated, and some formats may be missing. See  https://github.com/yt-dlp/yt-dlp/wiki/EJS  for details on installing one
[youtube] 91v67mJgIVU: Downloading visionos player API JSON

Solution:  on powershell execute following command to configure java script runtime:
**irm https://deno.land/install.ps1 | iex**

example:
```text
irm https://deno.land/install.ps1 | iex
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100 40.9M  100 40.9M    0     0  6954k      0  0:00:06  0:00:06 --:--:-- 8929k
Deno was installed successfully to C:\Users\Lenovo\.deno\bin\deno.exe
Run 'deno --help' to get started
Stuck? Join our Discord https://discord.gg/deno
```
