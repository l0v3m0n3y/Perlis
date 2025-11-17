# Perlis
api for perl.is site for Alon Perlis epigrams database
# main
```cpp
#include "Perlis.h"
#include <iostream>

int main() {
   Perlis api;

    auto quote = api.random_quote().then([](json::value result) {
        std::cout << "Search results: " << result.serialize() << std::endl;
    });
    quote.wait();
    
    return 0;
}
```

# Launch (your script)
```
g++ -std=c++11 -o main main.cpp -lcpprest -lssl -lcrypto -lpthread -lboost_system -lboost_chrono -lboost_thread
./main
```
