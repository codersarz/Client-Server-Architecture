# Simple Calculation Client-Server Model

## Project Overview

This project implements a client-server architecture model where a client sends requests to a server to perform simple calculations. The project leverages shared memory for communication between the client and server, with mutex locks used to handle concurrency issues in critical sections.

## Features

- **Client-Server Communication**: The client sends requests to the server to perform basic arithmetic operations such as addition, subtraction, multiplication, and division.
- **Shared Memory**: Facilitates efficient communication between the client and server.
- **Concurrency Handling**: Mutex locks ensure safe execution of critical sections, preventing race conditions and ensuring data integrity.

## Project Structure

- `client.c`: Contains the client-side code to send calculation requests to the server and retrieve the results.
- `server.c`: Contains the server-side code to process client requests, perform the calculations, and send the results back to the client.

## How It Works

1. **Shared Memory Setup**: The server initializes the shared memory segment and sets up a mutex lock for concurrency control.
2. **Client Request**: The client sends a request to the server with the desired operation and operands.
3. **Server Processing**: The server receives the request, performs the calculation, and stores the result in shared memory.
4. **Concurrency Control**: Mutex locks ensure that multiple clients can send requests simultaneously without causing data corruption.
5. **Result Retrieval**: The client reads the result from shared memory.

## How to Run

### Prerequisites

- A C compiler (e.g., GCC)
- POSIX-compliant system (Linux/Unix)

### Compilation

To compile the client and server programs:

```bash
gcc -o client client.c -lpthread
gcc -o server server.c -lpthread
