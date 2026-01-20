# Product Requirements Document (PRD)

## Basic Node Set-up

### 1. Product Overview

**Product Name:** Basic Node Set-up
**Version:** 1.0.0  
**Product Type:** Basic Node project Set-up with express

**Node.js Express Starter Boilerplate**
This project is a basic Node.js setup using Express. It provides a minimal, structured starting point for building server-side applications and REST APIs.
This repository is intended as a reference and reusable template for future Node.js projects, allowing quick setup without repeating boilerplate configuration.

### 2 The project includes:

- Express server configuration

- Basic API routes (e.g., /, /hello)

- Project folder structure for scalability

- Environment-based configuration support

# Project Setup Steps:

### Before Starting Any Project (PRD)

Before starting development, a PRD (Product Requirement Document) is created.

### What is PRD?

A PRD is a document that helps capture:

- Application requirements

- Features and flows

- Errors and edge cases

- Future scope

## 1. Initialize Project

    npm init

Update scripts inside package.json.

## 2. Add PRD

- Add file PRD (PRD.md) with ifno

## 3. Prettier Setup

Install Prettier

    npm install --save-dev prettier

    npx prettier . --write

Create .prettierrc and add rules

Example rules:

    {
      "tabWidth": 2,
      "useTabs": false,
      "semi": true,
      "singleQuote": false,
      "bracketSpacing": true,
      "arrowParens": "always"
    }

This enforces consistent formatting across the project.

Add prettierignore file to ignore some file folders like .env, node_module and etc.

## 4. Git Setup

Initialize git

    git init

Add .gitignore

Ignored files/folders:

    node_modules/
    .env

- Make initial commit

## 5. Auto Reload with Nodemon

Install nodemon

    npm install --save-dev nodemon

Update package.json:

    "scripts": {
     "dev": "nodemon index.js",
     "start": "node index.js"
    }

- npm run dev → development (auto-reload)

- npm start → production-style run

## 6. Environment Variables (dotenv)

install dotenv lib

    npm install dotenv

- Create .env file

- Store environment-specific values

- Load variables using **dotenv.config()** -> dotenv.config({ path: "./.env" });

## 7. Project Structure

    project-root/
    │
    ├── public/
    │   └── images/
    │
    ├── src/
    │   ├── controllers/
    │   ├── db/
    │   ├── middlewares/
    │   ├── models/
    │   ├── routes/
    │   ├── utils/
    │   └── validators/
    │   └── index.js
    │   └── app.js
    │
    ├── PRD.md
    ├── package.json

This structure is designed to scale cleanly as the project grows.

## 8. Module System Configuration

In package.json:

    "type": "module"

- Enables ES module syntax (import/export)

- If using require, keep CommonJS instead

Choose one, not both.

## 9. Basic Express Setup

Install Express

    npm install express

- Create a basic server

- Add a home route /

- Add a sample API route like /hello

## 10. Add Basic Express configurations

Basic configurations

    app.use(express.json({ limit: "16kb" }));
    app.use(express.urlencoded({ extended: true, limit: "16kb" }));
    app.use(express.static("public"));
    app.use(cookieParser());

## 11. Enable CORS

Install Cors

    npm install cors

Configure CORS globally

Basic Example:

    app.use(
      cors({
        origin: process.env.CORS_ORIGIN?.split(",") || "http://locahost:5173",
        credentials: true,
        methods: ["GET", "POST", "PUT", "PATCH", "DELETE", "OPTIONS"],
        allowedHeaders: ["Content-Type", "Authorization"],
      }),
    );

## 10. Postman Setup

- Create dummy APIs for testing

- Test APIs using Postman
