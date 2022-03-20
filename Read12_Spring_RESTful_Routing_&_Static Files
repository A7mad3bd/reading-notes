# Read: 12 - Spring RESTful Routing & Static Files
## Define an Entity

- @Entity indicates that it is a JPA entity. 

## Create Simple Queries

- Spring Data JPA focuses on using JPA to store data in a relational databaseand its most compelling feature is the ability to create repository implementations automatically, at runtime and from a repo interface.

## Build an executable JAR
- You can run the application from the command line with Gradle or Maven. You can also build a single executable JAR file that contains all the necessary dependencies, classes , and resources and run that. 

## Spring Data Repos
- Crud Repository -> provides CRUD functions
- PagingAndSortingRepository -> provides methods to do pagination and sort records.
- JpaRepository provides JPA related methods such as flushing the persistence contect and delete records in a batch.

## CrudRepository
- save() saves an Iterable of objects. Here we can pass multiple objects to save them in a batch
- findOne(…) gets a single entity based on passed one primary key value
- findAll() gets an Iterable of all available entities in the database
- count() returns the count of total objects in the table
- delete(…) delete an object based on the passed object
- exists(…) verify if an object exists based on the passed primary key value

## JPARepository

- findall
- findall(...)
- save(...)
- flush
- saveAndFlush()
- deleteInBatch

## Paging And Sorting Repository

When using Pageable, we create a pageable object with certain properties and weve to specify at least.
1. Page Size
2. Current Page Number
3. Sorting

## The Whole Process generally
- Succesfully made a simple application that uses Spring Data JPA to save objects to and fetch them from the database, all without writing a concrete repository implmenetaion. 

## Resources
- [Spring guide: Accessing Data with JPA](https://spring.io/guides/gs/accessing-data-jpa/)
- [Baeldung: Comparing repositories](https://www.baeldung.com/spring-data-repositories)
