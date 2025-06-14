#Github Repository link
https://github.com/MusaibUmer/Youtube-clone.git



# YouTube Clone Server

This is the backend server for the YouTube clone application. It provides RESTful APIs for user authentication, video management, comments, and user interactions.

## Prerequisites

Before you begin, ensure you have the following installed:
- Node.js (v14 or higher)
- MongoDB (local installation or MongoDB Atlas account)
- npm (Node Package Manager)

## Setup Instructions

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd youtube_clone-main/server
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Environment Setup**
   Create a `.env` file in the server directory with the following variables:
   ```
   MONGO=<your-mongodb-connection-string>
   PORT=8001
   ```
   
   For local MongoDB:
   ```
   MONGO=mongodb://localhost:27017/youtube_clone
   PORT=8001
   ```
   
   For MongoDB Atlas:
   ```
   MONGO=mongodb+srv://<username>:<password>@<cluster>.mongodb.net/<database>
   PORT=8001
   ```

4. **Start the server**
   ```bash
   npm start
   ```
   The server will start on port 8001 (or the next available port if 8001 is busy)

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - Login user
- `POST /api/auth/logout` - Logout user

### Users
- `GET /api/users/:id` - Get user profile
- `PUT /api/users/:id` - Update user profile
- `DELETE /api/users/:id` - Delete user account

### Videos
- `POST /api/videos` - Upload a new video
- `GET /api/videos/:id` - Get video details
- `PUT /api/videos/:id` - Update video details
- `DELETE /api/videos/:id` - Delete video
- `GET /api/videos/trend` - Get trending videos
- `GET /api/videos/random` - Get random videos
- `GET /api/videos/sub` - Get subscribed channels' videos

### Comments
- `POST /api/comments` - Add a comment
- `GET /api/comments/:videoId` - Get video comments
- `DELETE /api/comments/:id` - Delete a comment

## Dependencies

- express: Web framework
- mongoose: MongoDB object modeling
- dotenv: Environment variable management
- bcryptjs: Password hashing
- jsonwebtoken: JWT authentication
- cookie-parser: Cookie parsing middleware
- nodemailer: Email functionality

## Error Handling

The server includes global error handling middleware that returns errors in the following format:
```json
{
    "success": false,
    "message": "Error message",
    "status": 400
}
```

## Development

The server uses nodemon for development, which automatically restarts the server when changes are detected.

## Security

- Passwords are hashed using bcryptjs
- JWT tokens are used for authentication
- Environment variables are used for sensitive data
- Input validation is implemented on all routes

