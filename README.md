# Python Algorithms

[![Build Status](https://travis-ci.org/rlishtaba/py-algorithms-playground.svg?branch=master)](https://travis-ci.org/rlishtaba/py-algorithms)


## Installation

Add this line to your application as managed dependency:

```python
py-algorithms>=0,<1
```

Or install it globally/locally using `pip` package manager:

```bash
$ pip install py-algorithms
```

## What's inside?

    ^ Data Structures
      - Deque
      - Stack (LIFO)
      - Queue (FIFO)
      - Fibonacci Heap (https://en.wikipedia.org/wiki/Fibonacci_heap)
        - Min Heap
        - Max Heap
      - Priority Queue

    ^ Search
      - Binary Search

    ^ Sorting
      - Bubble Sort

    ^ Agorithms
      - Quick Union
      - Union Find
      - Weighted Union Find
      - Weighted Union Find with Path Compression

## Usage

Check out unit test in order to take usage examples.

### Sorting Algorithms

#### Bubble Sort

Sort algorithms factory methods implementation will follow
functional interface. Old school concrete type disclosure available too as well

```python
from py_algorithms.sort import new_bubble_sort

sort = new_bubble_sort() # type: Callable[[List[T]], List[T]]
sort([20,15,0,-1,70,-88])

#=> [-88, -1, 0, 15, 20, 70]
```

### Search Algorithms

#### Binary Search

```python
from py_algorithms.search import binary_search, Search

algorithm = binary_search() # type: Search
algorithm.search([0, 6, 7, 8, 9, 4, 5, 12], 1)

#=> 12
```

### Data Structures

#### Deque

Deque implementation using doubly-linked list underneath. Operations taking
constant time.

```python
from py_algorithms.data_structures import new_deque, Deque

ds = new_deque() # type: Deque
ds.push_back(1)  #=> 1
ds.push_front(2) #=> 2
ds.front         #=> 2
ds.back          #=> 1
ds.pop_front()   #=> 2
ds.size          #=> 1
```

#### FIFO queue

```python
from py_algorithms.data_structures import new_queue, Queue

ds = new_queue() # type: Queue
ds.push(1)
ds.push(2)
ds.pop() #=> 1
ds.pop() #=> 2
ds.size  #=> 0
```

#### LIFO queue. Stack.

```python
from py_algorithms.data_structures import new_stack, Stack

ds = new_stack() # type: Stack
ds.push(1)
ds.push(2)
ds.pop() #=> 2
ds.pop() #=> 1
ds.size  #=> 0
```

#### Heap

Generic Heap using Fibonacci algorithm underneath.

##### Generic MAX Heap example (using simple comparison functor)

Make a new heap with `Max` property

```python
from py_algorithms.data_structures import new_heap, Heap

heap = new_heap(lambda x, y: (x > y) - (x < y) == 1) # type: Heap
```

Push distinct key value pairs to the heap

```python
heap.push('Kelly', 1)
heap.push('Susan', 8)
heap.push('Ryan', 7)
```

Heap should manage to keep highest key & value on the top

```python
heap.next_key #=> 'Susan'
heap.pop()    #=> 8
```
### Algorithms

#### Weighted Union Find With Path Compression

...

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/rlishtaba/py-algorithms. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.


## License

The library is available as open source under the terms of the [LGPL v3 License](http://opensource.org/licenses/LGPLv3).
