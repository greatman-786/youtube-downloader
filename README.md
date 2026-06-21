📹 YouTube Downloader

A fast and simple web app that allows users to download YouTube videos in 
multiple formats and quality options — built and deployed on Vercel.

🌐 **Live Demo:** https://youtube-downloader-seven-pied.vercel.app

---

## 🚀 Features

- 📥 **Download YouTube videos** in multiple formats
- 🎬 **Multiple quality options** — 360p, 720p, 1080p
- 🎵 **Audio extraction** — download MP3 from any video
- ⚡ **Fast processing** — quick download generation
- 📱 **Fully responsive** — works on desktop and mobile
- 🔗 **Simple UI** — just paste the URL and download

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Next.js / React | Frontend framework |
| yt-dlp | YouTube video processing |
| Vercel | Deployment and hosting |
| Tailwind CSS | Styling and UI |

---

## 🔄 How It Works
User Pastes YouTube URL

↓

App Validates the URL

↓

yt-dlp Fetches Video Info

↓

User Selects Format & Quality

↓

Video Downloaded & Delivered

---

## ⚙️ Setup & Installation

1. Clone the repository
```bash
git clone https://github.com/greatman-786/youtube-downloader.git
cd youtube-downloader
```

2. Install dependencies
```bash
npm install
```

3. Run locally
```bash
npm run dev
```

4. Open `http://localhost:3000`

---

## 📁 Project Structure
youtube-downloader/

│

├── pages/          # Next.js pages

├── components/     # Reusable UI components

├── styles/         # Tailwind CSS styles

├── lib/            # yt-dlp integration logic

└── README.md       # Project documentation

---

## ⚡ Challenges & How I Solved Them

### 1. 🚀 Serverless Environment Limitations
**Problem:** yt-dlp is a command-line tool that doesn't run reliably inside 
Vercel's serverless functions — it requires a persistent runtime environment 
which serverless functions don't provide.  
**Solution:** Identified the architectural mismatch early and documented it 
clearly. For a production version, the solution would be to move the yt-dlp 
processing to a **dedicated backend server** (e.g. a VPS or containerised 
service) while keeping the frontend on Vercel.

### 2. ⏱️ Download Timeout Issues
**Problem:** Large video files took too long to process, causing Vercel's 
serverless function timeout limits to be hit before the download completed.  
**Solution:** Implemented a **streaming approach** where video data is piped 
directly to the user rather than being fully processed server-side first — 
reducing timeout risk significantly.

### 3. 📱 Mobile Download Compatibility
**Problem:** Download links behaved differently across browsers and mobile 
devices — some opened in a new tab instead of triggering a download.  
**Solution:** Used proper **Content-Disposition headers** and download attribute 
handling to ensure consistent download behaviour across all browsers and devices.

### 4. 🔗 URL Validation
**Problem:** Users pasting invalid or non-YouTube URLs caused the app to crash 
with unhelpful error messages.  
**Solution:** Added **frontend URL validation** before sending requests to the 
backend — checking for valid YouTube URL patterns and showing clear error 
messages to guide the user.

---

## 💡 Use Cases

- Downloading YouTube videos for offline viewing
- Extracting audio from YouTube videos
- Saving educational content for offline access
- Content creators downloading reference material

---

## 📌 Note

This app is built for **educational and personal use only**. Always respect 
YouTube's Terms of Service and content creators' rights when downloading videos.

---

## 🙋‍♂️ Author

**Asad** — Software Engineer  
Building practical web applications for real-world use cases
