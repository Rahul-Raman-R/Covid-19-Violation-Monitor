#### HW3-task2
###### 1.What specific design principle(s) does/do this design adhere to? Name as many as you can and explain each in details
>  Single responsibility principle : This principle states that each class should have a single reposibility and a single purpose. Therefore, the class should have only one reason to be changed. If the class is changed for multiple reasons there is risk of breaking other parts of the code.
> Open-Closed principle: This principle states that class should be open for extension but closed for modification. This means new feature can be add to the existing classes but we should not modify the existing code to add these new features. This prevent the breaking of any part of the existing code due to modifications.
> Liskov substitution principle: This principle states that while extending a class the objects of the subclass should be able to be passed in place of objects of parent class. Therefore, every sub class should be substitutable for their base class. In the given design the use of interfaces allows the addition of more sub classes without violating this principle.
> Dependency inversion principle: This principle states that high level classes should not change because of low-level classes. In the given design the high-level class Client is not dependent on the low-level class PDFUtility this is achieved due the interface FormatUtility. 

###### 2. What particular design pattern, if any, has been applied in this design?
> In the given design the adapter design pattern is applied. Here the PDFUtility class is the adapter and this allows interface FormatUtility to be used as another interface. Therefore, by introducing an adapter class the existing code can be reused without any change.
