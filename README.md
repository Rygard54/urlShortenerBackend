the backend of this app is made with express and connect to mongoDB it uses mongoose as it give us the way to use schemas and other methods that come in handly
the idea in how the id is created is just a number starting from 0 and it will be incremented by 1, then that number is changed in base 62 to make it shorter.

the way it save the urls used is in a document with the id that I create, the real url that was given and the timestamps

if the user inputs a url that is already in the DB then I make a query to get the document in the DB and return it's id. Also updating the last modify to the current date

if the user inputs a new url then two things can happen 
  I make a query if there is any url that haven't been use in the las 24 hours 
      if one is found then update its values (realUrl, last modify) and return that id
      
      if there wasn't a document that hasn't been "unused" in the las 24 hours then it register a new document
      
