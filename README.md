# BobbleaiAssignment
## Question 1

· Bobble Users enjoy Bigmauji feature a lot, so bobble is planning to create a big Text.
You are tasked to create an app with an option to display text entered by the user like a
threaded conversation.

· There should be an option for the user to enter some text and a display/send button
beside it

· Once the user enters the text and press the display button, the text should be displayed
as a list above the text input box like a threaded conversation(latest should be at the
bottom).

· If the user press and hold the display button, then entered text should keep on increasing
in size (animations can be shown for the same on the screen- watch bigmouji video),

· When the user releases the button it should be displayed in the appropriate size selected
by the user and input field should be blank.

· Also when the user closes and reopens the app, previous data should be shown(Think
about user experience if the data is too much)

### Solution

ABOUT APPLICATION:

This app shows all the input data entered by a authenticated user as a thread of messages. The data is stored in firebase realtime database. 
The screen shots of the application are attached below.





## Ques 2
one of the developer is facing the following error while using the application,Exception in thread "main" java.util.ConcurrentModificationException

at java.util.ArrayList$Itr.checkForComodification(ArrayList.java:859)

at java.util.ArrayList$Itr.next(ArrayList.java:831)

at main.java.Bobble.main(Test.java:25)

Can you tell what he might be doing wrong? and how he can fix it? demonstrate how to reproduce the error, and then the resolution

## Answer
The iterators returned by this ArrayList's iterator and listIterator methods are fail-fast: if the list is structurally modified at any time after the iterator is created, in any way except through the iterator's own remove or add methods, the iterator will throw a ConcurrentModificationException. Thus, in the face of concurrent modification, the iterator fails quickly and cleanly, rather than risking arbitrary, non-deterministic behavior at an undetermined time in the future.

Iterator<String> lir = al.iterator(); // Iterator created
```  
while (lir.hasNext())

System.out.println(lir.next());
    
al.add(2, "inserted"); 

while (lir.hasNext()) 

System.out.println(lir.next());

```

## Resolution

```
...
al.add(2, "inserted");

lir = al.iterator();

while (lir.hasNext()) 

System.out.println(lir.next());
    
 ```   
    
