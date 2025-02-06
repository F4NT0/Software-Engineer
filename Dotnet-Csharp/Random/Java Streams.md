#random
Java Streams API makes handling collections more efficient, readable and declarative.

-  __stream()__ - Convert a Collection into a Stream

First step is to create a stream to process data in a pipeline
```java
List<String> names = List.of("Alice","Bob","Charlie");
Stream<String> nameStream = names.stream();
```

- __filter()__ - Keep only what you need

Filter elements based on a condition
```java
List<Integer> numbers = List.of(1,2,3,4,5);
List<Integer> evenNumbers = numbers.stream()
	.filter(n -> n % 2 == 0)
	.collect(Collectors.toList());

System.out.println(evenNumbers); // [2,4,6]
```

- __map()__ - Transform each element

Used to modify each element in a stream
```java
List<String> names = List.of("alice","bob","charlie");
List<String> upperCase = names.stream()
	.map(String::toUpperCase)
	.collect(Collector.toList());

System.out.println(upperCase); // [ALICE,BOB.CHARLIE]
```

- __flatmap()__ - Flatten Nested Structures

Flattens multiple lists into a single stream
```java
List<List<String>> listOfLists = List.of(
	List.of("A","B"),
	List.of("C","D")
);

List<String> flatList = listOfLists.stream()
	.flatMap(List::stream)
	.collect(Collectors.toList());

System.out.println(flatList); // [A,B,C,D]
```

- __forEach()__ - Iterate over elements

Executes an action for each element
```java
List.of("Java","Streams","API").forEach(System.out:println);
```

- __sorted()__ - Sort Elements

Sorts elements based on natural order or a custom comparator
```java
List<Integer> numbers = List.of(5,3,8,1);
List<Integer> sortedNumbers = numbers.stream()
	.sorted()
	.collect(Collector.toList());

System.out.println(sortedNumbers); // [1,3,5,8]
```

- __reduce()__ - Combine Elements into One value

Used to aggregate results like sum, max or concatenation:
```java
List<Integer> numbers = List.of(1,2,3,4);
int sum = numbers.stream().reduce(0,Integer::sum);

System.out.println(sum); // 10
```

- __distinct()__ - Remove duplicates

Eliminates duplicate values from a stream
```java
List<Integer> numbers = List.of(1,2,2,3,3,4);
List<Integer> uniqueNumbers = numbers.stream()
	.distinct()
	.collect(Collectors.toList());

System.out.println(uniqueNumbers); // [1,2,3,4]
```
- __limit()__ and __skip()__ - Control Elements Processed

Limit the number of elements or skip a certain amount
```java
List<Integer> numbers = List.of(1,2,3,4,5);
List<Integer> limited = numbers.stream()
	.limit(3)
	.collect(Collectors.toList());

System.out.println(limited); // [1,2,3]
```
```java
List<Integer> numbers = List.of(1,2,3,4,5);
List<Integer> skipped = numbers.stream()
	.skip(2)
	.collect(Collectors.toList());

System.out.println(skipped) // [3,4,5]
```
- Matching operators: __anyMatch()__, __allMatch()__, __noneMatch()__ 

These operators are used to check if any, all or none of the elements in a stream match a given condition. They return a boolean value.

__anyMatch()__ - Return true if at least one element matches the condition
```java
List<String> names = List.of("Alice","Bob","Charlie");
boolean startWithA = names.stream().anyMatch(name -> name.startsWith("A"));
System.out.println(startWithA); // true
```
__allMatch()__ - Returns true if all elements match the condition
```java
List<String> names = List.of("Alice","Abigail","Anaconda");
boolean allStartWithA = names.stream().allMatch(name -> name.startsWith("A"));
System.out.println(allStartWithA); // true
```

__noneMatch()__ - Returns true if none of the elements match the condition
```java
List<String> names = List.of("Alice","Bob","Charlie");
boolean noneMatch = names.stream().noneMatch(name -> name.startsWith("Z"));
System.out.println(noneMatch); // true
```

## Best Practices
- Use methods references like map(String::toUpperCase) for cleaner and more readable code
- Avoid modifying elements inside _forEach()_. use map() for transformations instead.
- Be cautions with _parallelStream()_. While it can improve performance for some large datasets, it may cause unexpected behavior in some cases.
- Prefer _anyMatch()_, _allMatch()_, _noneMatch_ over _foreach()_ when only checking conditions on stream elements. These operators are efficient and concise.