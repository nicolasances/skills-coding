# What to test 

This document clarifies what aspects of a code base to test. 

## Front-end 

For front-end (UI) codebases, you **must avoid** testing the following: 
- **API calls**: the component that executes the call (typically classes that extend `TotoAPI`). These components are too simple to require testing. 
- **Data objects**: whether it is Transfer Objects or any domain Entity. This includes the parsing and constructors. These are too simple to require testing. Only test a data object if there is specific business logic in it.
- **Extremely simple code**: whenever a function is less than 5 lines of code testing is overkill. Only test small functions if they provide a critical aspect of the application, i.e. if the function provides a function that if not implemented properly would block the application flow.

## Back-end microservies
- **Data objects**: whether it is Transfer Objects or any domain Entity. This includes the parsing and constructors. These are too simple to require testing. Only test a data object if there is specific business logic in it.
- **Store objects**: objects that just integrate with Mongo. Do not test those **unless** they have some business logic embedded. Most of the time a `Store` object is just an interface to the database and has very simple functions that mostly perform simple queries or DB operations. Tests for those functions should be avoided. Reserve tests for functions that have business logic that generate queries or ops a bit more complex.