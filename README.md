# MVP Library Inventory

Our web agency has decided to open a library for no apparent reason. The rationality of this decision aside, to help guide us in our new venture we need a MVP inventory system to test with. We've decided to use a small Javascript program that we can load in the browser and run in the devtools console for feedback. We would like your help with it please.

Our criteria for the library inventory is as below. If anything is unclear about the requirements please ask and we will try to clarify. While extra functionality or enhancements are ok we are really only concerned with the functionality that is described below. For the purpose of our MVP we assume books must be unique (ie. no duplicates will be in the inventory) and we trust people are who they say they are (ie. they can simply tell us when checking out or returning a book and we won't attempt to verify their identity). We also only need to ensure our program runs in Chrome at the moment and aren't concerned with other browsers.

_Please clone this repo, add your JS solution (feeling free to use any taskrunners or npm if you wish), then answer the questions [here](./quiz.md), push everything to a private repo and invite Ben - https://github.com/benjamin-white and Lucian - https://github.com/LucianPauna as collaborators so we can review._

## The Requirements
+ The Library maintains an inventory of all books.
+ The Library should be able to add a book to its inventory.
+ The Library should be able to delete a book from its inventory.
+ The Library should not be able to delete a currently checked out book.
+ The Library should not be able to delete a book not in its inventory.
+ A user can request to check out a book from the library.
+ A user should not be able to check out a book the library does not have.
+ A user should not be able to check out a book that is already checked out.
+ A user can return a checked out book to the library.
+ A user cannot return a book not checked out by them or not in the inventory.
+ The library maintains a log of actions performed that can later be retrieved and printed to the console.
+ Log entries for adding, removing, checking in and checking out books should all start with a timestamp expressed in the format, `YYYY-MM-DD H:M:S`

**The below actions and expectations are provided to demonstrate all functionality.**

## Example test 'actions' to be performed:

````
John requests 'Special Book'  
Library adds 'Special Book' to its inventory  
John requests 'Special Book'  
Mary requests 'Special Book'  
John checks in 'Special Book'  
Mary requests 'Special Book'  
Library deletes 'Special Book'  
Mary checks in 'Special Book'  
Mary checks in 'Extra Special Book'  
John checks in 'Special Book'  
Library deletes 'Special Book'  
John requests 'Special Book'  
Library deletes 'Other Special Book'
````

## Asking the library for its  history would then output:

````
The library does not have "Special Book"  
TIMESTAMP: "Special Book" was added to the inventory  
TIMESTAMP: "Special Book" checked out to John  
"Special Book" not available (checked out to John)  
TIMESTAMP: "Special Book" checked in by John  
TIMESTAMP: "Special Book" checked out to Mary  
Unable to delete "Special Book" (checked out to Mary)  
TIMESTAMP: "Special Book" checked in by Mary  
Unable to return a book not checked out  
Unable to return a book not checked out  
TIMESTAMP: "Special Book" was removed from the inventory  
The library does not have "Special Book"  
The library does not have "Other Special Book"
````