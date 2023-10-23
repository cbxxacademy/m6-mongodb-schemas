# Exercise 1: Design Book and Author Schemas

To verify our comprehension of his example, our senior developer requested us to design two MongoDB schemas for a simple library system: Book and Author.

**Task 1: Book Schema**
Design a schema for the Book collection with the following requirements:
* Each book should have a title field, which is required.
* Each book should have a publicationYear field, which is also required.
* Each book requires a reference to the author who wrote it. Use ObjectId for this field and make sure to reference the Author model.

**Task 2: Author Schema**
Design a schema for the Author collection with the following requirements:
* Each author should have a name field, which is required.
* Each author should have a birthdate field, which is also required.
* Each author can have a list of books they have written. Use an array of ObjectId for this field and make sure to reference the Book model.

*Remember to define the variable that will be used to create the schema and its export.*


# Schema

Put your schema definition here.