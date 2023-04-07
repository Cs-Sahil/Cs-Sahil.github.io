---
layout: page
icon: fas fa-stream
order: 2
title: Recimeal Retrospective
---

<!-- ### Group 13 Retrospective for Iteration 3 -->

**Part 1 - Reflections**  There were some parts of the project that did not go as expected.
- Implementing the database brought issues. At the last moments before we handed in iteration 2, it was discovered that some tests from iteration 1 had broken due to the addition of a non-stub database. We figured it was a problem connecting to the database in the test environment but there wasn't time to fix it so we removed those tests, which tanked the coverage of the logic layer. As soon as iteration 3 began the issue was fixed and more effort is being put into building and maintaining our tests. This iteration there are multiple people focused mainly on the tests.
- Through all iterations there was discussion about our domain-specific objects. What each class would contain, if ingredients should be their own class or strings as part of recipe. Considerations for how the objects would interact with the database. We talked about these things a lot but even going into iteration 3 there was uncertainty on what was needed and what was not.
- One such discussion was if there should be one field for search tags or two. The database entries and the object ended up with two fields, while the create recipe menu did not allow tag input at all, leaving both those fields unused.
- Ingredients were agreed to be their own class and implemented into the database as such. However, this led to the creation of the 'AccessIngredients' class which seemed to have no use in iteration 2. 
-   Due to poor communication there was a time where it wasn't clear how a new recipe would get its ID, but due to function parameters it wasn't obvious that that responsibility was not for the caller (the presentation layer) to decide.

-   There are some duplicate codes to check whether the passed object has a valid primary key. In the database layer, methods like  `insertRecipe(),deleteRecipe(),getRecipeSequential()`  all contain a similar if-else block at the beginning of the method to check whether the object is valid. This problem can be solved by setting some pointscut and use the features of Aspect Oriented Programming to group this validate behavior together.

**Part 2 - Moving Forward**  We have several plans this iteration, some to move forward with new features and others to address the issues explained above.  This iteration there is more focus being put on the tests, and that will be considered a success if all tests pass and coverage is over 70%.

We will continue to examine the code for smells and condense where possible, removing duplication in the progress.  We hope to remove all dead code by the end of the iteration, either by cutting or implementing a use for it.

There are more features being added in iteration 3, like favoriting, search filters, and a grocery list.  If two or more of these features are in the final build, we will consider it a success.