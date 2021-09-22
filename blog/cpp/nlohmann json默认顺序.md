# nlohmann::json

Json是“多个名称/值对的无序集合”，因此不需要保留对象的特定顺序。

> The default type `nlohmann::json` uses a `std::map` to store JSON objects, and thus stores object keys **sorted alphabetically**.
>

### Example

```c++
#include <iostream>
#include "json.hpp"

using json = nlohmann::json;

int main()
{
    json j;
    j["one"] = 1;
    j["two"] = 2;
    j["three"] = 3;

    std::cout << j.dump(2) << '\n';
}
```

Output:

```c++
{
  "one": 1,
  "three": 3,
  "two": 2
}
```