# DiagramaDeClases 




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
    - 
    title : String
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
