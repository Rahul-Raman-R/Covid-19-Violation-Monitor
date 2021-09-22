#### HW3-task4
###### 1. What design pattern is being implemented here?
> Composite Design pattern is being used here.

###### 2. Assuming the price() function is implemented in DVD and Book classes, provide an implementation for price() inside the Shelf class.
```
class Shelf implements Product {
    private List<Product> products;
    int total = 0;
    
    public int price()
    {
        for(Product p:products)
        {
           total=total + p.price();
        }
        return total;
    }
    // implementation of Shelf omitted
}