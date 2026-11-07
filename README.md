# Tourist Records API – Token Validation

## Requirements
- Java 17+
- Maven (or import as Existing Maven Project in Spring Tool Suite)
- MySQL running

## Database setup
Run in MySQL:
```sql
CREATE DATABASE tourist_db;
```
Open `src/main/resources/application.properties` and replace `YOUR_MYSQL_PASSWORD` with your MySQL password.

## Run in STS
1. Extract this ZIP.
2. STS → File → Import → Maven → Existing Maven Projects.
3. Select the extracted `TouristTokenValidation` folder → Finish.
4. Right-click project → Run As → Spring Boot App.

## API
- GET `http://localhost:8080/api/tourists`
- Swagger UI: `http://localhost:8080/swagger-ui.html`
- Header name: `Token`
- Valid demo token: `tourist-access-123` (pre-generated; no token generation endpoint)

### Swagger testing
In Swagger UI, open `GET /api/tourists`, click **Try it out** and enter the `Token` header as `tourist-access-123`. Execute → `200 OK` with tourist JSON list.
Missing/wrong token → `500 Internal Server Error`, message `Unauthorized: Invalid Token Provided`.

## Sample records
On first startup, three sample tourist records are inserted if the table is empty.

> For real applications, avoid hardcoded tokens and returning all records without pagination. This token is only for the lab exercise.
