Learn X in Y minutes
Where X=Scala
There are no primitive types in Scala(unlike java). All data types in Scala are objects that have methods to operate on their data. 
All of Scala’s types exist as part of a type hierarchy.

#Root → Any: Every class is a subclass of Any, At the top of the hierarchy is class Any.
#Tthis are the method that every class defined in scala would inherence
final def ==(that: Any): Boolean
final def !=(that: Any): Boolean
def equals(that: Any): Boolean
def ##: Int
def hashCode: Int
def toString: String

#Example of Any
// Creating object 
object Geeks  
{ 
  
    // Main method 
    def main(args: Array[String])  
    { 
        #A value list that has Any
        val list: List[Any] = List( 
                false, //Boolean
                66677, //Integer
                732,  //Integer
                'a',  //Char
                "abs" //String 
                    ) 
  
        list.foreach(element => println(element)) 
    } 
} 

#The root class Any has two subclasses → AnyVal and AnyRef

#AnyVal
#AnyVal is the parent class of value classes in
#There are nine value classes built into Scala: Byte, Short, Char, Int, Long, Float, Double, Boolean, (java primitive types) and Unit
#The value classes support the usual arithmetic and boolean operators as methods. For instance, Int has methods named + and *, and 
#Boolean has methods named || and &&.

#Example of AnyVal
def check(in: AnyVal) = ()

check(42)  //Int --> AnyVal
check(13.37) //Double --> Anyval

check(new Object) //--> AnyRef = fails to compile

#AnyRef
#Base class of all reference classes in Scala
#All non-value types are defined as reference types
#Every user-defined type in Scala is a subtype of AnyRef.
#On the Java platform AnyRef is in fact just an alias for class java.lang.Object
#For example: a sequence, list, a string, iterators

#Example AnyRef
object Geeks 
{ 
  
    // Main method 
    def main(args: Array[String]) 
    { 
        val list: List[AnyRef] = List( 
        "GFG", "GEEKSFORGEEKS" //Two strings who belong to AnyRef class
            ) 
  
        list.foreach(element => println(element)) 
    } 
} 

#Bottom → null and nothing
#At the bottom of the type hierarchy there are two classes scala: Null and scala.Nothing. These are special types that handle some “corner cases” of Scala’s object-oriented type system 
#in a uniform way.

#Null
#Class Null is the type of the null reference
#Is a subclass of every reference class (i.e., every class that itself inherits from AnyRef).
#Null is not compatible with value types. You cannot, for example, assign a null value to an integer variable

#Example of Null
val thing: Strong =
if (test)
  'Yay!' //:String
else:
  null  //:Null
  
#Nothing
#Type Nothing is at the very bottom of Scala’s class hierarchy
#Is a subtype of every other type
#There exist no values of this type whatsoever
#One use of Nothing is that it signals abnormal termination

#Example of Nothing
def error(message: String): Nothing =
throw new RintimeException(message)

def divide(x: Int, y: Int): INt = 
if (y != 0) x/y
else error("can't divide by zero")

#Defining your own value classes
#For a class to be a value class, it must have exactly one parameter and it must have nothing inside it except defs.
#No other class can extend a value class, and a value class cannot redefine equals or hashCode.
#To define a value class, make it a subclass of AnyVal, and put val before the one parameter.


class Dollars(val amount: Int) extends AnyVal {
  override def toString() = "$" + amount
}

References:
https://www.geeksforgeeks.org/scala-type-hierarchy/
https://ktoso.github.io/scala-types-of-types/
Odersky, M. Spoon, L. Venners, B. (2016) Programming in scala(3rd edition). WALNUT CREEK, CALIFORNIA: ARTIMA PRESS












































