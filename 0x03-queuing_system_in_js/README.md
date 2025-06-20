# 0x03. Queuing System in JS

A comprehensive Node.js project implementing a queuing system using Redis and Kue for background job processing.

## Author
**Daisy Mwambi**

## Project Overview

This project demonstrates the implementation of a Redis-based queuing system in JavaScript, covering basic Redis operations, pub/sub patterns, job creation and processing with Kue, and building a complete web application with inventory management and seat reservation systems.

## Technologies Used

- **Node.js** 12.x
- **Redis** 5.0.7+
- **Kue** - Redis-based priority job queue
- **Express.js** - Web framework
- **Babel** - ES6+ transpilation
- **ES6/ES7** - Modern JavaScript features
- **Ubuntu** 18.04

## Project Structure

```
0x03-queuing_system_in_js/
├── README.md
├── package.json
├── .babelrc
├── dump.rdb
├── 0-redis_client.js
├── 1-redis_op.js
├── 2-redis_op_async.js
├── 4-redis_advanced_op.js
├── 5-subscriber.js
├── 5-publisher.js
├── 6-job_creator.js
├── 6-job_processor.js
├── 7-job_creator.js
├── 7-job_processor.js
├── 8-job.js
├── 8-job.test.js
├── 9-stock.js
└── 100-seat.js
```

## Prerequisites

### Redis Installation
```bash
# Download and install Redis
wget http://download.redis.io/releases/redis-6.0.10.tar.gz
tar xzf redis-6.0.10.tar.gz
cd redis-6.0.10
make

# Start Redis server
src/redis-server &

# Test Redis connection
src/redis-cli ping
# Expected output: PONG

# Set initial data
src/redis-cli set ALX School
```

### Node.js Dependencies
```bash
npm install
```

## Tasks Overview

### Task 0: Install Redis Instance
- Download, compile, and configure Redis server
- Set up initial key-value pair: `ALX` → `School`
- Copy `dump.rdb` to project root

### Task 1: Node Redis Client (0-redis_client.js)
Basic Redis client connection with error handling:
- Connects to Redis server on localhost:6379
- Logs connection status messages
- Handles connection errors gracefully

### Task 2: Basic Redis Operations (1-redis_op.js)
Implements basic Redis operations:
- `setNewSchool(schoolName, value)` - Sets key-value pairs
- `displaySchoolValue(schoolName)` - Retrieves and displays values
- Uses callback-based operations

### Task 3: Async Redis Operations (2-redis_op_async.js)
Modernizes Redis operations using:
- `promisify` for converting callbacks to promises
- `async/await` syntax for cleaner code
- Same functionality as Task 2 with modern syntax

### Task 4: Advanced Redis Operations (4-redis_advanced_op.js)
Demonstrates Redis hash operations:
- Stores city population data using `hset`
- Retrieves complete hash using `hgetall`
- Working with complex data structures

### Task 5: Pub/Sub Pattern (5-subscriber.js & 5-publisher.js)
Redis publish/subscribe implementation:
- **Subscriber**: Listens to `ALXchannel`, handles messages
- **Publisher**: Sends timed messages to channel
- Demonstrates inter-process communication

### Task 6: Basic Job Queue (6-job_creator.js & 6-job_processor.js)
Introduction to Kue job queuing:
- **Creator**: Creates notification jobs
- **Processor**: Processes jobs and sends notifications
- Basic job lifecycle management

### Task 7: Advanced Job Processing (7-job_creator.js & 7-job_processor.js)
Enhanced job processing with:
- Batch job creation from array data
- Progress tracking (0%, 50%, 100%)
- Blacklist functionality for phone numbers
- Concurrent job processing (2 jobs at a time)
- Comprehensive error handling

### Task 8: Job Creation Function (8-job.js)
Reusable job creation utility:
- `createPushNotificationsJobs(jobs, queue)` function
- Input validation and error handling
- Standardized job creation process

### Task 9: Job Testing (8-job.test.js)
Comprehensive test suite using Mocha:
- Tests job creation function
- Validates queue operations
- Uses Kue test mode for safe testing
- Ensures code reliability

### Task 10: Stock Management System (9-stock.js)
Complete inventory management web application:
- **Products**: Suitcase inventory with different models
- **Endpoints**:
  - `GET /list_products` - List all products
  - `GET /list_products/:itemId` - Get specific product details
  - `GET /reserve_product/:itemId` - Reserve product
- **Features**:
  - Real-time stock tracking with Redis
  - Stock reservation system
  - Error handling for invalid products
  - JSON API responses

### Task 11: Seat Reservation System (100-seat.js)
Advanced reservation system with queue processing:
- **Features**:
  - 50 available seats initially
  - Real-time seat availability tracking
  - Queue-based reservation processing
  - Automatic reservation blocking when full
- **Endpoints**:
  - `GET /available_seats` - Check available seats
  - `GET /reserve_seat` - Reserve a seat
  - `GET /process` - Process reservation queue
- **Queue Management**:
  - Asynchronous seat processing
  - Automatic reservation disabling
  - Job completion/failure tracking

## Usage Examples

### Starting Redis Server
```bash
# Start Redis in background
./src/redis-server &

# Verify Redis is running
ps aux | grep redis-server
```

### Running Individual Tasks
```bash
# Basic Redis client
npm run dev 0-redis_client.js

# Job creation and processing (run in separate terminals)
npm run dev 6-job_creator.js
npm run dev 6-job_processor.js

# Pub/Sub pattern (run in separate terminals)
npm run dev 5-subscriber.js
npm run dev 5-publisher.js

# Web applications
npm run dev 9-stock.js     # Stock management on port 1245
npm run dev 100-seat.js    # Seat reservation on port 1245
```

### Testing
```bash
# Run test suite
npm test 8-job.test.js
```

### API Testing Examples
```bash
# Stock Management API
curl localhost:1245/list_products
curl localhost:1245/list_products/1
curl localhost:1245/reserve_product/1

# Seat Reservation API
curl localhost:1245/available_seats
curl localhost:1245/reserve_seat
curl localhost:1245/process
```

## Key Learning Outcomes

- **Redis Fundamentals**: Basic operations, data structures, pub/sub
- **Queue Systems**: Job creation, processing, and management
- **Asynchronous Programming**: Promises, async/await, callbacks
- **Error Handling**: Robust error management and validation
- **Testing**: Unit testing with Mocha and Kue test mode
- **Web APIs**: RESTful API design with Express.js
- **Real-time Systems**: Inventory and reservation management
- **Concurrency**: Managing multiple processes and job queues

## File Requirements

- All files end with a new line
- Code uses `.js` extension
- Compatible with Ubuntu 18.04, Node 12.x, Redis 5.0.7+
- ES6+ features with Babel transpilation
- Comprehensive error handling and logging

## Repository Information

- **GitHub Repository**: `alx-backend`
- **Directory**: `0x03-queuing_system_in_js`
- **Project Type**: Backend Development
- **Specialization**: ALX Software Engineering Program

---

This project provides a comprehensive foundation for understanding queuing systems, Redis operations, and building scalable backend applications with job processing capabilities.
