# planetdistance-api
This is the backend service for a planetary distance calculator. 
It provides a REST API for calculating distances between planets on a given date using data from the **VSOP87 model**. 
The backend is implemented in **Java with Spring Boot** and exposes endpoints for retrieving supported planet names 
and computing distances.
For a frontend using this project see www.planetdistance.space

## Features
- Calculate the distance between two planets for a given date
- Retrieve a list of all available planets
- RESTful API with JSON responses
- Deployed on **Heroku**

## Technologies Used
- **Java 23**
- **Spring Boot** (REST API)
- **VSOP87 Astronomical Model** (for planetary positions)
- **Maven** (Dependency Management)

## Installation

### Prerequisites
- Java 23+
- Maven
- (Optional) Docker

### Clone the Repository
`git clone https://github.com/MichaSchrader/planetdistance-api.git && cd planetdistance-api`

### Build and Run
`mvn clean install && mvn spring-boot:run`

Or, using **Docker**:  
`docker build -t planetdistance-api . && docker run -p 8080:8080 planetdistance-api`

## API Endpoints

### Get Distance Between Two Planets
**GET** `/planet/distance/{firstPlanet}/{secondPlanet}/{dateInIsoFormat}`

**Example Request:**  
`curl -X GET "http://localhost:8080/planet/distance/Earth/Mars/2025-02-16"`

**Response Example (Distance in Kilometers):**  
`114598410`

### Get List of All Planets
**GET** `/planet/all`

**Example Request:**  
`curl -X GET "http://localhost:8080/planet/all"`

**Response Example:**  
`["Sun", "Mercury", "Venus", "Earth", "Mars", "Jupiter", "Saturn", "Uranus", "Neptune", "Moon"]`

## Deployment
The backend is deployed on **Heroku**. If you want to deploy it yourself:

`heroku create your-app-name && git push heroku main && heroku open`

## License
This project is licensed under the **GNU General Public License v3.0**. See the [LICENSE](LICENSE) file for details.  
