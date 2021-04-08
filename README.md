# Diagrama De Clases 

<p align ="center">
 <image src="Pics/lectura.png"></image>
 </p>
<p></p>

He omitido todos los constructores por defecto, y en el método de ReadingItem el getName, he sustitido void por String, porque no tiene sentido
que un metodo de devolver un nombre no devuelva nada.

<p align ="center">
 <image src="Pics/ReadingItem.png"></image>
 </p>

    ReadingItem <|-- Encyclopedia : extends
    ReadingItem <|-- Magazine : extends
    ReadingItem <|-- Book : extends
    GST_Chargeable <|.. Encyclopedia : implements
    GST_Chargeable <|.. Magazine : implements
    Customer"*"--> "*"ReadingItem : Tiene
    
    
    class ReadingItem{
    <<Abstract>>
    - title : String
    - price : double

    #ReadingItem(double, String)
    #getName() String
    #getType() String
      calculatePrice()*double
      displayInfo()*void
    }

    class Customer{

    - customerName : String
    - totalPay : double
    - item : ReadingItem

    +Customer(String)
    +buy(ReadingItem)void
    +getTotalPay() double
    +toString() String
    }

    class GST_Chargeable{
    <<Interface>>
      -RATE = 0.06  : double [ReadOnly]
      +getGSTCharges() double 
    }

    class Encyclopedia{
      -year : int

      + Encyclopedia(String, double) 
    }

    class Magazine{
    -monthIssue : int
    -year : int

    +Magazine(double, String, int, int)
    }
    
    class Book{
    
    -author : String
    -year : int

    + Book(double, String, String, int)

    }
  <p align ="center">
 <image src="Pics/pet.jpg"></image>
 </p>
  
    <p align ="center">
 <image src="Pics/Animal.png"></image>
 </p>

    Animal <|-- Spider : extends
    Animal <|-- Cat : extends
    Animal <|-- Fish : extends
    Pet <|..Cat : implements
    Pet <|..Fish : implements
    

    class Animal{
    <<Abstract>>
    #legs : int

    #Animal()
    #Animal(legs : int)
    #eat() void 
    #walk()  void
    #eat() void 
    }

    class Pet{
    <<Interface>>
      
      +getName() String
      +setName(n : Sting) void
      +play()
    }

    class Spider{
      +Spider()
    }

    class Cat{
    -name : String

    +Cat()
    +Cat(n : String)
    +getName() String
    +setName(n:) String
    +play() void
    }

    class Fish{
    -name : String

    +Fish()
    +getName() String
    +setName(n : String) void
    +play() void
    }
