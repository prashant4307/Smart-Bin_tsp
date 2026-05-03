# SmartBin TSP

A Node.js backend server for a smart waste management system in Chennai. It helps city authorities track, manage, and optimize the collection of waste bins using route optimization (TSP).

## Features

- **Bin Management (CRUD):**
  - Add, view, update, and delete bins with location, area, and fill level.
- **Route Optimization:**
  - Uses a Nearest Neighbor TSP algorithm to find the shortest route for collecting bins with fill level above 70%.
- **MySQL Integration:**
  - Stores all bin data in a MySQL database.
- **REST API:**
  - Endpoints for frontend/dashboard to interact with bin data and routes.
- **Static File Serving:**
  - Serves HTML, CSS, JS, and other static files for dashboards.

## Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/prashant4307/Smart-Bin_tsp.git
   cd Smart-Bin_tsp
   ```

2. **Install dependencies:**
   ```bash
   npm install mysql2
   ```

3. **Configure MySQL:**
   - Create a database named `smart_waste_db`.
   - Create a table:
     ```sql
     CREATE TABLE bins (
       id INT AUTO_INCREMENT PRIMARY KEY,
       location_lat DOUBLE NOT NULL,
       location_lng DOUBLE NOT NULL,
       area VARCHAR(255) NOT NULL,
       fill_level INT NOT NULL
     );
     ```
   - Update the MySQL credentials in `server.js` if needed.

4. **Run the server:**
   ```bash
   node server.js
   ```
   The server runs on [http://localhost:3000](http://localhost:3000).

## API Endpoints

- `GET /api/bins` — Get all bins
- `POST /api/bins` — Add a new bin
- `PUT /api/bins/:id/fill` — Update fill level of a bin
- `DELETE /api/bins/:id` — Delete (collect) a bin
- `GET /api/routes/optimize` — Get optimized collection route for bins with fill level > 70%

## Project Structure

- `server.js` — Main server and API logic
- `gov-dashboard.html` — (Optional) Dashboard frontend
- Static files (HTML, CSS, JS) can be served from the project root

## License

MIT

---

**SmartBin TSP** helps make waste collection smarter and more efficient for cities!
