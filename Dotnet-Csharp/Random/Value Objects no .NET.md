𝐀 𝐌𝐨𝐝𝐞𝐫𝐧 𝐖𝐚𝐲 𝐭𝐨 𝐒𝐨𝐥𝐯𝐞 𝐏𝐫𝐢𝐦𝐢𝐭𝐢𝐯𝐞 𝐎𝐛𝐬𝐞𝐬𝐬𝐢𝐨𝐧 𝐢𝐧 .𝐍𝐄𝐓  
  
𝐏𝐫𝐢𝐦𝐢𝐭𝐢𝐯𝐞 𝐨𝐛𝐬𝐞𝐬𝐬𝐢𝐨𝐧 is a tendency to use basic data types to represent more complex concepts. It is a common anti-pattern that can lead to unclear code and harder-to-maintain systems.  
  
Today you will learn why primitive obsession can lead to problems in your applications and how to address this issue using Value Objects in .NET.  
  
𝐏𝐫𝐢𝐦𝐢𝐭𝐢𝐯𝐞 𝐨𝐛𝐬𝐞𝐬𝐬𝐢𝐨𝐧 occurs when basic data types (such as int, string, or DateTime) are overused to represent complex concepts in your domain. This practice can lead to unclear code, bugs, and difficulty in maintaining and extending your system.  
  
The solution to this problem is to use 𝐕𝐚𝐥𝐮𝐞 𝐎𝐛𝐣𝐞𝐜𝐭𝐬, which encapsulate related data and behavior into a single, meaningful unit.  
  
𝐕𝐚𝐥𝐮𝐞 𝐎𝐛𝐣𝐞𝐜𝐭𝐬 represent a value in your domain that has no identity but is defined by its attributes. For example, an Address might be a Value Object, as it is defined by its properties (Street, City, Zip).  
  
Value Objects are a key concept in Domain-Driven Design (DDD).  
  
𝐊𝐞𝐲 𝐜𝐡𝐚𝐫𝐚𝐜𝐭𝐞𝐫𝐢𝐬𝐭𝐢𝐜𝐬 𝐨𝐟 𝐕𝐚𝐥𝐮𝐞 𝐎𝐛𝐣𝐞𝐜𝐭𝐬:  
  
- 𝐈𝐦𝐦𝐮𝐭𝐚𝐛𝐢𝐥𝐢𝐭𝐲: once created, a Value Object cannot be changed. Any modification results in a new instance.  
  
- 𝐄𝐪𝐮𝐚𝐥𝐢𝐭𝐲: value Objects are compared based on their properties, not by reference.  
  
- 𝐒𝐞𝐥𝐟-𝐯𝐚𝐥𝐢𝐝𝐚𝐭𝐢𝐨𝐧: they ensure that their state is always valid by enforcing constraints on their properties.  
  
I can list the following most popular options for creating value objects:  
- using ValueOf library  
- using C# Records  
- using C# Record Structs  
  
Records are a wonderful choice for value objects, but they are reference types. If you care about memory allocations, you can use readonly record structs for Value Objects. They behave the same as records but they are value types and not allocated on the heap.  
  
This is my personal choice for creating Value Objects.  
  
If you want to learn how to implement a 𝐕𝐚𝐥𝐮𝐞 𝐎𝐛𝐣𝐞𝐜𝐭 pattern, make sure to check my full blog post on this topic:  
[https://lnkd.in/eWdwc69d](https://lnkd.in/eWdwc69d)

![[Pasted image 20250205103056.png]]