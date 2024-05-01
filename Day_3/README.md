## Day_3: Connect FrontEnd and Backend in Javascript
There are Two ways to use Packages in javascript.
- common js
  
        const express = require('express')
- module js
  
        import express from 'express'
  if you're using module then you have to define type as module in package.json

          "type": "module"
### To create a web application using Vite, then follow these steps:

- Install Node.js: Ensure that you have Node.js installed on your system. You can download and install it from the official Node.js website: https://nodejs.org/
- Install Vite: You can install Vite globally using npm (Node Package Manager) by running the following command in your terminal or command prompt:

        npm install -g vite
- Create a new Vite project: Once Vite is installed, you can create a new project by running the following commands:

        mkdir my-vite-app
        cd my-vite-app
        vite
    This will prompt you to choose a project template. You can choose from various options like Vue, React, Preact, or Vanilla (plain JavaScript).
- Install dependencies: After choosing the template and generating the project, navigate into the project directory and install dependencies using npm or yarn:
