### Web App Security
### Many to many relationships
### Security: a humorous overview

--- 
## Many to many relationships
![](/assets/mm.jpg)
 - A many-to-many relationship occurs when multiple records in a table are associated with multiple records in another table.
### Example

- Example of Many to Man relationship between two entities student and project.
- In this scenario any given student can be assigned to multiple projects and a project may have multiple student working for it.

### Model Class 

- In order to map a many-to-many association, we use the @ManyToMany, @JoinTable and @JoinColumn annotations.
- The @ManyToMany annotation is used in both classes to create the many-to-many relationship between the entities.
- This association has two sides i.e. the owning side and the inverse side.
- The @JoinColumn annotation is used to specify the join/linking column with the main table.

# James Meekins 
This World of Ours
- Security is very important we must protect your online accounts and data with a strong password, for example, or two-factor authentication, and not click on fake ads and anonymous messages.

## Resources

- [Many to Many](https://www.baeldung.com/hibernate-many-to-many)
- [This World of Ours](https://scholar.harvard.edu/files/mickens/files/thisworldofours.pdf)