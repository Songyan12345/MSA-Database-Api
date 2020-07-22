# MSA-Database-API

This repository contains the URL for an API server that allows for creation and manipulation of Student and Address entities. 

The Azure-hosted APIs can be found [here](https://msa-student-address.azurewebsites.net/).

### Student table example:

![Student Table](/StudentTable.JPG)

### Address table example:

![Address Table](/AddressTable.JPG)

### API endpoints (Swagger):

#### Addresses:
* **GET /api/Addresses** retrieves all Addresses

* **POST /api/Addresses** creates a new Address and new Student

* **GET /api/Addresses/{id}** retrieves an Address with the specified **id**

* **PUT /api/Addresses/{id}** modifies an Address with the specified **id**

* **DELETE /api/Addresses/{id}** deletes an Address with the specified **id**

* **POST /api/Addresses/{studentId}** creates a new Address belonging to a specified student

* **PUT /api/Addresses/{addressId}/{studentId}** modifies an Address of a specified student

#### Students:
* **GET /api/Students** retrieves all Students

* **POST /api/Students** creates a new Student

* **GET /api/Students/{id}** retrieves a Student with the specified **id**

* **PUT /api/Students/{id}** modifies a Student with the specified **id**

* **DELETE /api/Students/{id}** deletes a Student with the specified **id**

<br />

![API Endpoints](/Swagger.JPG)

#### Notes:
* When POSTing (adding) a new Address without a specified Student, a new Student entity is automatically created. This is because an Address should not exist within a Student database if there are no Students that live at the Address
* When PUTting (modifying) a Student or Address entity, the respective **id** to be changed must be declared both as an input parameter and as a parameter for the **id** attribute within the request body. If either values are not present, or the two values are not equal, it will result in an error 
