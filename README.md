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


