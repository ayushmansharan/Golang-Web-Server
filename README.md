# Mini Web Server in Go

A very simple implementation of a Web Server using the Go programming language.

## Description

This project implements a basic Web Server using only the Go Standard Library. It was created for educational purposes to explore the fundamental functions provided by the standard library for networking, specifically the `net/http` package. The server is capable of:

- Listening on a specific port for incoming HTTP requests.
- Processing requests and replying with corresponding HTTP responses.

The application serves requests in two different ways:

1. **Handler functions**: Registers individual functions to process requests based on specific patterns.
2. **FileServer handler**: Serves HTTP requests with the contents of the file system rooted at `root`.

A Postman collection is included in this repository for testing the functionality of the Web server.

## Getting Started

### Dependencies

To build and compile the application, you will need:
- **Go version 1.18.x or higher**
- **Postman** (optional, for testing the provided requests)

### Installation

1. **Clone the repository**:
   ```sh
   git clone https://github.com/your-repo/mini-web-server-go.git
   ```
2. **Navigate to the project directory**:
   ```sh
   cd mini-web-server-go
   ```
3. **Initialize the Go module**:
   ```sh
   go mod init module_name
   go mod vendor
   ```
4. **Update the import reference** in `cmd/web-server/golang-web-server.go`:
   ```go
   "module_name/pkg/handler"
   ```
5. **Compile and build the application**:
   - On Unix-like systems:
     ```sh
     ./scripts/build.sh
     ```
   - Alternatively, run:
     ```sh
     go build -o ./bin/web-server cmd/web-server/golang-web-server.go
     ```
   This will generate a binary file named `web-server` in the `bin` directory.

### Running the Server

#### Using Handler Functions (default)
```sh
./bin/web-server
```
**Expected output:**
```
Initializing the handler functions...
Handler functions have been initialized
Listening on localhost:8081...
```

#### Using FileServer Handler
```sh
./bin/web-server -use-handler-functions=false
```
**Expected output:**
```
Initializing handler with FileServer
Handler has been initialized
Listening on localhost:8081...
```

## Testing

You can test the application using a **Web browser** or **Postman**.

### Web Browser
Open your browser and go to:
```
http://localhost:8081
```
If everything is working correctly, the index page should load. Check the source code for the requests supported by the Web server.

### Postman
1. Import the Postman collection provided in the repository.
2. Open the **Golang Mini Web Server** collection.
3. The collection contains two folders:
   - **Handler Functions Implementation**
   - **FileServer Handler Implementation**
4. Run the requests matching the current mode of the Web server.



