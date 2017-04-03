# Code Challenge - Week 5 (Mongo Databases and Full Stack Logic - Debug)

## Overview

This Code Challenge is different from the rest. This time, you will need to debug an existing code base. You will need your
complete knowledge of the past 4 weeks to successfully navigate the problems that are in the code.

Keep in mind, often debugging is stressful for a couple reasons:

* The problems are not obvious, especially when you did not write the code.

* The solutions are often simple. Have confidence in your solutions and move onto the next problem.

* Debugging code bases that are not yours takes time. Take your time to work through each of the steps.


In addition to making the changes to the code base to correct the code, update this README.md file to explain your solutions.
Meaning, in your own words, explain the problem and why your solution fixes the problem.


## TODO

### Base Mode
[X] - Mongo does not seem to be connecting correctly.
      -->Previously, the localhost port (on line 3 of the "db.js" file) was set to 2701. The default port for accessing MongoDB is 27017.
      --> This has been resolved by updating the localhost port to 27017.

[X] - The models have a conflict.
      -->Previously, the model names (that is, the first parameters in lines 19-21 of file "listings.js") were identical (here, they were each "listings"); MongoDB does not allow this.
      -->This has been resolved by providing each model with a unique name ("listings," "apartments", and "houses", respectively).

[X] - Index.html is not being properly served.
      --> "app.js" lacked a route to serve static files on a base "app.get('/'...)" call.
      --> This has been resolved by adding that method, on lines 14-16.

[X] - Posting information does not seem to come up correctly on the req.body as intended.
      -->In the "app.js" file, "app.use(bodyParser...)" was previously initiated after the "listings" route. The "listings" route depends on bodyParser to read objects passed through the ajax call, however: so "listings" was unable to properly read that data (because the tool it required, bodyParser, had not yet been established.)
      --> This has been resolved by moving "app.use(bodyParser...)" above "app.use('/listings'....)".

[X] - The information from the database is not being appended to the DOM.
    --> In "client.js", the "getListings" function made an ajax GET call that, on success, only logged its returned values to the console (rather than calling the "appendListings" function.)
    --> This has been resolved by replacing the "console.log(response);" on line 82 with "appendListings(response)". 

### Hard Mode
[ ] - All the information being appended on the DOM is not lining up together in their respective row.


### Pro Mode
[ ] - Not that you need to, but if you were to post this on Heroku, it would not work correctly.
