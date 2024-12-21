# YouTube API Integration Project

This project integrates with the YouTube API to fetch video details and comments based on a provided video ID. It is built using Node.js, Express.js, and EJS for server-side rendering.

### Features

- Fetch video metadata (title, description, likes, views).
- Fetch video comments with pagination.
- Handles API rate limits with proper error messages.
- Includes a preloader and user-friendly interface for displaying video data.

### Prerequisites

1. Node.js installed on your machine.
2. A valid YouTube Data API key.

### Installation

1. Clone the repository:

   git clone <repository-url>
   cd <repository-folder>

2. Install dependencies:

   npm install

3. Create a `.env` file in the root folder with the following content:

   PORT=3000
   YOUTUBE_API_KEY=your_youtube_api_key

4. Run the application:

   npm start

5. Access the application:
   Open your browser and navigate to `http://localhost:3000`.

### Usage

1. Enter the YouTube video ID in the form.
2. Click the Get Video Info button to fetch the video's details.
3. View metadata such as title, description, likes, and comments.

### File Structure

├── src/
│ ├── app.ts # Initializes the Express app
│ ├── server.ts # Starts the server
│ ├── controllers/
│ │ └── youtube.controller.ts # Handles API requests
│ ├── services/
│ │ └── youtube.service.ts # Logic for interacting with YouTube API
│ ├── routes/
│ │ └── youtube.routes.ts # Defines application routes
│ ├── utils/
│ │ └── logger.ts # Configures Winston logging
│ ├── public/ # Static files (CSS, JS)
│ ├── views/ # EJS templates
│ ├── .env # Environment variables
│ └── package.json # Dependencies and scripts

### Logging

- Errors and system messages are logged using `winston`.
- Logs can be found in `error.log` for error-level logs.

### Contributing

Feel free to contribute by forking the repository and submitting a pull request. Make sure to follow the existing code style and structure.

## Code Documentation

### Overview

The application is structured to maintain modularity and scalability:

- Routes: API endpoints (`/api/youtube`).
- Controllers: Handle request-response logic.
- Services: Interact with the YouTube Data API.
- Views: EJS templates for rendering the frontend.

### Key Components

#### 1. youtube.controller.ts

Handles API requests for fetching video details and comments.

- `getVideoDetails`: Fetches video metadata from the YouTube API.
- `getVideoComments`: Fetches comments, handles pagination.

#### 2. youtube.service.ts

Contains logic for interacting with the YouTube API.

- `getVideoInfo(videoId)`: Fetches video details.
- `getVideoComments(videoId)`: Fetches comments, handles rate limits.

#### 3. logger.ts

Provides a centralized logging mechanism using Winston.

- Logs are stored in `error.log` for errors.
- Console transport used for development debugging.

### API Endpoints

1. GET /api/youtube/video/:videoId

   - Fetch details of a video by its ID.
   - Response: `{ title, description, viewCount, likeCount }`.

2. GET /api/youtube/comments/:videoId
   - Fetch comments for a video.
   - Response: `[{ author, comment, likeCount }]`.

### EJS Frontend

The `index.ejs` file renders a simple UI with:

- A form to input YouTube video IDs.
- Sections for displaying metadata and comments.
- Spinner for preloading state.

Thanks To Aella For This Great Opportunity
