🌐 API Overview
The MoviesDatabase API provides a large catalog of movies with support for filtering, searching, and pagination. Key features include:

Fetching movie data by year, genre, or keywords
Detailed movie information (title, release year, genres, poster)
Pagination support for browsing
API key authentication for secure access
📌 API Version
v1

🔗 Available Endpoints
/titles – Fetch a list of movies (supports year, genre, and pagination filters)
/titles/{id} – Fetch details for a specific movie
/genres – Retrieve a list of all available genres
📄 Request and Response Format
Example Request
GET /titles?year=2020&genre=Action&page=1
Host: moviesdatabase.p.rapidapi.com
X-RapidAPI-Key: YOUR_API_KEY
X-RapidAPI-Host: moviesdatabase.p.rapidapi.com
Example Response
{
  "results": [
    {
      "id": "tt1234567",
      "titleText": { "text": "Example Movie" },
      "releaseYear": { "year": 2020 },
      "primaryImage": { "url": "https://image.url/poster.jpg" },
      "genres": { "genres": [{ "text": "Action" }] }
    }
  ],
  "page": 1,
  "total_pages": 50
}
🔑 Authentication
Uses API Key authentication

Pass API key via request headers:

X-RapidAPI-Key: YOUR_API_KEY
X-RapidAPI-Host: moviesdatabase.p.rapidapi.com
API keys are stored in .env.local to prevent exposure

⚠️ Error Handling
400 Bad Request – Invalid parameters or missing required fields
401 Unauthorized – Missing or invalid API key
404 Not Found – Resource does not exist
429 Too Many Requests – Rate limit exceeded
500 Server Error – API server issues
Implementation in Code:

Wrap API calls in try/catch
Check response.ok before processing data
Use loading and error UI states
📊 Usage Limits and Best Practices
Rate Limits: API has request caps per minute/hour (see provider’s docs)
Pagination: Use page parameter to fetch results gradually
Caching: Store frequent queries client-side to reduce API calls
Error Boundaries: Gracefully handle failures without breaking the app
Secure Keys: Always keep API keys in environment variables