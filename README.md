# Student management system - Laboration 1

A simple JAX-RS application using a Payara server for student managing in a MySQL database.

## Getting Started

### Deployment

1. Download [Payara.](https://www.payara.fish/downloads)
2. Clone [this repository](https://github.com/albindubech/student-management-system)
   by following [this article.](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository)
3. Install Payara Platform Tools Plugin.
5. Download [Docker.](https://www.docker.com/products/docker-desktop)
6. Run the command below in CMD and run the container in Docker: <br/>
   docker run --name mysql -e MYSQL_ROOT_PASSWORD=my_secret_password -e
   'MYSQL_ROOT_HOST=%' -e MYSQL_DATABASE=test -e MYSQL_USER=user -e
   MYSQL_PASSWORD=password -p 3306:3306 mysql:latest
7. After following these steps you should be able to run the application using insomnia and the following commands.


Create a student
- 
**POST** http://localhost:8080/student-management-system/api/v1/students

- Enter the student credentials in JSON format as shown below:
  Mandatory fields: **firstName, lastName, email.**
```
   {
    "firstName" : "Name",
    "lastName" : "Lastname",
    "email" : "mail@mail.com",
    "phoneNumber" : "1234567890"
   }
```


Get all students**
- 
**GET** http://localhost:8080/student-management-system/api/v1/students

- Returns a list with all students added


Get student by ID
-
**GET** http://localhost:8080/student-management-system/api/v1/students/{id}
- Returns student with the ID given in the URL.


Get all students by lastname
-
**GET** http://localhost:8080/student-management-system/api/v1/students/lastname?lastname={lastname}
- Returns a list of students with lastname added in the URL


Update student
- 
**PUT** http://localhost:8080/student-management-system/api/v1/students/{id}
- Updates student with given ID in the URL **_AND_** the JSON-body.

```
   {
    "firstName" : "Name",
    "lastName" : "Lastname",
    "email" : "mail@mail.com",
    "phoneNumber" : "1234567890"
   }
```

Delete student
-  
**DELETE** http://localhost:8080/student-management-system/api/v1/students/{id}
- Deletes student with ID given in URL.
