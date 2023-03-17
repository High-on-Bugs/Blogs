---
title: "Web Basics - Part 4"
datePublished: Wed Mar 15 2023 10:29:56 GMT+0000 (Coordinated Universal Time)
cuid: clf9jjfvt000d09ju6aqgexpu
slug: web-basics-part-4
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1678873542544/c4c3e2d5-5220-4f2a-99d1-229d1666facd.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1678876188525/23f53377-879d-461a-b120-f07f0a630d08.png
tags: data, cookies, localstorage, cache, session

---

### What are Cookies, Local Storage, and Session Storage?

Cookies, local storage, and session storage are all ways to store data in a user's browser while they are interacting with a website.

Cookies are small text files that are stored on a user's computer by a website they visit. They can be used to remember information about the user, such as their login details or their preferences for using the website. Cookies are important for web development because they allow websites to provide personalized experiences for users and to track user behavior for analytics purposes.

Local storage is a way to store larger amounts of data in a user's browser than is possible with cookies. Local storage is designed to be used for data that needs to persist beyond a single session, such as user preferences or settings. Local storage is important for web development because it provides a way to store data on the client side of a website, reducing the need to constantly request data from the server.

Session storage is similar to local storage, but the data it stores is only available for the duration of a user's session on a website. This means that once the user closes their browser or navigates away from the website, the data stored in session storage is deleted. Session storage is important for web development because it provides a way to store data temporarily during a user's session, such as items in a shopping cart or form data.

### Cookies

Cookies are small text files that are stored on a user's computer or device when they browse a website. These files contain information about the user's activities on the website, including preferences, settings, login information, and browsing history. Cookies are designed to enhance the user's experience by making it easier and faster for them to access the website's features and content.

There are several types of cookies:

1. **Session cookies**: These cookies are temporary and are deleted when the user closes their browser. They are used to remember the user's preferences and settings during a single session.
    
2. **Persistent cookies**: These cookies are stored on the user's computer even after they close their browser. They are used to remember the user's preferences and settings for future sessions.
    
3. **First-party cookies**: These cookies are set by the website that the user is visiting.
    
4. **Third-party cookies**: These cookies are set by a third-party website, such as an advertising network or analytics service.
    

Some examples of cookies include:

1. **Authentication cookies**: These cookies are used to remember a user's login information, such as their username and password.
    
2. **Shopping cart cookies**: These cookies are used to remember the items that a user has added to their shopping cart on an e-commerce website.
    
3. **Analytics cookies**: These cookies are used to track a user's behavior on a website, such as which pages they visit and how long they stay on each page.
    
4. **Advertising cookies**: These cookies are used to display targeted ads to users based on their browsing history and interests.
    
5. **Social media cookies**: These cookies are used to integrate social media features into a website, such as the ability to share content on social media platforms.
    

### Local Storage

Local storage is a web technology that allows web applications to store data on the client-side (user's browser) beyond the lifetime of a single session. It is a way for web developers to save information that persists even after the browser is closed, allowing the user to pick up where they left off the next time they visit the website.

Local storage works by providing a key-value storage mechanism for data. The data is stored in the user's browser in a separate storage area than cookies, with a much larger storage capacity. The data is stored as strings, but it can be converted to other data types using JavaScript methods.

The data stored in local storage is specific to the domain and protocol of the website, meaning that it cannot be accessed by other websites. It is also accessible to all scripts running on the website, making it a useful tool for sharing data between different parts of a web application.

Local storage is needed for several reasons:

1. **Persistent data storage**: Local storage allows web applications to store data that persists beyond the lifetime of a single session. This means that users can come back to the website at a later time and pick up where they left off, without losing any data.
    
2. **Improved performance**: Local storage can improve the performance of web applications by reducing the need for server requests. By storing data locally, the website can access it more quickly and efficiently, without having to make requests to the server.
    
3. **Offline functionality**: Local storage can be used to store data that is needed for offline functionality. For example, a web application that needs to be accessed in areas with poor internet connectivity can use local storage to store data that can be accessed even when the user is offline.
    
4. **Enhanced user experience**: Local storage can be used to store user preferences, settings, and other data that can improve the user experience. By storing this data locally, the website can personalize the user's experience and provide a more seamless experience overall.
    

Here are some examples of how local storage can be used:

1. **Remembering user preferences**: A website can use local storage to remember a user's preferences, such as their preferred language, font size, or theme. This allows the website to provide a more personalized experience for the user.
    
2. **Storing form data**: When a user is filling out a form on a website, local storage can be used to save their progress. This way, if the user accidentally closes the browser or navigates away from the page, they can come back and continue where they left off.
    
3. **Saving game progress**: Online games can use local storage to save a player's progress. This allows the player to come back later and resume playing from where they left off, without losing any progress.
    
4. **Cache management**: Local storage can be used to store frequently used data, such as images or other assets, to reduce the number of server requests. This can improve the performance of the website and reduce page load times.
    
5. **Offline functionality**: Web applications can use local storage to store data that is needed for offline functionality. For example, a note-taking application can use local storage to store the user's notes, which can be accessed even when the user is offline.
    

### Session Storage

Session storage is a web storage technology that allows web applications to store data on the client-side (user's browser) for the duration of a single session. A session is defined as the time period between when a user opens a website and when they close their browser or navigate away from the website. Session storage provides a way for web developers to store data temporarily, for use during the current session.

Session storage works by providing a key-value storage mechanism for data, similar to local storage. The data is stored in the user's browser and is specific to the domain and protocol of the website. However, unlike local storage, the data stored in session storage is deleted when the user closes their browser or navigates away from the website.

Here are some examples of how session storage can be used:

1. **Anonymous Shopping cart**: Session storage can be used to store the items in a user's shopping cart during a single session without logging in. This allows the user to add and remove items from their cart without losing any data.
    
2. Page state: Session storage can be used to store the state of a webpage during a session. For example, if a user is on a webpage that allows them to filter results, session storage can be used to store their filter preferences so that they can be applied to subsequent searches.
    

### Other Data Storages

Browser cache, IndexedDB, and Web SQL are three web technologies that can be used to store data on the client-side (user's browser) to improve website performance and provide offline functionality.

1. **Browser cache**: A browser cache is a mechanism used by web browsers to temporarily store web page data, such as HTML, CSS, and JavaScript files, images, and other assets. When a user visits a web page, the browser checks if it has cached versions of the requested resources. If cached versions exist, the browser loads them from the cache instead of making a new request to the server, which can significantly reduce page load times and improve website performance. The usefulness of browser cache is that it reduces the number of requests to the server, which in turn reduces server load and bandwidth usage. It also improves the user experience by allowing pages to load faster.
    
2. **IndexedDB**: IndexedDB is a client-side database technology that allows web developers to store and retrieve large amounts of structured data in the user's browser. It is designed to be a scalable storage solution that can store large amounts of data and work efficiently with large datasets. IndexedDB works by storing data in key-value pairs, with the ability to create indexes for efficient data retrieval. Data stored in IndexedDB can be queried using various APIs, allowing web applications to manipulate and retrieve data as needed. The usefulness of IndexedDB is that it provides a way for web developers to store large amounts of data on the client side, which can improve website performance by reducing the number of server requests. It also provides offline functionality, allowing web applications to continue working even when the user is not connected to the internet.
    
3. **Web SQL**: Web SQL is a deprecated client-side database technology that allowed web developers to store structured data in the user's browser. It used an SQLite database engine to provide a SQL-like interface for storing and retrieving data. The usefulness of Web SQL was that it provided a way for web developers to store data on the client side, allowing for improved website performance and offline functionality. However, it has been deprecated in favor of IndexedDB due to concerns about cross-browser compatibility and security.
    

---

These were some of the Web Storage Mechanisms, that help us in retaining/storing data on the client side. These help in a lot of business logic as well as user experience improvements. If you did find this helpful, stay tuned/like/all that good stuff. Will write on more topics. If you still have any questions/queries you can reach out to me on my [**LinkedIn**](https://www.linkedin.com/in/sbk2k1/) / [**GitHub**](https://github.com/sbk2k1) / [**Twitter**](https://twitter.com/sbk_2k1).

Cheers!