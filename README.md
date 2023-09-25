# Social Network API

The Social Network API is a robust and scalable backend application designed to simulate a simple social network. It provides a set of RESTful API endpoints allowing clients to perform CRUD operations on users, thoughts, friends, and reactions. The application is built with Node.js, Express.js, MongoDB, and Mongoose, ensuring optimal performance and security.



https://github.com/Youngobz/Social-Network-API/assets/133522178/4df9ce42-2684-4eee-bdc5-66009646556f




## Table of Contents

- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Usage](#usage)
- [API Routes](#api-routes)
  - [User Routes](#user-routes)
  - [Thought Routes](#thought-routes)
- [Models](#models)
  - [User Model](#user-model)
  - [Thought Model](#thought-model)
  - [Reaction Model](#reaction-model)
- [Contributing](#contributing)
- [License](#license)

## Technologies Used

- Node.js
- Express.js
- MongoDB
- Mongoose

## Installation

Clone the repository to your local machine and navigate to the project directory. Run the following command to install the necessary packages:

```sh
npm install
```

## Usage

To start the server, navigate to the project directory and run the following command:

```sh
npm start
```

The server will start, and the application will be accessible at `http://localhost:3001/`.

## API Routes

### User Routes

- `GET /api/users`: Retrieve all users.
- `GET /api/users/:id`: Retrieve a single user by ID.
- `POST /api/users`: Create a new user.
- `PUT /api/users/:id`: Update a user by ID.
- `DELETE /api/users/:id`: Delete a user by ID.
- `POST /api/users/:userId/friends/:friendId`: Add a new friend to a user's friend list.
- `DELETE /api/users/:userId/friends/:friendId`: Remove a friend from a user's friend list.

### Thought Routes

- `GET /api/thoughts`: Retrieve all thoughts.
- `GET /api/thoughts/:id`: Retrieve a single thought by ID.
- `POST /api/thoughts`: Create a new thought.
- `PUT /api/thoughts/:id`: Update a thought by ID.
- `DELETE /api/thoughts/:id`: Delete a thought by ID.
- `POST /api/thoughts/:thoughtId/reactions`: Add a new reaction to a thought.
- `DELETE /api/thoughts/:thoughtId/reactions/:reactionId`: Remove a reaction from a thought.

## Models

### User Model

- `username`: String, unique, required, trimmed.
- `email`: String, unique, required, must match a valid email format.
- `thoughts`: Array of `_id` values referencing the `Thought` model.
- `friends`: Array of `_id` values referencing the `User` model.

### Thought Model

- `thoughtText`: String, required, must be between 1 and 280 characters.
- `createdAt`: Date, set default to the current timestamp.
- `username`: String, required.
- `reactions`: Array of nested documents created with the `reactionSchema`.

### Reaction Model

- `reactionId`: Schema.Types.ObjectId, set default to a new ObjectId.
- `reactionBody`: String, required, max 280 characters.
- `username`: String, required.
- `createdAt`: Date, set default to the current timestamp.

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change. 

## License

This project is licensed under the MIT License
