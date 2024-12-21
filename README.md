Here’s the finalized version of your README file for easy copy-and-paste:

---

# YouTube API Integration Project

This project integrates with the YouTube API to fetch video details and comments using a provided video ID. Built with **Node.js**, **Express.js**, and **EJS**, it delivers a responsive and user-friendly interface.

## Features

- Fetch video metadata (title, description, likes, views).  
- Retrieve video comments with pagination.  
- Handle API rate limits with clear error messages.  
- Preloader for smooth video data display.

## Prerequisites

1. **Node.js** installed.  
2. A valid **YouTube Data API key**.

## Installation

1. Clone the repository:  
   ```bash
   git clone <repository-url>
   cd <repository-folder>
   ```
2. Install dependencies:  
   ```bash
   npm install
   ```
3. Create a `.env` file in the root folder:  
   ```env
   PORT=3000
   YOUTUBE_API_KEY=your_youtube_api_key
   ```
4. Start the application:  
   ```bash
   npm start
   ```
5. Open your browser at `http://localhost:3000`.

## Usage

1. Enter a YouTube video ID in the form.  
2. Click **Get Video Info** to fetch video details.  
3. View metadata and comments.

## File Structure

```
src/
├── app.ts               # Initializes Express app
├── server.ts            # Starts the server
├── controllers/
│   └── youtube.controller.ts  # Handles API requests
├── services/
│   └── youtube.service.ts     # Logic for YouTube API
├── routes/
│   └── youtube.routes.ts      # Defines routes
├── utils/
│   └── logger.ts        # Winston logging
├── public/              # Static files
├── views/               # EJS templates
├── .env                 # Environment variables
└── package.json         # Dependencies and scripts
```

## Logging

- Managed using **Winston**.  
- Logs stored in `error.log` for errors and in the console during development.

## API Endpoints

### 1. **GET** `/api/youtube/video/:videoId`  
Fetch video metadata.  
**Response**:  
```json
{
  "title": "string",
  "description": "string",
  "viewCount": "number",
  "likeCount": "number"
}
```

### 2. **GET** `/api/youtube/video-comments/:videoId`  
Fetch video comments.  
**Response**:  
```json
[
  {
    "author": "string",
    "comment": "string",
    "likeCount": "number"
  }
]
```

## EJS Frontend

The frontend includes:  

- A form for entering video IDs.  
- Sections to display metadata and comments.  
- Preloader spinner for loading transitions.

## Contributing

1. Fork the repository.  
2. Create a new branch for your feature or fix.  
3. Submit a pull request with a detailed description.  

---

Thank you, **Aella**, for this wonderful opportunity to create and share this project.
