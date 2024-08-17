# Redis Worker Queue Implementation

## Overview

This project demonstrates a robust worker queue system using Redis, with an Express.js backend. The system is designed to efficiently manage tasks, ensuring that work is distributed across available workers. If a worker crashes, tasks remain in the queue until a worker becomes available again, simulating a real-world scenario.

## Features

- **Task Queue**: All incoming tasks are stored in a Redis queue, managed by the Express backend.
- **Worker Distribution**: Tasks are randomly assigned to available workers, ensuring balanced load distribution.
- **Crash Recovery**: If a worker crashes, tasks remain in the queue until the worker is back online, at which point tasks are reassigned.

## Prerequisites

- Docker installed on your machine
- Node.js and npm installed

## Setup Instructions
### 1. Start Redis

Begin by launching a fresh Redis instance. You can use Docker to spin up Redis:

```bash
docker run --name my-redis -p 6379:6379 -d redis
```
### 2. Run the Express Backend
Navigate to the express-backend directory and install the necessary dependencies:
```bash
cd express-backend
npm install
```
Start the Express server:
``` bash 
npm start
```
### 3. Start Worker Logic
Open a new terminal for each worker you want to start. Navigate to the worker-logic directory, install dependencies, and start the worker:
``` Bash
cd worker-logic
npm install
npm start
```
### 4. Simulate Work Distribution
Use Postman or any other API testing tool to send requests to the Express backend. The tasks will be queued and randomly assigned to available workers.
### 5. Handling Worker Crashes
To simulate real-world scenarios, you can manually terminate a worker process. The tasks assigned to the terminated worker will remain in the queue until a worker is back online. Once a new or existing worker resumes, the tasks will be reassigned

### License
This project is licensed under the MIT License.
