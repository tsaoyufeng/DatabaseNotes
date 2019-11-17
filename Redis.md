## 3.1 Redis 数据类型和抽象

### Redis values

Redis不是一个简单的 key-value 存储，它实际上是一个数据结构服务器，支持不同类型的 values。这意味着，在传统的 key-value存储中你可以关联 string key 到 string values，但在Redis中， value不限于简单的string，你可以使用更复杂的数据结构。以下是Redis支持的所有数据结构：

1. Binary-safe strings （二进制安全的字符串）：字符串值内容是安全的，意味着可以把数字、文本、图片、视频等都赋给这个值。

2. Lists （列表）：根据插入顺序排序的 string 元素集合，基于链表。
3. Sets（集合）：无重复、无顺序的 string 元素集合。
4. Sorted sets（有序集合）：与 Sets相似，但每个 string 元素都会关联到一个 floating number value， 叫做 score。元素根据它们的 score 来排序，所以，与Sets不同的是它可以检索元素的范围（比如，可以请求 top 10， 或 bottom 10）。
5. Hashes（哈希）：是由 values 关联的字段组成的映射。字段和值都是 strings。与 Ruby 或 Python 的 hashes 非常相像。
6. Bit arrays (or simply bitmaps): it is possible, using special commands, to handle String values like an array of bits: you can set and clear individual bits, count all the bits set to 1, find the first set or unset bit, and so forth. 
7.  HyperLogLogs: this is a probabilistic data structure which is used in order to estimate the cardinality of a set. Don't be scared, it is simpler than it seems... See later in the HyperLogLog section of this tutorial. 
8.  Streams: append-only collections of map-like entries that provide an abstract log data type. They are covered in depth in the [Introduction to Redis Streams](https://redis.io/topics/streams-intro). 

### Redis keys

Redis 键是二进制安全的，这意味着你可以使用任何二进制序列作为一个键，例如一个字符串或是一张JPEG图像的内容。空字符串也是一个有效的键。

一些关于键的规则：

* 太长的键不太好
* 太短的键也不太好
* Try to stick with a schema.
* 被允许的最大的键的大小是 512 MB。

## 3.2 Redis 命令

### Redis strings

Redis 字符串类型是可以与 Redis 键关联的最简单的值类型。  

因为 Redis 键是字符串，所以当我们使用字符串类型当值的时候，我们是将一个字符串映射到另一字符串。字符串类型在很多案例中都是有用的，比如缓存HTML片段或页面。

### Redis Lists

### Redis Hashes

### Redis Sets

### Redis Sorted sets

### Bitmaps

### HyperLogLogs









