---
title: "REST and REST APIs - Part 2"
datePublished: Sun Mar 05 2023 15:09:23 GMT+0000 (Coordinated Universal Time)
cuid: clevj4ave000g09m88ke6arps
slug: rest-part-2
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1678008840695/f0add78b-1cec-4516-bc72-5758fb7cac59.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1678028953081/aa8fcd78-61e3-4fb3-ae23-6249500ba952.png
tags: rest, github, git, restful, rest-api

---

In this blog, we will set up a REST API implemented using HTTP to play around and understand.

### Resources

1. **API endpoint:** [https://hob-api.vercel.app/](https://hob-api.vercel.app/)
    
2. **GitHub Repository**: [https://github.com/sbk2k1/API-Blog](https://github.com/sbk2k1/API-Blog)
    

### Prerequisites

We will need some tools to get through this blog. They are:

1. [Git/GitHub](https://highonbugs.sbk2k1.me/git-and-github) and [npm](https://nodejs.org/en/download/)/[yarn](https://classic.yarnpkg.com/lang/en/docs/install/#windows-stable)(Necessary only if the deployed endpoint is down)
    
2. [Postman](https://www.postman.com/) (We can use cURL but Postman will provide us with a cleaner UI)
    

### Installation

* **Git/GitHub** (optional)- Check out my [blog](https://highonbugs.sbk2k1.me/git-and-github)!
    
* **npm** and **yarn** (optional)**\-** To install npm, follow the below steps:
    
    1. Download the Node.js installer from [**here**](https://nodejs.org/en/download/)**.**
        
    2. Run the installer and follow the installation steps.
        
    3. Once installed, open a command prompt or terminal and type `npm -v` to check the version of npm.
        
    
    To install yarn, follow the below steps:
    
    1. Download the Yarn installer from [**here**](https://classic.yarnpkg.com/en/docs/install)**.**
        
    2. Run the installer and follow the installation steps.
        
    3. Once installed, open a command prompt or terminal and type `yarn -v` to check the version of Yarn.
        
    
    **Note: Yarn can also be installed using npm by running the command** `npm install -g yarn` **in the command prompt or terminal.**
    
* **Postman:** To install Postman, you can follow these steps:
    
    1. Go to the Postman [website](https://www.postman.com/downloads/).
        
    2. Click the "Download" button for the version of Postman you want to install.
        
    3. Follow the on-screen instructions to download the installation file.
        
    4. Once the file is downloaded, open it and follow the instructions to install Postman.
        
    5. Once the installation is complete, you can launch Postman by opening the application from your computer's application menu or by double-clicking on the Postman icon on your desktop (if you chose to create one during installation).
        
    
    That's it! You're now ready to use Postman to test and explore APIs.
    

### Setting up a local server (optional)

Follow the following steps to start up a server on your local system:

1. Clone the repository:
    
    ```bash
    git clone https://github.com/sbk2k1/API-Blog.git
    ```
    
2. Navigate to the directory:
    
    ```bash
    cd API-Blog
    ```
    
3. Install dependencies using either npm or yarn:
    
    ```bash
    npm install
    ```
    
    or
    
    ```bash
    yarn install
    ```
    
4. Remove the two forward slashes (`//`) from the beginning of the `app.listen` line to uncomment it.
    
    ```javascript
    app.listen(3000, () => {
      console.log(`Server running on port 3000`)
    });
    ```
    
5. Add two forward slashes (`//`) at the beginning of the `module.exports = app` the line to comment it out.
    
    ```javascript
    // module.exports = app;
    ```
    
6. Once the dependencies are installed, start the server:
    
    ```bash
    npm start
    ```
    
    or
    
    ```bash
    yarn start
    ```
    
    This will start the server on port 3000 by default.
    

### Getting it to work

**Note: I'm going to use the deployed endpoint for the blog, but you can use the** `http://localhost:3000` **if you have it set up in your local system.**

## / Route

Create a new request in Postman as shown below:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1678027771128/b461c08f-ed22-492a-ab99-71d18f1b534c.png align="center")

Fire it off and see what happens.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1678027804334/54c88d25-512a-4325-8523-841f823d3474.png align="center")

This is the response.

This signifies that the server is working fine. Note that the status in the top right that says 200 OK. (Status code refresher [here](https://highonbugs.sbk2k1.me/rest-part-1))

You can also paste the link into your browser and see what happens. By default, when you enter a URL into a web browser and press enter, it sends a GET request to the server to retrieve the content of the specified resource.

We will look into each route and each little element in greater detail in the next blog. Stay tuned for part 3. If you still have any questions/queries you can reach out to me on my [**LinkedIn**](https://www.linkedin.com/in/sbk2k1/) / [**GitHub**](https://github.com/sbk2k1) / [**Twitter**](https://twitter.com/sbk_2k1).

Cheers!