# Welcome to your Expo app 👋

This is an [Expo](https://expo.dev) project created with [`create-expo-app`](https://www.npmjs.com/package/create-expo-app).

## Get started

1. Install dependencies

   ```bash
   npm install
   ```

2. Start the app

   ```bash
   npx expo start
   ```

In the output, you'll find options to open the app in a

- [development build](https://docs.expo.dev/develop/development-builds/introduction/)
- [Android emulator](https://docs.expo.dev/workflow/android-studio-emulator/)
- [iOS simulator](https://docs.expo.dev/workflow/ios-simulator/)
- [Expo Go](https://expo.dev/go), a limited sandbox for trying out app development with Expo

You can start developing by editing the files inside the **app** directory. This project uses [file-based routing](https://docs.expo.dev/router/introduction).

## Get a fresh project

When you're ready, run:

```bash
npm run reset-project
```

This command will move the starter code to the **app-example** directory and create a blank **app** directory where you can start developing.

## Learn more

To learn more about developing your project with Expo, look at the following resources:

- [Expo documentation](https://docs.expo.dev/): Learn fundamentals, or go into advanced topics with our [guides](https://docs.expo.dev/guides).
- [Learn Expo tutorial](https://docs.expo.dev/tutorial/introduction/): Follow a step-by-step tutorial where you'll create a project that runs on Android, iOS, and the web.

## Join the community

Join our community of developers creating universal apps.

- [Expo on GitHub](https://github.com/expo/expo): View our open source platform and contribute.
- [Discord community](https://chat.expo.dev): Chat with Expo users and ask questions.

VaultVu Backend
This is the backend service for the VaultVu application, built with Node.js and Express. It handles user authentication, including registration, login, and profile completion, using MongoDB for data persistence.

Prerequisites
Before you begin, ensure you have the following installed on your machine:

Node.js: A JavaScript runtime environment.

npm: Node Package Manager, which comes bundled with Node.js.

MongoDB: A NoSQL database. You can install it locally or use a cloud-based service like MongoDB Atlas.

Getting Started
Follow these steps to get the backend server up and running on your local machine.

1. Clone the Repository
Clone the project repository to your local machine:

git clone <your-repository-url>
cd <your-project-directory>




Note: Replace <your-project-directory> with the name of the folder where you cloned the backend files.

2. Install Dependencies
Install all the necessary npm packages listed in package.json:

npm install



3. Configure Environment Variables
The project uses a .env file to manage sensitive information like the database connection string and JWT secret.

Create a new file named .env in the root of the project directory with the following content:

PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key_for_jwt





Note:

MONGO_URI: Replace your_mongodb_connection_string with your actual MongoDB connection string. For a local instance, it might look like mongodb://localhost:27017/vaultvu. For MongoDB Atlas, you can find this in your cluster's connection settings.

JWT_SECRET: Replace your_secret_key_for_jwt with a strong, random string. This is used to sign and verify JSON Web Tokens.

4. Run the Server
Start the Node.js server using the following command:

npm run dev





This command assumes you have a dev script in your package.json file. Alternatively, you can run the server directly with Node:

node server.js





You should see the message Server running on port 5000 in your console, indicating that the server is successfully running.

API Endpoints
The backend exposes the following authentication endpoints under the /api/auth route:

Method

Endpoint

Description

Request Body

POST

/api/auth/register

Registers a new user with an email and password.

{ "email": "string", "password": "string" }

POST

/api/auth/login

Logs in a user. Accepts either an email or a username.

{ "emailOrUsername": "string", "password": "string" }

POST

/api/auth/complete-profile

Completes a user's profile with personal details.

{ "email": "string", "username": "string", "dateOfBirth": "Date", "country": "string", "gender": "string" }

