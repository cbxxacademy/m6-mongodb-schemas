# Introduction

In the realm of NoSQL databases, MongoDB stands out as a powerful and flexible database. A MongoDB schema is a flexible blueprint defining document structure in a collection. One key aspect of structuring our data in MongoDB is through the use of schemas. Unlike traditional databases, MongoDB's schema allows varied structures in the same collection.

Our senior developers at Rocket Elevators want us to grasp this concept for our knowledge and upcoming tasks by providing two schema examples that demonstrate different aspects of MongoDB. These examples clearly show how to use various kinds of fields. They want us to read and understand the different parts of it. Let's take a closer look at these examples to grasp their important elements:


```
const mongoose = require('mongoose');

const postSchema = new mongoose.Schema({
        title: { type: String, required: true },
        content: { type: String, required: true },
        author: { type: mongoose.Schema.Types.ObjectId, ref: 'User', required: true },
        likes: [{ type: mongoose.Schema.Types.ObjectId, ref: 'User' }],
        tags: [String],
        createdAt: { type: Date, default: Date.now },
});

const userSchema = new mongoose.Schema({
        username: { type: String, required: true, unique: true },
        email: {
            type: String,
            required: true,
            match: /^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,4}$/,
        },
        friends: [{ type: mongoose.Schema.Types.ObjectId, ref: 'User' }],
});

const Post = mongoose.model('Post', postSchema);
const User = mongoose.model('User', userSchema);

module.exports = { Post, User };
```


### Data Type
The type property found within each schema field specifies the data type of that particular field. For instance, when `type: String` is used, it indicates that the field contains a string.

### Validation Rules
Numerous properties located within the schema fields enforce validation rules. For instance, when `required: true` is applied, it mandates that a field must be present during the creation of a new document. The match property utilizes a regular expression to validate the `email` format.

### Relationship
The `ref` property within a schema field establishes a relationship with another model. To illustrate, within the postSchema's author field, `ref: 'User'` denotes that this field references the User model.

### Default Values
The default property within a schema field establishes a predefined value for that field when a new document is generated. For instance, `default: Date.now` configures the `createdAt` field to the current timestamp upon the creation of a new post.

### Embedding
In the provided example, explicit embedding is absent. Embedding encompasses the nesting of one document within another. For instance, if the `User schema` comprised an `array of posts`, each element of the array could embed a Post document.

### Referencing
Referencing entails forming a relationship between documents using their distinct identifiers `ObjectId`. For instance, the `likes` field within the postSchema makes reference to an `array of User` documents that have expressed appreciation for the post.

# Exercices

Complete the exercises by going to their respective folder and following the instructions