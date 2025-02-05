# MongoDB $inc operator with string value
This example demonstrates an uncommon error when using the MongoDB $inc operator. The $inc operator is used to increment a numeric field in a document. However, if you pass a string value to the $inc operator, it won't throw an error but it will fail to increment the value. This can be hard to debug because there's no explicit error message.

## Bug
The bug is in the `updateOne` method. The `$inc` operator is passed a string value ('1') instead of a numeric value (1). This will result in the field not being incremented.

## Solution
The solution is to use the numeric value 1 instead of the string '1'.