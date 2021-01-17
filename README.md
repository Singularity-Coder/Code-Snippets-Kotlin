# Code-Snippets-Kotlin
List of Kotlin topics and their code snippets!

## Package definition and imports
```Kotlin
package my.demo

import kotlin.text.*
```

## Comments
```Kotlin
// Single line comment or End-of-line comment

/* Multi-line comment
or Inline comment 
or Block comment */

/**
* 
* Documentation comment used for explaining code
*
* @author 
* @param
* @return
*
* Refer https://kotlinlang.org/docs/reference/kotlin-doc.html
*
**/
```

## Constants and Variables
```Kotlin
const val user = "Singularity Coder"; // const val means Immutable or unchangeable
val user = "Singularity Coder";	// val means Immutable or unchangeable
var user = "Singularity Coder"; // var means Mutable or changable
```

## Print to Console
```Kotlin
println("Printing this and adding a line break!");
print("Just printing this! ");
print("So i am next to the previous line.");
```

## Null Stuff
Assigning the null value
```Kotlin
var value: String?
value = Nullable
val message: String? = null
log(message ?: "")
```
Verify if value is null
```Kotlin
value?.let {
    val length = value.length
}
// or simply
val length = value?.length
```

## Data Types
Unlike Java, there are no primitive types in Kotlin. All of them are reference or Object types. So by-default they are null and do not contain any defaults like primitives. There are total 9 types.

**Number Types**
* Byte
```Kotlin
val myByte: Byte = 0;
val maxByte: Byte = Byte.MAX_VALUE; // 127
val minByte: Byte = Byte.MIN_VALUE; // -128
val byteSizeInBits: Int = Byte.SIZE_BITS; // 8 bits
val byteSizeInBytes: Int = Byte.SIZE_BYTES; // 1 byte
```
* Short
```Kotlin
val myShort: Short = 0;
val maxShort: Short = Short.MAX_VALUE; // 32767
val minShort: Short = Short.MIN_VALUE; // -32767
val shortSizeInBits: Int = Short.SIZE_BITS; // 16 bits
val shortSizeInBytes: Int = Short.SIZE_BYTES; // 2 bytes
```
* Int (Inferred by default)
```Kotlin
val myInt: Int = 0;
val maxInt: Int = Int.MAX_VALUE; // 2147483647 (~ 2.14 billion)
val minInt: Int = Int.MIN_VALUE; // -2147483648 (~ -2.14 billion)
val intSizeInBits: Int = Int.SIZE_BITS; // 32
val intSizeInBytes: Int = Int.SIZE_BYTES; // 4
```
* Long
```Kotlin
val myLong: Long = 0L;
val maxLong: Long = Long.MAX_VALUE; // 9223372036854775807 (~ 9.22 * 10^18) or (~ -9.2E18)
val minLong: Long = Long.MIN_VALUE; // -9223372036854775807 (~ -9.22 * 10^18) or (~ -9.2E18)
val longSizeInBits: Int = Long.SIZE_BITS; // 64
val longSizeInBytes: Int = Long.SIZE_BYTES; // 8
```

**Decimal Types**
* Float
```Kotlin
val myFloat: Float = 0F;
val maxFloat: Float = Float.MAX_VALUE; // 3.4028235E38 (~ 3.40 * 10^38)
val minFloat: Float = Float.MIN_VALUE; // 1.4E-45 (1.4 * 10^-45)
val floatSizeInBits: Int = Float.SIZE_BITS; // 32
val floatSizeInBytes: Int = Float.SIZE_BYTES; // 4
val floatMax: Float = 1E38F; // 1.0E38, beyond this number Kotlin returns "Infinity" string. 
```
* Double (Inferred by default)
```Kotlin
val myDouble: Double = 0.0;
val maxDouble: Double = Double.MAX_VALUE; // 1.7976931348623157E308 (~ 1.79 * 10^308)
val minDouble: Double = Double.MIN_VALUE; // 4.9E-324 (4.9 * 10^-324)
val doubleSizeInBits: Int = Double.SIZE_BITS; // 64
val doubleSizeInBytes: Int = Double.SIZE_BYTES; // 8
val doubleMax: Double = 1.0E308; // 1.0E308, beyond this number Kotlin returns "Infinity" string.
```

**Others**
* String
```Kotlin
val myString: String = "I am a string!";
```
* Char
```Kotlin
val myChar: Char = 'C';
val myCharAsciiValue: Int = myChar.toInt(); // 67

// ASCII Characters

// Extended ASCII Characters

// Unicode Characters

// List all lowercase Characters
val lowCaseCharArray: Array<Char> = Array(26) { 'a' }; // 'a' is the starting value at 0th position
for (i in 0..25) lowCaseCharArray.set(i, ('a'.toInt() + i).toChar()); // [a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z]

// List all uppercase Characters
val upCaseCharArray: Array<Char> = Array(26) { 'A' }; // 'A' is the starting value at 0th position
for (i in 0..25) upCaseCharArray.set(i, ('A'.toInt() + i).toChar()); // [A, B, C, D, E, F, G, H, I, J, K, L, M, N, O, P, Q, R, S, T, U, V, W, X, Y, Z]
```
* Bool
```Kotlin
val myBoolean: Boolean = false;
```

**More**
* Any
> This Type can hold any of the above mentioned data types. It cannot hold BigInteger and BigDecimal Types.
```Kotlin
val myAnyTypeByte: Any = 72;
val myAnyTypeShort: Any = 32425;
val myAnyTypeInt: Any = 1123456789345;
val myAnyTypeLong: Any = 71234567823456734;
val myAnyTypeFloat: Any = 0F;
val myAnyTypeDouble: Any = 1.1;
val myAnyTypeString: Any = "Singularity Coder";
val myAnyTypeChar: Any = 'C';
val myAnyTypeBool: Any = true;
```
* BigInteger  
> If you are working with ridiculously large numbers, use BigInteger & BigDecimal.

> BigInteger must support values in the range -2^Integer.MAX_VALUE (exclusive) to +2^Integer.MAX_VALUE (exclusive) and may support values outside of that range.  
> 
> Implementation note: BigInteger constructors and operations throw ArithmeticException when the result is out of the supported range of -2^Integer.MAX_VALUE (exclusive) to +2^Integer.MAX_VALUE (exclusive).
```Kotlin
val myBigIntegerNum1: BigInteger = BigInteger.valueOf(Long.MAX_VALUE).pow(10); // 4455508415646675013373597242420117818453694838130159772560668808816707086990958982033203334310070688731662890013605553436739351074980172000127431349940128178077122187317837794167991459381249
val myBigIntegerNum2: BigInteger = BigInteger(Long.MAX_VALUE.toString()).pow(10); // 4455508415646675013373597242420117818453694838130159772560668808816707086990958982033203334310070688731662890013605553436739351074980172000127431349940128178077122187317837794167991459381249

// Commonly used BigInteger Numbers 
val bigInt0: BigInteger = BigInteger.ZERO; // 0
val bigInt1: BigInteger = BigInteger.ONE; // 1
val bigInt2: BigInteger = BigInteger.TWO; // 2
val bigInt10: BigInteger = BigInteger.TEN; // 10
```
* BigDecimal
```Kotlin
val myBigDecimalNum1: BigDecimal = BigDecimal.valueOf(Double.MAX_VALUE).scaleByPowerOfTen(-Int.MAX_VALUE); // 1.7976931348623157E-2147483339
val myBigDecimalNum2: BigDecimal = BigDecimal(Double.MAX_VALUE.toString()).scaleByPowerOfTen(-Int.MAX_VALUE); // 1.7976931348623157E-2147483339
val myBigDecimalNum3: BigDecimal = BigDecimal(Double.MAX_VALUE).scaleByPowerOfTen(-Int.MAX_VALUE); // 1.79769313486231570814527423731704356798070567525844996598917476803157260780028538760589558632766878171540458953514382464234321326889464182768467546703537516986049910576551282076245490090389328944075868508455133942304583236903222948165808559332123348274797826204144723168738177180919299881250404026184124858368E-2147483339

// Rounding Precision
val myDecimalNum1: BigDecimal = BigDecimal("1.1234567");
myDecimalNum1.setScale(3, RoundingMode.UP); // 1.124
myDecimalNum1.setScale(3, RoundingMode.DOWN); // 1.123
myDecimalNum1.setScale(3, RoundingMode.HALF_UP); // 1.123
myDecimalNum1.setScale(3, RoundingMode.HALF_DOWN); // 1.123
myDecimalNum1.setScale(3, RoundingMode.HALF_EVEN); // 1.123
myDecimalNum1.setScale(3, RoundingMode.FLOOR); // 1.123
myDecimalNum1.setScale(3, RoundingMode.CEILING); // 1.124

val myDecimalNum2: BigDecimal = BigDecimal("1.0");
myDecimalNum2.setScale(3, RoundingMode.UNNECESSARY); // 1.000

myDecimalNum2.setScale(3, RoundingMode.UNNECESSARY).movePointRight(1); // From 1.000 to 10.00
myDecimalNum2.setScale(3, RoundingMode.UNNECESSARY).movePointLeft(1); // From 1.000 to 0.1000

// Commonly used BigDecimal Numbers 
val bigDec0: BigDecimal = BigDecimal.ZERO; // 0
val bigDec1: BigDecimal = BigDecimal.ONE; // 1
val bigDec10: BigDecimal = BigDecimal.TEN; // 10
```

## Strings
Concatenation of strings
```Kotlin
val name: String = "Singularity Coder";
var age: Int = 129;
print("Hello World, My name is $name, and I am $age years old. In 3 years, I will be ${age + 3}. My bank balance is currently \$7."); // Hello World, My name is Singularity Coder, and I am 129 years old. In 3 years, I will be 132. My bank balance is currently $7.
```
New line in string
```Kotlin
val text = """
        |First Line
        |Second Line
        |Third Line
        """.trimMargin()
```
Substring
```Kotlin
var str = "Kotlin Programming Language"
var substr = ""

// print Kotlin
substr = str.substring(0..5)
println("substring $substr")

// print Language
substr = str.substring(18..26)
println("substring $substr")
```

## Type Casting or Type Conversion
```Kotlin
if (object is Car) { 
   var car = object as Car
}

// if object is null
if (object is Car?) {
   var car = object as Car?
}
```

## Operators 
#### Arithmetic Operators
#### Assignment Operators
#### Comparision Operators
#### Logical Operators
#### Bitwise Operators
```Kotlin
val andResult  = a and b
val orResult   = a or b
val xorResult  = a xor b
val rightShift = a shr 2
val leftShift  = a shl 2
val unsignedRightShift = a ushr 2
```

## Math

## Booleans

## Flow Control
#### Conditional Statements
Block Statement
```Kotlin
val price: Int = 59
if (price < 50) {
    println("Cheap")
} else if (price in 50..70) {
    println("Average")
} else {
    println("Expensive")
} // Average
```
When Statement (Switch-Case)
```Kotlin
val price: Int = 59
when(price) {
    30, 31, 32, 33, 34, 35 -> print("Cheap")
    in 36..50 -> print("Average")
    else -> {
        println("Too much!")
        print("Expensive as hell!")
    }
} // Too much! Expensive as hell!
```
#### Conditional Expressions
* Single Line Expression (Ternary Operations)
```Kotlin
val price: Int = 59
val priceReaction: String = if (price < 100) "Cheap" else "Expensive" // Cheap
```
* Block Expression
```Kotlin
val price: Int = 59
val priceReaction2: String = if (price < 50) {
    "Cheap"
} else {
    "Expensive"
} // Expensive
```
* When Expression (Switch-Case)
```Kotlin
val price: Int = 59
val priceReaction3: String = when {
    price <= 30 -> "Cheap"
    price in 30..50 -> "Average"
    price in 50 until 70 -> "Expensive"
    else -> "Too much"
} // Expensive
```
#### For Loop
```Kotlin
for (i in 1..10) print("$i ")  // 1 2 3 4 5 6 7 8 9 10

for (i in 1 until 10) print("$i ")    // 1 2 3 4 5 6 7 8 9

for (i in 10 downTo 0) print("$i ")    // 10 9 8 7 6 5 4 3 2 1 0

for (i in 1..10 step 2) print("$i ")    // 1 3 5 7 9

for (i in 10 downTo 0 step 2) print("$i ")    // 10 8 6 4 2 0

val list: List<Int> = listOf(1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
for (item in list) print("$item ")  // 1 2 3 4 5 6 7 8 9 10

val map: Map<Int, String> = mapOf(
        1 to "Air", 
        2 to "Bed", 
        3 to "Breakfast")
for ((key, value) in map) println("Key: $key and Value: $value")
// Key: 1 and Value: Air
// Key: 2 and Value: Bed
// Key: 3 and Value: Breakfast
```
#### ForEach (Enhanced For loop)
```Kotlin
val list: List<Int> = listOf(1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
list.forEach { it: Int ->
    print("$it ")   // 1 2 3 4 5 6 7 8 9 10
}

list.filter { it > 5 }.forEach {
    print("$it ")   // 6 7 8 9 10
}

list.stream().filter { it > 5 }.forEach {
    print("$it ")   // 6 7 8 9 10
}


list.parallelStream().filter { it > 5 }.forEach {
    print("$it ")   // 7 9 10 8 6
}
```
#### While Loop
```Kotlin
var x = 1
while (x <= 10) {
    print("$x ")  // 1 2 3 4 5 6 7 8 9 10 
    x++
}
```
#### Do-While Loop
```Kotlin
var y = 1
do {
    print("$y ")  // 1 2 3 4 5 6 7 8 9 10
    y++
} while (y <= 10)
```
#### Break
```Kotlin
for (i in 1..10) {
    print("$i ")  // 1 2 3 4 5 6 
    if (i == 6) break
}
```
#### Continue
```Kotlin
for (i in 1..10) {
    if (i == 2) continue
    if (i == 5) continue
    if (i == 8) continue
    print("$i ")  // 1 3 4 6 7 9 10 
}
```

## Data Structures
#### Arrays
* Declaring Array
```Kotlin
lateinit var lowCaseCharArray: Array<Char>;
```
* Initializing Array with a fixed size or Allocating memory
```Kotlin
val lowCaseCharArray: Array<Char> = Array(26) { 'a' }; // where 'a' is the starting value at 0th position
```
* Printing Arrays
```Kotlin
print(Arrays.toString(lowCaseCharArray));
```
* Splitting Arrays
```Kotlin
val (param, value) = "param=car".split("=")
```
#### Lists
* Sorting List
```Kotlin
val profile = loadProfiles(context)
profile.sortedWith(Comparator({ profile1, profile2 ->
    if (profile1.age > profile2.age) return@Comparator 1
    if (profile1.age < profile2.age) return@Comparator -1
    return@Comparator 0
}))
```
#### Maps
```Kotlin
val listOfNumber = listOf(1, 2, 3, 4)
val keyValue = mapOf(1 to "Air",
                     2 to "Bed",
                     3 to "Breakfast")
```
#### Set

## Functions and Methods
#### Function
Functions in Kotlin are not methods when they do not belong to a class. However they look and behave the same way. Its just the way they are accessed is different.

* Defining Function
```Kotlin
fun doSomething() {
   // logic here
}
```
* Variable number of arguments
```Kotlin
fun doSomething(vararg numbers: Int) {
   // logic here
}
```
* Defining function with return 
```Kotlin
fun getScore(): Int {
   // logic here
   return score
}

// as a single-expression function
fun getScore(): Int = score
```
* Returning result of an operation
```Kotlin
fun getScore(value: Int): Int {
   // logic here
   return 2 * value
}

// as a single-expression function
fun getScore(value: Int): Int = 2 * value
```
#### Method
Methods in Kotlin are functions that are called on objects. So they have to be inside a class.
```Kotlin
fun Int.triple(): Int {
  return this * 3
}

var result = 3.triple()
```
#### Default Parameters/Arguments
#### Named Parameters/Arguments
#### Function/Method Overloading
#### Scope
#### Recursion
#### Tail Recursion
#### Scope Functions
#### Higher Order Functions
* Functions can be stored in a variable.
```Kotlin
val operation1 = returnValue(num1 = 8, num2 = 12) // 20
val operation2 = printComment() // Hello World!

fun returnValue(num1: Int, num2: Int): Int = num1 + num2
fun printComment(): Unit = print("Hello World!")
```
* Functions can be returned from a function.
```Kotlin
fun returnFunc(): Unit = printComment() // Hello World!

fun printComment(): Unit = print("Hello World!")
```
* Functions can be passed to other functions as an argument.
```Kotlin
fun highOrderFuncNoParams(unitFunc: (() -> Unit)? = null) {
    unitFunc?.invoke()
}

fun highOrderFuncWithParams(unitFunc: (() -> Unit)? = null, imgSize: Int) {
    if (imgSize > 5) unitFunc?.invoke()
    else println("Using image with default resolution!")
}

fun highOrderFuncWithParams2(dummyApiCallback: ((dummyApiResponse: String) -> Unit)? = null) {
    val movieList: List<String> = listOf(
        "Grave of the Fireflies",
        "My Neighbor Totoro",
        "Kiki's Delivery Service",
        "Princess Mononoke",
        "Spirited Away",
        "Howl's Moving Castle",
    )

    for (movie in movieList) {
        Thread.sleep(3000)
        dummyApiCallback?.invoke(movie)
    }
}

fun voidOrUnitFunc1(num1: Int = 0, num2: Int = 0) {
    println("Void or Unit function result is ${num1 + num2}")
}

fun voidOrUnitFunc2() {
    println("Reducing Image Resolution!")
    println("Compressing Image!")
}

highOrderFuncNoParams(unitFunc = { voidOrUnitFunc1(num1 = 6, num2 = 9) })    // Void or Unit function result is 15

highOrderFuncWithParams(
    unitFunc = {
        println("Reducing Image Resolution!")
        println("Compressing Image!")
    },
    imgSize = 4
)   // Using image with default resolution! 

highOrderFuncWithParams(
    unitFunc = { voidOrUnitFunc2() },
    imgSize = 11
)   // Reducing Image Resolution! Compressing Image!

highOrderFuncWithParams2(dummyApiCallback = { dummyApiResponse: String ->
    println(dummyApiResponse)
})
// Grave of the Fireflies
// My Neighbor Totoro
// Kiki's Delivery Service
// Princess Mononoke
// Spirited Away
// Howl's Moving Castle
```
#### Extension Functions
```Kotlin
fun Int.factorial(): BigInteger {
    var fact = BigInteger.ONE
    for (i in 2..this) fact = fact.multiply(BigInteger.valueOf(this.toLong()))
    return fact
}

fun Double.squared(): Double = this * this

fun Char.asciiValue(): Int = this.toInt()

fun String.analyzeString() {
    when {
        this == "Singularity Coder" -> println("Definitely Neo!")
        this.length > 3 -> println("Not Neo!")
        else -> println("Could be Neo!")
    }
    println("String Length: ${this.length}")
    println("String starts with the letter: ${this[0]}")
    println("String mid value: ${if (this.length % 2 == 0) "No mid value!" else this[this.length / 2]}")
}

fun User.canWork(age: Int): Boolean = age > 18

val myInt: Int = 55
val myDouble: Double = 12.5
val myChar: Char = 'C'
val myString: String = "Singularity Coder"
val myUser: User = User(name = "Hithesh", age = 67)
data class User(val name: String, val age: Int)

myInt.factorial()   // 9540809681250034973565866501770328168700249765255186764678629884883775957860052585601806640625
myDouble.squared()  // 156.25
myChar.asciiValue() // 67
myUser.canWork(myUser.age)  // true
myString.analyzeString()
// Definitely Neo!
// String Length: 17
// String starts with the letter: S
// String mid value: i
```
#### Infix Function Call

## Classes and Objects
#### Creating Instance
```Kotlin
class Address1 {
    private val CUSTOM_HASH_CODE = SecureRandom().nextInt()

    var city: String = ""
    var country: String = ""
    var zip: Int = 0

    override fun toString(): String {
        return "Address(City: $city, Country: $country, Zip: $zip)"
    }

    override fun equals(other: Any?): Boolean {
        if (this === other) return true
        if (null === other) return false
        return false
    }

    override fun hashCode(): Int {
        return CUSTOM_HASH_CODE
    }
}

val address1 = Address1()
val address2 = Address1()
address1.city = "Tesla"
address1.country = "Mars Colony @#$%123"
address1.zip = 123456

println(address1.toString())	// Address(City: Tesla, Country: Mars Colony @#$%123, Zip: 123456)
println(address1.hashCode())	// 654287787
println(address1.equals(address2))	// false
```
#### Inheritance
#### Constructors
Primary Constructor
```Kotlin
class User0(val name: String = "", val age: Int = 0) 

val user0: User0 = User0(name = "Hithesh", age = 199)
println("Name: ${user0.name}")  // Name: Hithesh
println("Age: ${user0.age}")    // Age: 199
```
Secondary Constructors
```Kotlin
class User1 {
    var name: String? = null
    var age: Int? = null

    constructor(name: String = "Singularity Coder", age: Int = 77) {
        this.name = name
        this.age = age
    }

    constructor()
}

val user1: User1 = User1(name = "Singularity Coder", age = 6543)
println("Name: ${user1.name}")  // Name: Singularity Coder
println("Age: ${user1.age}")    // Age: 6543
```
Primary and Secondary Constructors
```Kotlin
class User2(private val dob: String = "", private val profession: String = "") {
    var name: String? = null
    var age: Int? = null

    constructor(name: String = "Singularity Coder", age: Int = 77) : this(dob = "", profession = "") {
        this.name = name
        this.age = age
    }

    constructor() : this(dob = "", profession = "")

    fun printDob() = println("Date Of Birth: $dob")

    fun printProfession() = println("Profession: $profession")
}

val user2: User2 = User2(dob = "12/07/0001", profession = "Magic Caster")
user2.printDob()	// Date Of Birth: 12/07/0001
user2.printProfession()	// Profession: Magic Caster
```
Private Constructor
```Kotlin
class Utils private constructor() {
}

// another way
object Utils {
}
```
#### Getters and Setters

#### Defining uninitialized objects
```Kotlin
internal lateinit var person: Person
```
#### Initialization Block
```Kotlin
class User {
	// Initialization block
    init {
        println("Init block")
    }
}
```
#### Companion Object
#### Singleton
#### Data Class
```Kotlin
data class User(var name: String, var age: Int)
```
#### Abstract Class
#### Interface
#### Sealed Classes
#### Enum Class
```Kotlin
enum class Direction(val direction: Int) {
    NORTH(1),
    SOUTH(2),
    WEST(3),
    EAST(4);
}
```
#### Anonymous Class
```Kotlin
val task = object : AsyncTask<Void, Void, Profile>() {
    override fun doInBackground(vararg voids: Void): Profile? {
        // fetch profile from API or DB
        return null
    }

    override fun onPreExecute() {
        super.onPreExecute()
        // do something
    }
}
```

## Cloning or Copying
```Kotlin
data class User(var name: String, var age: Int)

// cloning or copying
val user = User("Singularity Coder", 30)
val user2 = user.copy()
// in case you only want to copy selected properties
val user2 = user.copy(age = 25)
```

## Pair and Triple

## Lateinit and Lazy

## Exceptions

## Generics

## Lambda

## JvmStatic, JvmOverloads, and JvmField

## Visibility Modifiers

## Random Numbers
* Generate Secure Random Number. Cryptographically strong random values using a cryptographically strong pseudo-random number generator.
```Kotling
val secureRandom = SecureRandom().nextInt(100)  // 14
```
* Generate Pseudo Random Number
```Kotlin
val randomNumber = Math.random()    // 0.15076138593048494
```
* Random number in a given range. You can access all the Array properties on this random array.
```Kotlin
val randomArray = (1..10).shuffled()	// [8, 9, 1, 2, 3, 5, 7, 10, 6, 4]
val randomArrayFirstElem = (1..10).shuffled().first()   // 10
val randomArrayLastElem = (1..10).shuffled().last()     // 5
```
* Thread-safe Random Number that can have positive and negative values
```Kotlin
val randomfloat1 = ThreadLocalRandom.current().nextFloat()          // 0.23447311
val randomDouble1 = ThreadLocalRandom.current().nextDouble()        // 0.3792768572850779
val randomInteger1 = ThreadLocalRandom.current().nextInt()          // -1424838063
val randomLong1 = ThreadLocalRandom.current().nextLong()            // 6186415735628776307
val randomGaussian1 = ThreadLocalRandom.current().nextGaussian()    // 1.7022158793655815
val randomBoolean1 = ThreadLocalRandom.current().nextBoolean()      // false
```
* Thread-safe Random Number in a given range
```Kotlin
val randomDouble2 = ThreadLocalRandom.current().nextDouble(1.0, 10.0)   // 4.842464268215246
val randomInteger2 = ThreadLocalRandom.current().nextInt(1, 10)         // 2
val randomLong2 = ThreadLocalRandom.current().nextLong(1, 10)           // 8
```

## Multi-Tasking
#### Coroutines
#### RxJava
#### Executors and Handlers
#### Thread
#### AsyncTask

## Collections

## Generate Morse Code

## Meta-Programming

## Common Vocabulary
* **Expression:** A function with return value or a variable.  
* **Statement:** Code with an assignment operator.  
* **Pascal Case:** KotlinCodeSnippets  
* **Camel Case:** kotlinCodeSnippets  
* **Snake Case:** KOTLIN_CODE_SNIPPETS  
* **Main Function:** Entry point in our app.  
* **Compiler:** Translates high level language to low level language that machine can understand. Also checks for syntax errors.  
* **Run Kotlin Program:** Converts Kotlin code to Java byte code to run it on JVM. JVM further converts the Java byte code into machine code that <a href=""></a> platform like Mac or Windows can understand.  
* **Statically Typed Programming Language:** Type of a variable is known at compile-time. So once variable is declared with a type, it cannot ever be assigned to a variable of different type and doing so will result in a type error at compile-time. So you CANNOT build the app without fixing the bugs. Fast & Efficient. Ex: Kotlin, Java, C, C++, etc.  
* **Dynamically Typed Programming Language:** Type of a variable is known at run-time. Variables are bound to objects at run-time. You can assign a variable with a different an Integer type even if it was initially assigned String type. So you CAN build the app without fixing the bugs. Slow & less optimized but has its own advantages like dynamic dispatch, late binding, down-casting, reflection. Ex: JavaScript, Objective-C, PHP, Python, Ruby, Lisp, etc.  
* **Type Checking:** The process of verifying and enforcing the constraints of types.  
* **Static check:** Type check happening at compile-time.  
* **Dynamic check:** Type check happening at run-time.  
* **Strongly-typed language:** Variables are bound to specific data types, and will result in type errors if types do not match up as expected in the expression - regardless of when type checking occurs. Ex: Java, Python, etc.  
* **Weakly-typed language:** Variables are not bound to a specific data type; they still have a type, but type safety constraints are lower compared to strongly-typed languages. Ex: PHP, C, C++, etc.  
* **Top-Level function:** A function that is not enclosed in a class.  
* **Double Type:** Double-precision floating-point. More exact than Float numbers.
* **Number System:** A way of representing numbers. The value of any digit in a number can be known if we know:
	1. The Digit 
	2. Its position in the number
	3. The base/radix of the number system
* **Radix/Base:** Available numbers in a number system (or) numbers used in a system (or) number of digits used in a positional number system. Ex: base-10 numbering system or decimal numbers (0,1,2,3,4,5,6,7,8, and 9) is most common. So the radix/base for Decimal numbers is 10. Computers deal with base-2 or binary which only deals with numbers 0 and 1. So for binary numbers the radix/base is 2.
* **Types of base or Types of Number Systems:** 
	1. Base-2 (Binary): Uses only 0, 1
	2. Base-8 (Octal): Uses only 0, 1, 2, 3, 4, 5, 6, 7
	3. Base-10 (Decimal): Uses only 0, 1, 2, 3, 4, 5, 6, 7, 8, 9
	4. Base-16 (Hexadecimal): Uses only 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F
* **Signed Integer:** Whole range of integers negative, zero and positive integers. Ex: ...-3, -2, -1, 0, 1, 2, 3...
* **Unsigned Integer:** Non-negative integers including 0. Ex: 0, 1, 2, 3...

## References
1. https://kotlinlang.org/docs/reference/
2. https://github.com/MindorksOpenSource/from-java-to-kotlin
3. https://www.youtube.com/playlist?list=PL6nth5sRD25iv8jZrQWD-5dXgu56ae5m8
4. https://www.youtube.com/playlist?list=PLrnPJCHvNZuAIbejjZA1kGfLeA8ZpICB2
5. https://android.jlelse.eu/magic-lies-here-statically-typed-vs-dynamically-typed-languages-d151c7f95e2b
6. https://byjus.com/maths/number-system/
7. https://www.geeksforgeeks.org/biginteger-class-in-java/
8. https://stackoverflow.com/questions/12693273/is-there-an-upper-bound-to-biginteger
9. https://www.baeldung.com/kotlin/kotlin-random-number

