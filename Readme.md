# Laravel bugs

- Major bug I always forget - ***14.09.2020***. When you pass the whole model in associate, after we call model's method `toJson` it ends in an endless loop where we exhaus all our bytes.
