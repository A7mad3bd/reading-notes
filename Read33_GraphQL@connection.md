# Data modeling

- Amplify automatically creates Amazon DynamoDB database tables for GraphQL types annotated with the @model directive in your GraphQL schema. You can create relations between the data models via the @hasOne, @hasMany, @belongsTo, and @manyToMany directives.


- Setup database tables
- The following GraphQL schema automatically creates a database table for "Todo". @model will also automatically add an id field as a primary key to the database table. See Configure a primary key to learn how to customize the primary key.

```
type Todo @model {
  todoId: ID! @primaryKey
  content: String
}
```

- Has One relationship
- The @hasOne and @hasMany directives do not support referencing a model which then references the initial model via @hasOne or @hasMany if DataStore is enabled.


@hasOne
Create a one-directional one-to-one relationship between two models. For example, a Project "has one" Team. This allows you to query the team from the project record.

@hasMany
Create a one-directional one-to-one relationship between two models. For example, a Project "has one" Team. This allows you to query the team from the project record.

@belongsTo
Use a "belongs to" relationship to make a "has one" or "has many" relationship bi-directional. For example, a Project has one Team and a Team belongs to a Project. This allows you to query the team from the project record and vice versa.

@manyToMany
Configures a "join table" between two models to facilitate a many-to-many relationship. For example, a Blog has many Tags and a Tag has many Blogs.


## Guide To CompletableFuture
- CompletableFuture is used for asynchronous programming in Java. 
- Using CompletableFuture as a Simple Future
- we can create an instance of this class with a no-arg constructor to represent some future result.
- CompletableFuture is an extension to Java’s Future API which was introduced in Java 5.
- A Future is used as a reference to the result of an asynchronous computation. It provides an isDone() method to check whether the computation is done or not, and a get() method to retrieve the result of the computation when it is done.
- If we already know the result of a computation, we can use the static completedFuture method with an argument that represents a result of this computation.


### Resources

[Google’s app publishing guide](https://developer.android.com/studio/publish)  

