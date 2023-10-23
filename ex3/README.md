# Exercise 3: "Fill in the Blanks" of the Online Store Schema

During a Rocket Elevators customer meeting, you had started to write parts of two schemas, but the information was coming so quickly that you barely had time to write it down. Now that the customer has left, you feel the urge to complete the blanks in your notes. You recall that the product should have availability, a category, a name, and a price. Additionally, the customer wants to store reviews for products, including the reviewer's rating, a review text, and a name. Complete the schema template by filling in the blanks.

# Schema

```
const _____ = require('mongoose');

const productSchema = _____  mongoose._____({
         _____: String,
        price: _____,
        _____: String,
        availability: _________,
        reviews: [{
            reviewerName: _________,
            _____: Number,
            reviewText: _________,
        }],
});

_____Product = mongoose._____('Product', _____);

module._____ = _____;
```

# Answer

Put your filled schema here.