# Kaiburr-Task-1

# 

Java REST API example.

Implement an application in java which provides a REST API with endpoints for searching, creating and deleting “server” objects:
 ● GET servers. Should return all the servers if no parameters are passed. When server id
is passed as a parameter - return a single server or 404 if there’s no such a server.
 ● PUT a server. The server object is passed as a json-encoded message body.
 ● DELETE a server. The parameter is a server ID.
 ● GET (find) servers by name. The parameter is a string. Must check if a server name contains this string and return one or more servers found. Return 404 if nothing is found.
    “Server” objects should be stored in MongoDB database.
    
    

## **Prerequisites**

- Docker installed on your system
- Git installed on your system

## **Setup**

### **Step 1: Pull the latest MongoDB image**

```bash
docker pull mongo:latest
```

### **Step 2: Clone the repository**

```bash
git clone <repository_url>
```

### **Step 3: Navigate to the repository**

```bash
cd <repository_directory>
```

### **Step 4: Build the Docker image for the Spring Boot application**

```bash
docker build -t kaiburr-api .
```

### **Step 5: Open the terminal and navigate to `src/resources`**

```bash
cd src/resources
```

### **Step 6: Start the Docker Compose to run MongoDB and the Spring Boot application**

```bash
docker-compose up
```

### *****API Endpoints*****

## **`GET /servers/get`**

### **Description**

This endpoint retrieves a list of servers.

### **Request**

- Method: GET
- URL: **`http://localhost:9090/servers/get`**

### **Example**

**Request**

```bash
curl -X GET http://localhost:9090/servers/get
```
<img width="1440" alt="Screenshot 2023-09-14 at 9 04 18 PM" src="https://github.com/SUNIL-RAGHU/Kaiburr-Task1/assets/89726488/0125f14d-a1cd-4091-b359-32f05092adf5">

<img width="1440" alt="Screenshot 2023-09-14 at 9 05 04 PM" src="https://github.com/SUNIL-RAGHU/Kaiburr-Task1/assets/89726488/5ed34102-d3ca-4f3c-bef7-b4f232e6c181">



## **`POST /servers/create`**

### **Description**

This endpoint adds a new server.

### **Request**

- Method: POST
- URL: **`http://localhost:9090/servers/create`**
- Body: JSON Object

### **Example**

**Request**

```bash

curl -X POST -H "Content-Type: application/json" -d '{
 {
        "id": "2",
        "name": "abc",
        "language": "python",
        "framework": "Asp"
    }
}' http://localhost:9090/servers/create

```
<img width="1440" alt="Screenshot 2023-09-14 at 9 03 21 PM" src="https://github.com/SUNIL-RAGHU/Kaiburr-Task1/assets/89726488/bd3e77b9-5e93-4465-bb98-c7be4fe957b1">


## **`DELETE /servers/{id}`**

### **Description**

This endpoint deletes a server.

### **Request**

- Method: DELETE
- URL: **`http://localhost:9090/servers/{id}`**
- Path Variable: **`id`** (ID of the server to delete)

### **Example**

**Request**

```bash
curl -X DELETE http://localhost:9090/servers/3
```
<img width="1440" alt="Screenshot 2023-09-14 at 9 08 03 PM" src="https://github.com/SUNIL-RAGHU/Kaiburr-Task1/assets/89726488/c94fb789-9b7d-4ffb-bcc3-fe7c1de573c6">


## **`GET /servers/findbyname?name={name}`**

### **Description**

Retrieves a server by its name.

### **Request**

- Method: GET
- URL: **`http://localhost:9090/servers/findByName?name={name}`**
- Path Variable: **`name`** (Name of the server)

### **Example**

**Request**

```bash
curl -X GET **http://localhost:9090/servers/findByName?name=name**
```
<img width="1440" alt="Screenshot 2023-09-14 at 9 07 31 PM" src="https://github.com/SUNIL-RAGHU/Kaiburr-Task1/assets/89726488/485b46c8-6f91-4d99-82b3-3bc153dea0b1">

