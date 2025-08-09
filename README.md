# MoviesDatabase API

## API Overview
The MoviesDatabase API provides access to comprehensive and regularly updated data for over **9 million titles**, including movies, series, and episodes.  
- **Recent titles** are updated weekly  
- **Ratings and episode data** are updated daily  
- Supports searching by keyword, title, aka's, and retrieving detailed data on titles, ratings, actors, seasons, and episodes  
- Includes utility endpoints for genres, title types, and curated lists like *Top 250 movies* or *Most Popular Series*  

---

## Version
**v1.0** (as per the current API documentation)

---

## Available Endpoints

### Titles
- **`GET /titles`** – Returns an array of titles based on filters/sorting parameters.  
- **`GET /x/titles-by-ids`** – Returns titles by a provided list of IMDb IDs.  
- **`GET /titles/{id}`** – Returns details of a single title.  
- **`GET /titles/{id}/ratings`** – Returns rating and votes count for a title.

### Seasons and Episodes
- **`GET /titles/series/{id}`** – Lists all episodes for a series (IDs, episode numbers, season numbers).  
- **`GET /titles/seasons/{id}`** – Returns the number of seasons for a series.  
- **`GET /titles/series/{id}/{season}`** – Lists episodes for a specific season.  
- **`GET /titles/episode/{id}`** – Returns detailed information about a specific episode.

### Upcoming Titles
- **`GET /titles/x/upcoming`** – Returns upcoming titles based on filters.

### Search
- **`GET /titles/search/keyword/{keyword}`** – Search titles by keyword.  
- **`GET /titles/search/title/{title}`** – Search titles by exact or partial title.  
- **`GET /titles/search/akas/{aka}`** – Search titles by aka (exact match only).

### Actors
- **`GET /actors`** – Returns actors based on filters.  
- **`GET /actors/{id}`** – Returns detailed information for an actor.

### Utilities
- **`GET /title/utils/titleType`** – Returns available title types.  
- **`GET /title/utils/genres`** – Returns available genres.  
- **`GET /title/utils/lists`** – Returns available predefined title lists.

---

## Request and Response Format

**Example Request**
```http
GET /titles?genre=Action&year=2022&limit=5
Host: api.example.com
Authorization: Bearer YOUR_API_KEY
