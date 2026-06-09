# Phantom-Client

A lightweight C++ Bedrock ghost client with native Apple-style UI.

## Features
- Pure C++ implementation (no external dependencies)
- Native Apple appearance UI
- INS launcher integration
- Minimal footprint
- Bedrock server compatibility

## Requirements
- C++17 or higher
- macOS 10.14+
- No external dependencies

## Project Structure
```
Phantom-Client/
├── src/
│   ├── core/
│   │   ├── client.hpp
│   │   ├── client.cpp
│   │   ├── protocol.hpp
│   │   └── protocol.cpp
│   ├── ui/
│   │   ├── apple_ui.hpp
│   │   └── apple_ui.cpp
│   ├── net/
│   │   ├── connection.hpp
│   │   └── connection.cpp
│   └── main.cpp
├── include/
│   └── phantom.hpp
├── CMakeLists.txt
└── LICENSE
```

## Building
```bash
mkdir build
cd build
cmake ..
make
```

## License
Apache License 2.0
