##### HW3-task3
###### 1. Name the design pattern the above class implements and explain the named design pattern in a sentence.
> The design pattern that the above class implements is Singleton design pattern. The Singleton design pattern ensures that a class has only one instance while also giving a global access point to that instance.

###### 2. Why does it make sense to make the constructor of CreateImageReader class private?
> The constructor of CreateImageReader class is private to prevent other objects from using the new operator with singleton class.

###### 3. Assume fis is an instance of FileInputStream associated with a binary file that stores a GIF image. How do you make use of the above class in order to read the GIF image? Write the java statement.
Here FileInputStream extends InputStream therefore an instance of FileInputStream can be created as given below:
```
InputStream fis= new FileInputStream(filepath);
```
Now we can use "fis" instance in place of the "is" instance to use the same class to read the GIF image as shown in the code below: 
```
public class CreateImageReader {
   private CreateImageReader() {}
   public static CreateImageReader createImageReader(InputStream fis) {
      int imageType = figureOutImageType(fis);
      switch(imageType) {
        case CreateImageReader.GIF:
           return new GifReader(fis);
        case CreateImageReader.JPEG: 
           return new JpegReader(fis);
      }
   }
}
```