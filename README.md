## **Backend README** (Harmony Vault Backend)

---

# **Harmony Vault Backend**
### A tool for managing and storing musician data, biographical data, and audio files to streamline workflows for WMUC radio shows.

---

## **Overview**
Harmony Vault is the backend service for the Harmony Vault project, built using **Spring Boot**. It provides a robust RESTful API for storing, retrieving, and managing musician-related data such as biographies, audio files, and other metadata.

This project was developed to **ease workflows** for radio show hosts on [WMUC 90.5 FM](https://www.wmuc.umd.edu/show/282907), enabling efficient management of curated musician content.

---

## **Key Features**
- RESTful APIs for **CRUD operations** on:
   - Musician data
   - Biographical information
   - Audio file storage and retrieval
- **Audio Upload Support**: Supports uploading audio files and stores references for easy access.
- **Pagination and Sorting**: Implements paginated and sorted results using Spring Data.
- **Stable JSON Serialization**: Custom `PageSerializationMode` ensures consistent response structures.
- **File System Storage**: Audio and photo files are stored in the filesystem with URL generation for retrieval.

---

## **Project Structure**
```plaintext
src/
 ├── main/
 │   ├── java/com/example/HarmonyVault
 │   │   ├── config/           (Application configurations)
 │   │   ├── domain/           (Entity classes)
 │   │   ├── repo/             (Repositories for database interaction)
 │   │   ├── resource/         (Controllers for REST endpoints)
 │   │   └── service/          (Service layer for business logic)
 │   └── resources/            (Application properties)
 └── test/                     (Unit and integration tests)
```

---

## **Dependencies**
- **Spring Boot** (Web, Data JPA)
- **PostgreSQL** (Database)
- **Lombok** (Code simplification)
- **Mockito** (Testing)
- **Jackson** (JSON Serialization)

---

## **Setup and Installation**

### **Prerequisites**
- Java 17
- Maven
- PostgreSQL installed and running

### **Steps:**
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/harmony-vault-backend.git
   cd harmony-vault-backend
   ```

2. Set up the database:
   - Create a PostgreSQL database named `harmony_vault`.
   - Update `application.properties` with your database credentials.

3. Build and run the project:
   ```bash
   mvn spring-boot:run
   ```

4. Access the application:
   - API base URL: `http://localhost:8080`
   - Example endpoint: `GET /artists`

---

## **Endpoints**
| Method | Endpoint                     | Description                     |
|--------|-----------------------------|---------------------------------|
| GET    | `/artists`                  | Fetch all artists (paginated)   |
| POST   | `/artists`                  | Create a new artist             |
| GET    | `/artists/{id}`             | Fetch a specific artist         |
| POST   | `/artists/audio/{id}`       | Upload audio files              |
| GET    | `/artists/audio-download/{filename}` | Download an audio file          |

---

## **Troubleshooting**
- If audio files are not appearing, ensure:
   - The file upload directory exists and is writable.
   - `@ElementCollection` for `audioPaths` is correctly mapped in the `Artist` entity.

---

## **Contributing**
Contributions are welcome! Fork the repository, make changes, and submit a pull request.

---

## **License**
This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).

---

