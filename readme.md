# 🔄 Dynamic Thread Optimizer for Video Downloads

This project provides a smart Python-based video downloader using [`yt-dlp`](https://github.com/yt-dlp/yt-dlp), enhanced with real-time **thread optimization** to maximize download speed.

## 🚀 Features

- ✅ Downloads video + audio in best quality
- ⏫ Adjusts number of threads during download based on real-time speed
- 📈 Tracks and prints download progress and speed
- 🛠️ Easy to run with a single URL argument

## 📦 Requirements

- Python 3.7+
- [`yt-dlp`](https://github.com/yt-dlp/yt-dlp)

Install dependencies with:

```bash
pip install yt-dlp

## 🧠 How It Works
	1.	Starts downloading using yt-dlp with an initial number of threads.
	2.	Every 2 seconds, checks if download speed increased or decreased.
	3.	If speed drops more than 10% → decreases threads.
	4.	If speed increases more than 10% → increases threads.
	5.	Optimizes dynamically until download is complete.

## 📂 File Overview

File	Description
main.py	Main script with dynamic thread optimization
script1.py	(Optional) Additional example scripts
script2.py	(Optional) Additional example scripts

## 🧪 Usage

python main.py <VIDEO_URL>

Example:

python main.py https://www.youtube.com/watch?v=xxxx

## 🛠️ Configuration Options

Inside main.py, you can tweak:
	•	max_threads (default: 16)
	•	min_threads (default: 1)
	•	http_chunk_size
	•	Output template (filename pattern)

## 📌 Notes
	•	If video or audio format detection fails, it will fallback to 'bestvideo+bestaudio/best'.
	•	Tested with YouTube, but yt-dlp supports many platforms.

⸻

🤝 Contributing

Pull requests welcome. Ideas welcome. Help optimize better thread logic? Let’s do it 💡

⸻

📜 License

MIT — free to use and modify.
