# Any vs All

## Any

The **Any()** method is a LINQ extension method that operates on any **IEnumerable<TSource>**. Its purpose is to return **true** if there is at least one item (or match) in a enumerable collection.

**Any()** that takes no parameters (aside from the implicit extension method source) we see that it’s really a “not empty” check. This is a very handy check to use anytime you want to see if an **IEnumerable<TSource>** collection is non-empty

## All

The  **All()**  extension method is very useful for checking enumerable collections for consistency. Just like  **Any()**  is used to check to see if an item matching a given predicate exists,  **All()**  checks to make sure  _**every**_ item in the collection matches the predicate. Unlike  **Any()**,  **All()**  does not have a form that does not take a  **Predicate<TSource>**, because this would not have meaning for  **All()**  – after all, what would  **All()**  with no additional arguments mean?

So we have only the one form that takes the predicate (in addition to the implicit source argument for the extension method syntax, of course):

-   **All(Predicate<TSource>)**
    -   Returns  **true**  if and only if there is  **_not_** an item in the list that  **_fails_** to match the predicate condition – note that this means that empty collections will return  **true!**

Notice that last point! If the enumerable collection is empty,  **All()**  will return true regardless of what the predicate is! This makes logical sense because a list of zero items has no items to check, and thus there is no item in the list that  _**fail**_ to pass the predicate.
