## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

### Week 1 Questions

1. List the five common HTTP verbs and what the purpose is of each verb.
  GET - read
  POST - create
  PUT - update
  PATCH - modify
  DELETE - delete 
  

2. What is Sinatra?
  Sinatra is a framework providing an MVC model for app creation: model, view, controller - allowing for communication to database and frontend presentation.

3. What is MVC?
  MVC is the model/view/controller model.  Model houses the object classes and base functionality in the form of methods - the data logic.  View houses the various html-based files providing for browser display - the presentation logic.  Controller houses routes controlling "traffic": calling appropriate methods and classes, calling appropriate view files, and formatting comms between the app and other resources via HTTP - the business logic.

4. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
  Convention allows us to stick strictly to the MVC model, maintaining SRP and driving logic to the lowest possible layer.

5. What types of variables are accessible in our view templates without explicitly passing them?
  Only locally created variables would be available in view templates.  Instance variables are available only by being passed by the controller.

6. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?

  ```ruby
  get '/horses' do
    @count = 1
    name = "Mr. Ed"
    erb :index
  end
  ```

7. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?

8. What's the purpose of ERB?
  ERB is embedded Ruby.  It allows Ruby code to be called and processes within an HTML document.

9. Why do I need a development AND test database?
  Having a test database allows for complete setup to teardown functionality in each test without risking the development database and without having to deal with the data volume of the dev database.

10. What is CRUD and why is it important?
  CRUD is an acronym for create, read, update, destroy/delete.  It is the basic model of functions that need to be accomplished on any given resource.

11. What does HTTP stand for?
  Hypertext Transfer Protocol

12. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?
  <% %> allows Ruby code to run 
  <%= %> runs ruby code and writes result

13. What's an ORM? What does it do?
  Object Relational Mapper - maps Ruby objects to database syntax; by example, ActiveRecord abstracts away the need to write database-specific language and does so for us

14. What's the most commonly used ORM in ruby (Sinatra & Rails)?
  ActiveRecord

15. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.
 GET './' - homepage
 GET './restaurants' - list of all 
 GET './restaurants/new' - new restaurant entry form 
 POST './restaurants' - create a new restaurant 
 GET './restaurants/:id' - get by id 
 DELETE './restaurants/:id' - delete a specific restaurant 
 GET './restaurants/:id/edit' - edit form for particular restaurant
 PUT './restaurants' - update restaurant with edits
 

16. What's a migration?
  A migration is a file providing for database update.

17. When you create a migration, does it automatically modify your database?
  No, the migration file must be initiated to update.

18. How does a model relate to a database?
  The model provides the object with attributes.  That object becomes a row in the database with attributes corresponding to column values.

19. What is the difference between `#new` and `#create`?
  #new is a ruby method creating a new instance of an object; #create is an ActiveRecord method creating a new instance of the object and placing it in a new row in the database

20. Given a table named `animals`, What is the SQL query that will return all info from that table?
    `id     name        number_of_legs
    -----   ------      --------------
      1     panda       4
      2     giraffe     4
      3     whale       0
      4     bird        2
  SELECT * FROM animals;  `

21. Using the same table, What is the SQL query that will return only the animals that has 4 legs?
  SELECT * FROM animals WHERE number_of_legs = 4;


### Review Questions:  
22. Given a CSV file (“films.csv”) with these headers [id, title, description], how would you load these into your database to create new instances of Film?  
  I would create the class Film with id, title, and description attributes;
  Use .readlines to pull the rows in one at a time;
  Run .create to add each as its own entry into the database

23. Given the following hash:
```
activities = {
  hiking: {cost: $0, supplies: ['hiking shoes', 'water', 'compass']},
  karaoke: {cost: $10, supplies: ['courage', 'microphone']},
  brunch: {cost: $35, supplies: ['mimosa flutes']},
  antiquing: {cost: $200, supplies: ['list of antique stores']}
}
```
How would I add 'granola bar' to things you should have when hiking?
  hiking[:supplies] << 'granola bar'

24. What are the 4 Principles of OOP? Give a one sentence explanation of each.
  (credit: http://scottpantall.com/2017/09/four-principles-object-oriented-programming-examples-java/)
  ENCAPSULATION is the idea that the attributes of an entity are enclosed in that entity. This gives context to attributes. This also allows the programmer to restrict access to those attributes so that those attributes are modified and/or used only in ways that the programmer intends to use them.
  INHERITANCE is the idea that an entity can inherit attributes from another entity. It allows the programmer to create similar entities without needing to redefine similar attributes over and over.
  POLYMORPHISM means “having many forms” which honestly doesn’t really help too much as a definition.  I like to call it a way to have the same method, only different. There are two ways to do this:
    Overloading: The method name stays the same, but the parameters, the return type and the number of parameters can all change.
    Overriding: This is when a subclass method has the same name, parameters and return type as a method in a superclass but has a different implementation.
  ABSTRACTION is the process of hiding all but the relevant information about a thing to make things less complex and more efficient for the user. For example, we don’t need to know how a clock works in order to use it to tell time. Abstraction lets you focus on what the thing does instead of how it does it.

### Self Assessment:
Choose One: (erase the others)
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week
* I feel overwhelmed by the content presented this week
Note: I feel fairly confident of the concepts, however, I do feel somewhat overwhelmed when I try to put them all together.
