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

