![image](https://github.com/user-attachments/assets/a5f3b628-b238-459d-b558-6f88a5b3d735)

# Video Streaming Application

A React-based video streaming application that supports HLS (HTTP Live Streaming) playback using Video.js.

## Features

- HLS video streaming support
- Responsive video player
- Custom video controls
- Server-side video processing with FFmpeg

## Tech Stack

- Frontend:
  - React
  - Video.js
  - Vite
- Backend:
  - Node.js
  - Express
  - Multer (file uploads)
  - FFmpeg (video processing)

## Getting Started

1. Install dependencies:

```sh
# Install backend dependencies
npm install

# Install frontend dependencies
cd frontend
npm install

```
2.Start the Backend Server

```sh

npm start

```

3.Start the frontend development server:

```sh

cd frontend
npm run dev 

```

The application will be available at:

```

- Frontend: http://localhost:5173

- Backend: http://localhost:8000

```
# Video Streaming API

Backend service running on http://localhost:8000

## Endpoints 

- Upload Video:

Convert and upload a video file to HLS format.

```sh
POST /upload
Content-Type: multipart/form-data
```
- Parameter:
  -file (required): Video file to be uploaded
- Response:
```sh
{
  "message": "Video converted to HLS format",
  "videoUrl": "http://localhost:8000/uploads/courses/{lessonId}/index.m3u8",
  "lessonId": "uuid-string"
}
```

- Stream Video

Get HLS video stream.

```sh
GET /uploads/courses/{lessonId}/index.m3u8
```

- Parameters:
  -lessonId (required): UUID of the video lesson

- Responses:
  - Content-Type: application/x-mpegURL
  - Returns HLS manifest file
