<<<<<<< HEAD
# NgTrail

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 14.2.9.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.io/cli) page.
=======
# Event Tracker Project

## Description:
This is an application that allows a user to track each trip/trail they take with their 4x4 vehicle. Of note, the app can also be used to track other trail types/uses such as mountain biking, hiking/backpacking, trail running, and/or horseback riding.  Users can:
- view lists of all trails
- view a specific trail
- create a trail
- update a trail
- delete a trail

Information about a trail event includes:
- date the trip was completed
- trail's name
- trail's length
- highest elevation seen
- coordinates for the trailhead (currently not displayed in frontend)
- an image (url)  

### Stretch Goals Implemented:
- The Controller contains logic which anticipates many possible errors and will display a corresponding status code (400, 404, etc) as well as setting more specific codes (204, etc) for successful operations.  Potential errors include giving bad data (missing a non-nullable field) or attempting to modify a record that does not exist.  Postman tests include tests for bad data and bad id numbers.

- Users can also:
1. sort the list of all trails by Highest Elevation (in either ascending or descending order)
2. sort the list of all trails by Date Completed (in either ascending or descending order)
3. sort the list of all trails by Length (in either ascending or descending order)
4. search for trails whose Name or Notes contains a keyword

### REST route URIs and HTTP methods:
| CRUD Op. | HTTP Verb | URI                         | Request Body | Response Body |
|----------|-----------|-----------------------------|--------------|---------------|
| Read     | GET       | `/api/trails`               |              | List of all trails |
| Read     | GET       | `/api/trails/{trailId}`     |              | Representation of one trail |
| Create   | POST      | `/api/trails`               | JSON for new trail| JSON of created trail |
| Update   | PUT       | `/api/trails/{trailId}`     | JSON to update trail | JSON of updated trail |
| Delete   | DELETE    | `/api/trails/{trailId}`     |              | |
| Read     | GET       | `/api/trails/sort/elev/asc` |              | List of trails sorted by elevation (ascending order)|
| Read     | GET       | `/api/trails/sort/elev/desc`|              | List of trails sorted by elevation (descending order)|
| Read     | GET       | `/api/trails/sort/date/asc` |              | List of trails sorted by date completed (ascending order)|
| Read     | GET       | `/api/trails/sort/date/desc`|              | List of trails sorted by date completed (descending order)|
| Read     | GET       | `/api/trails/sort/length/asc` |              | List of trails sorted by length (ascending order)|
| Read     | GET       | `/api/trails/sort/length/desc`|              | List of trails sorted by length (descending order)|
| Read     | GET       | `/api/trails/search/{keyword}`|              | List of trails whose name or notes contains the keyword|

## Lessons Learned:
This being my first REST project, I learned about `@RestController` and `@PutMapping` / `@DeleteMapping`.  I also learned about using `@RequestMapping('blah')` to shorten all of the other `@xyzMapping` paths.
- I used `HttpServletResponse` to set response status codes and `HttpServletRequest` to getRequestUrl.  
- Instead of using a DAO and DAOImplementation, I used a Repository class with a Service and ServiceImplementation.  
- Spring Data gives the Repository class several "built-in" queries such as "show," "create," and "delete."

This is also my first JavaScript project, so I learned a lot about manipulating the DOM vs showing a jsp or html page for different views.
- I used `.style.display = 'none'` to hide an element from the DOM and `.style.display = 'block'` to display an element in the DOM.  
- In order to refresh the DOM with new data (updated trail or new trail info), I called the function which displayed that information from within an `eventListener`.

### What I Might Do Differently:
I specifically included the trailhead lat/long for the potential to integrate the Google Maps API. These fields are not currently displayed, I may enable them if I implement the Maps API.

The REST endpoints for sorting and searching are not currently accessible from the JS frontend, I might implement these in a future version.  

Changing the DOM views with display = none and display = block, got to be repetitive and difficult to track.  I might refactor by adding a function "setDomView(viewName)" that used a switch to control the visibility of all elements based on the viewName passed to the function.  

## Technology Used:
### Applications:
MySQL Workbench, Spring, Spring Boot, Spring Data, JUnit, JSON, REST, Bootstrap, Postman, JPA, Spring Tools Suite, Chrome, git/gitHub, Atom, Unix Terminal, Slack, Zoom

### Languages:
Java, MySQL, JavaScript, HTML, CSS
>>>>>>> a9525ad48029af2e918dd11585197241193c50bf