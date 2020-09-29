# BobbleaiAssignment
## Ques 2
one of the developer is facing the following error while using the application,Exception in thread "main" java.util.ConcurrentModificationException

at java.util.ArrayList$Itr.checkForComodification(ArrayList.java:859)

at java.util.ArrayList$Itr.next(ArrayList.java:831)

at main.java.Bobble.main(Test.java:25)

Can you tell what he might be doing wrong? and how he can fix it? demonstrate how to reproduce the error, and then the resolution

## Answer
The iterators returned by this ArrayList's iterator and listIterator methods are fail-fast: if the list is structurally modified at any time after the iterator is created, in any way except through the iterator's own remove or add methods, the iterator will throw a ConcurrentModificationException. Thus, in the face of concurrent modification, the iterator fails quickly and cleanly, rather than risking arbitrary, non-deterministic behavior at an undetermined time in the future.

Iterator<String> lir = al.iterator(); // Iterator created
  
while (lir.hasNext())

    System.out.println(lir.next());
    
al.add(2, "inserted"); 

while (lir.hasNext()) 

    System.out.println(lir.next());

## Resolution
...
al.add(2, "inserted");

lir = al.iterator();

while (lir.hasNext()) 

    System.out.println(lir.next());
    
