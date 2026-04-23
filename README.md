# 🎵 TikTok Downloader API

A fast and reliable TikTok video downloader API that fetches TikTok videos without watermarks.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![API Status](https://img.shields.io/badge/API-Online-success)](https://tiktok-downbloder.vercel.app)

## ✨ Features

- 🚀 **Fast & Reliable** - Quick response times with minimal latency
- 💧 **No Watermark** - Download videos without TikTok watermarks
- 🎵 **Audio Extraction** - Separate music/audio download links
- 📊 **Video Statistics** - Fetch likes, comments, and share counts
- 👤 **Author Information** - Get creator details and profile pictures
- 🔄 **RESTful API** - Simple JSON-based API interface
- ⚡ **Serverless** - Deployed on Vercel for high availability
- 🆓 **Free to Use** - No API key required

## 📡 API Endpoint

```
GET https://tiktok-downbloder.vercel.app/?url={TIKTOK_VIDEO_URL}
```

### Parameters

| Parameter | Type   | Required | Description                    |
|-----------|--------|----------|--------------------------------|
| `url`     | string | Yes      | Full TikTok video URL          |

## 🚀 Quick Start

### Example Request

```bash
curl "https://tiktok-downbloder.vercel.app/?url=https://www.tiktok.com/@akhi79874/video/7619227493748247828"
```

### JavaScript/Node.js

```javascript
const url = 'https://www.tiktok.com/@akhi79874/video/7619227493748247828';
const apiUrl = `https://tiktok-downbloder.vercel.app/?url=${encodeURIComponent(url)}`;

fetch(apiUrl)
  .then(response => response.json())
  .then(data => {
    console.log('Video URL:', data.result.raw.result.video);
    console.log('Music URL:', data.result.raw.result.music);
    console.log('Author:', data.result.raw.result.author.nickname);
  })
  .catch(error => console.error('Error:', error));
```

### Python

```python
import requests

tiktok_url = "https://www.tiktok.com/@akhi79874/video/7619227493748247828"
api_url = f"https://tiktok-downbloder.vercel.app/?url={tiktok_url}"

response = requests.get(api_url)
data = response.json()

if data['success']:
    video_url = data['result']['raw']['result']['video']
    music_url = data['result']['raw']['result']['music']
    print(f"Video: {video_url}")
    print(f"Music: {music_url}")
```

### PHP

```php
<?php
$tiktokUrl = "https://www.tiktok.com/@akhi79874/video/7619227493748247828";
$apiUrl = "https://tiktok-downbloder.vercel.app/?url=" . urlencode($tiktokUrl);

$response = file_get_contents($apiUrl);
$data = json_decode($response, true);

if ($data['success']) {
    echo "Video: " . $data['result']['raw']['result']['video'] . "\n";
    echo "Music: " . $data['result']['raw']['result']['music'] . "\n";
}
?>
```

## 📋 Response Format

### Success Response

```json
{
  "success": true,
  "id": "5bc8ta",
  "developer": "Sujoy Paul",
  "github": "https://github.com/devlopersujoy",
  "result": {
    "provider": "tiktokapi-src",
    "version": "v2",
    "raw": {
      "status": "success",
      "result": {
        "type": "video",
        "desc": "#foryou #foryoupage ❤️❤️",
        "author": {
          "avatar": "https://...",
          "nickname": "Akhi"
        },
        "statistics": {
          "likeCount": "187.3K",
          "commentCount": "1.6K",
          "shareCount": "1K"
        },
        "video": "https://tikcdn.io/ssstik/...",
        "music": "https://tikcdn.io/ssstik/m/..."
      }
    }
  }
}
```

### Response Fields

| Field                              | Type    | Description                           |
|------------------------------------|---------|---------------------------------------|
| `success`                          | boolean | Request success status                |
| `id`                               | string  | Unique request identifier             |
| `result.raw.result.video`          | string  | Direct video download URL (no watermark) |
| `result.raw.result.music`          | string  | Audio/music download URL              |
| `result.raw.result.desc`           | string  | Video description/caption             |
| `result.raw.result.author.nickname`| string  | Creator's display name                |
| `result.raw.result.author.avatar`  | string  | Creator's profile picture URL         |
| `result.raw.result.statistics`     | object  | Video engagement stats                |

## 🛠️ Tech Stack

- **Runtime:** Node.js / Vercel Serverless Functions
- **API Provider:** TikTok API Source (v2)
- **CDN:** TikCDN for media delivery
- **Hosting:** Vercel

## 📝 Use Cases

- Build TikTok download websites/apps
- Create TikTok content archives
- Analyze TikTok engagement metrics
- Extract audio for remixing
- Research & data analysis projects
- Social media management tools

## ⚠️ Rate Limiting

This API does not currently enforce rate limits, but please use responsibly:

- Recommended: Max 6000 requests/minute
- Avoid automated scraping of large video batches
- Cache responses when possible

## 📄 License

This project is licensed under the MIT License 

## 👨‍💻 Developer

**Sujoy Paul**

- GitHub: [@devlopersujoy](https://github.com/devlopersujoy)
- API: [tiktok-downbloder.vercel.app](https://tiktok-downbloder.vercel.app)

## ⚖️ Legal Disclaimer

This tool is for educational purposes only. Please respect TikTok's Terms of Service and copyright laws. Users are responsible for ensuring they have the right to download and use any content.

- Only download videos you have permission to use
- Respect content creators' intellectual property
- Do not use for commercial purposes without proper authorization
- TikTok® is a registered trademark of ByteDance Ltd.

## 🌟 Show Your Support

If this project helped you, please give it a ⭐️ on GitHub!

---

<div align="center">

Made with ❤️ by [Sujoy Paul](https://github.com/devlopersujoy)

</div>
