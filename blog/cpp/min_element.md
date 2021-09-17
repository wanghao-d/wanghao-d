# std::min_element

Defined in header `<algorithm>`

```c++
// Elements are compared using operator<.
template< class ForwardIt >
ForwardIt min_element( ForwardIt first, ForwardIt last );
// Elements are compared using the given binary comparison function comp.
template< class ForwardIt, class Compare >
ForwardIt min_element( ForwardIt first, ForwardIt last, Compare comp );
```

Finds the smallest element in the range `[first, last)`.

**first, last**:	forward iterators defining the range to examine

**comp**:	comparison function object (i.e. an object that satisfies the requirements of Compare) which returns true if a is less than b.

The signature of the comparison function should be equivalent to the following:

```c++ 
 bool cmp(const Type1 &a, const Type2 &b);
```

### Example

```c++
#include <algorithm>
#include <iostream>
#include <vector>
 
int main()
{
    std::vector<int> v{3, 1, 4, 1, 5, 9};
 
    std::vector<int>::iterator result = std::min_element(v.begin(), v.end());
    std::cout << "min element at: " << std::distance(v.begin(), result);
}
```

