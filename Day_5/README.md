# Day_5: Data Modelling for Backend with Mongoose
This repository contains code examples and resources for understanding data modelling for backend applications using Mongoose, an elegant MongoDB object modeling tool designed to work in an asynchronous environment.

## Overview

Data modelling is a critical aspect of backend development, especially when working with NoSQL databases like MongoDB. Mongoose simplifies the process of defining schemas and models for MongoDB, allowing developers to structure their data effectively.

In this repository, you will find:

- Code examples demonstrating various aspects of data modelling with Mongoose.
- Explanation of key concepts such as schemas, models, validators, middleware, etc.
- Best practices and tips for designing efficient schemas.
- Resources for further learning.

## Contents

1. **Installation**: Instructions for installing Mongoose and setting up a project.
2. **Basic Usage**: Simple examples illustrating how to define schemas and models.
3. **Advanced Features**: Exploring advanced features like middleware, virtuals, population, etc.
4. **Testing**: Guidelines for testing Mongoose schemas and models.
5. **Best Practices**: Tips for designing schemas for optimal performance and scalability.
6. **Resources**: Links to additional documentation, tutorials, and related resources.

## Data Modeling
Data modeling is the process of designing the structure and relationships of data within a database system. It involves defining entities, attributes, and relationships to create a blueprint for organizing and storing data effectively. By modeling data, developers can ensure data integrity, optimize performance, and support the requirements of applications.

## Creating a Schema with Mongoose
To create a schema using Mongoose in your Node.js application, follow these steps:

- Install Mongoose: If you haven't already, install Mongoose in your Node.js project using npm or yarn.

      npm install mongoose

- Require Mongoose: Require Mongoose in your Node.js file where you want to define the schema.

      import moongoose from 'moongoose'
- Define Schema: Use the mongoose.Schema constructor to define your schema. Specify fields and their types, along with any validation rules or default values.

        const Schema = mongoose.Schema;
        const userSchema = new Schema({
            name: String,
            email: {
                type: String,
                required: true,
                unique: true
            },
            age: {
                type: Number,
                min: 18
            },
            createdAt: {
                type: Date,
                default: Date.now
            }
        });
- Create Model: Create a Mongoose model using mongoose.model by providing a name for the model and the schema you defined.

        const User = mongoose.model('User', userSchema);

- Usage: Now you can use the User model to interact with your MongoDB database.

        // Example: Creating a new user
        const newUser = new User({
            name: 'John Doe',
            email: 'john@example.com',
            age: 25
        });
        
        newUser.save()
            .then(user => {
                console.log('User created:', user);
            })
            .catch(error => {
                console.error('Error creating user:', error);
            });

- Modify your schema definition to include fields for "createdBy" and "modifiedBy". These fields can be of type ObjectId to reference user documents or any other identifier that uniquely identifies users in your system.

            const mongoose = require('mongoose');
            const Schema = mongoose.Schema;
            
            const yourSchema = new Schema({
            // Other fields in your schema
            field1: String,
            field2: Number,
            // "createdBy" field
            createdBy: {
            type: Schema.Types.ObjectId,
            ref: 'User' // Assuming 'User' is the name of your user model
            },
            // "modifiedBy" field
            modifiedBy: {
            type: Schema.Types.ObjectId,
            ref: 'User'
            }
            });

## Acknowledgements

- [Mongoose Documentation](https://mongoosejs.com/docs/index.html)
- [MongoDB University](https://university.mongodb.com/)
- [Stack Overflow](https://stackoverflow.com/) community for valuable insights and solutions.
