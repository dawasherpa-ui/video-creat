# Express Server

A simple Express.js server with basic routing and static file serving.

## Setup

1. Make sure you have Node.js installed on your machine
2. Install dependencies:
   ```
   npm install
   ```
3. Set up environment variables in a `.env` file:
   ```
   PORT=3000
   GEMINI_API_KEY=your_gemini_api_key
   BASE_URL=http://localhost:3000 | deployed url
   SUPABASE_URL=your_supabase_url
   SUPABASE_KEY=your_supabase_key
   FACEBOOK_PAGE_ID=your_facebook_page_id
   FACEBOOK_ACCESS_TOKEN=your_facebook_page_access_token
   ```

## Running the server

Start the server by running:
```
node server.js
```

The server will start on port 3000 by default. You can change this by setting the PORT environment variable.

## Available endpoints

- `GET /`: Serves the static HTML page
- `GET /api/status`: Returns server status as JSON
- `GET /image?text=YOUR_TEXT`: Generates an image with the specified text
- `GET /video?image=IMAGE_URL&audio=AUDIO_URL&duration=DURATION`: Generates a video from image and audio
- `POST /post-social`: Posts video content to social media platforms
- `POST /creator`: Creates and posts content to social media platforms

### POST /creator
Creates a video from text and audio and posts it to social media.

**Request Body:**
```json
{
  "type": "image",
  "text": "Dont just focus on the techinal things. Focus on What your developing also.",
  "audio": "https://example.supabase.co/storage/v1/object/public/audio/audio.mp3",
  "caption": "YOO testing"
}
```

**Parameters:**
- `type` (string): Content type - currently only "image" is supported
- `text` (string): Text to display on the generated image
- `audio` (string): URL to the audio file that will be combined with the image
- `caption` (string): Caption to use when posting to social media
- `duration` (number, optional): Duration in seconds, default is 10
- `aspectratio` (string, optional): Aspect ratio for the output, default is "9:16"

## Features

- Express.js server
- Static file serving
- JSON API endpoint
- Body parsing middleware
- Image generation with Google Gemini API
- Video generation with FFmpeg
- Social media posting to Facebook/Instagram


[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy?repo=https://github.com/dawasherpa-ui/video-creat)
