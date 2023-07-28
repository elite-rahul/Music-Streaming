# Music Streaming API
_______


## Framework Used
* Spring Boot
----
## Dependencies
The following dependencies are required to run the project:


* Spring Web
* Spring Data JPA
* MySQL Driver
* Lombok
* Validation
* Swagger
 ----
## Language used
* Java (Version: 17)
* 
----

Sure, let's create a simplified version of a Music Streaming API using Spring Boot. We'll focus on the core functionalities related to users, playlists, and songs. For brevity, we won't include authentication and role-based access control in this example.

Framework Used
Spring Boot
Dependencies
To keep things simple, we'll only use the following dependencies:

Spring Web
Spring Data JPA
H2 Database (in-memory database for testing)
Language Used
Java (Version: 17)
Data Model
We will have three main entities: User, Playlist, and Song. Here's how the data models will look:

User Model:
java
Copy code
public class User {
    private Long id;
    private String username;
    private String email;
    // Other user properties, such as password (it should be hashed and not shown here for security).
}
Playlist Model:
java
Copy code
public class Playlist {
    private Long id;
    private String playlistName;
    private List<Song> songs;
    private User user; // The user who owns this playlist.
}
Song Model:
java
Copy code
public class Song {
    private Long id;
    private String songTitle;
    private String artist;
    private User user; // The user who uploaded this song.
}
API Endpoints
We'll create API endpoints to perform CRUD operations on users, playlists, and songs.

User Endpoints:

POST /users: Create a new user.
GET /users/{id}: Get user details by ID.
PUT /users/{id}: Update user details by ID.
DELETE /users/{id}: Delete a user by ID.
Playlist Endpoints:

POST /playlists: Create a new playlist.
GET /playlists/{id}: Get playlist details by ID.
PUT /playlists/{id}: Update playlist details by ID.
DELETE /playlists/{id}: Delete a playlist by ID.
Song Endpoints:

POST /songs: Upload a new song.
GET /songs/{id}: Get song details by ID.
PUT /songs/{id}: Update song details by ID.
DELETE /songs/{id}: Delete a song by ID.

## Data Model

<br>

* User Model
```
Id : integer
password : string
email : string
role : Role

```

* Playlist Model
```
playlistId : Long
playListName: String
songs : songs
User : user
```
* Song Model
```
SongId : Long
SongTitle : String
Artist : String 
user: User

* Structure of project
* *- src/
  - main/
    - java/
      - com.example.musicstreaming/
        - controller/
          - UserController.java
          - PlaylistController.java
          - SongController.java
        - model/
          - User.java
          - Playlist.java
          - Song.java
        - repository/
          - UserRepository.java
          - PlaylistRepository.java
          - SongRepository.java
        - service/
          - UserService.java
          - PlaylistService.java
          - SongService.java
        - MusicStreamingApplication.java


```



## Data Flow

1. The user at client side sends a request to the application through the API endpoints.
2. The API receives the request and sends it to the appropriate controller method.
3. The controller method makes a call to the method in service class.
4. The method in service class builds logic and retrieves or modifies data from the database, which is in turn given to controller class
5. The controller method returns a response to the API.
6. The API sends the response back to the user.

---

## DataBase Used
* SQL database
```

We have used Persistent database to implement CRUD Operations.
```
---
Please note that this is a simplified version of a Music Streaming API for demonstration purposes. In a real-world scenario, you would need to consider security, authentication, authorization, pagination, and error handling, among other things. Additionally, you could use a more robust database like MySQL or PostgreSQL for production use.





you can visit for testing the API SWagger Link
http://13.127.113.144:8080/swagger-ui/index.html#/
