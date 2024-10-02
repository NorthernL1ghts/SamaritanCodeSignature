# Code Signature

**Samaritan** supports a broad range of programming languages and syntaxes, accommodating both compiled and interpreted languages. This includes popular languages such as Python and C++. 

- Python is predominantly used within Samaritan for its modularity, allowing for flexible and efficient code development. Its dynamic nature and extensive libraries make it ideal for various components of the system, including core algorithms and modular extensions. C++ is employed for larger-scale projects, such as data preprocessing and performance-critical tasks, where its speed and efficiency provide significant advantages.

To maintain code consistency and readability, the following naming conventions are used across the codebase:
- **PascalCase**: Used for method names, e.g., `Run()`, to denote public methods and functions.
- **Public variables**: Named directly without a prefix, e.g., `VarName`, for variables that are intended to be accessible from outside the class.
- **Global variables**: Prefixed with `g_`, e.g., `g_Configuration`, indicating variables that are accessible throughout the application.
- **Private members**: Prefixed with `m_`, e.g., `m_PrivateData`, denoting class-level variables that should not be accessed directly from outside the class.
- **Static variables**: Prefixed with `s_`, e.g., `s_StaticValue`, representing class-level variables that are shared among all instances of the class.
- **Handles**: Prefixed with `h_`, e.g., `h_FileHandle`, used for resources or external references like file handles and database connections.
- **Constants**: Prefixed with `c_`, e.g., `c_MaxValue`, indicating values that remain unchanged throughout the program.
- **Booleans**: Prefixed with `b_`, e.g., `b_IsActive`, used for variables that hold true/false values.

### Example in C++

- Here is an example of a C++ class using the described naming conventions:
```cpp
class DataProcessor {
public:
    // Public variable
    int VarName;

private:
    // Private member
    int m_DataValue;
    
    // Static variable
    static const int s_MaxBufferSize = 1024;
    
    // Handle
    FILE* h_FileHandle;

public:
    // Constructor
    DataProcessor() : m_DataValue(0), h_FileHandle(nullptr), VarName(0) {}

    // Method to initialize data
    void Initialize() {
        // Initialize the file handle
        h_FileHandle = fopen("data.txt", "r");
        if (h_FileHandle != nullptr) {
            b_IsActive = true;
        }
    }

    // Method to process data
    void ProcessData() {
        // Process data
        if (b_IsActive) {
            // Implementation
        }
    }

    // Destructor
    ~DataProcessor() {
        if (h_FileHandle != nullptr) {
            fclose(h_FileHandle);
        }
    }

private:
    // Boolean variable
    bool b_IsActive;
};
```

### Example in Python

Here is an example of a Python class following the naming conventions:

```python
class DataProcessor:
    # Static variable
    s_MaxBufferSize = 1024
    
    def __init__(self):
        # Public variable
        self.VarName = 0
        # Private member
        self.m_DataValue = 0
        # Handle
        self.h_FileHandle = None
        # Boolean variable
        self.b_IsActive = False
    
    def Initialize(self):
        # Initialize the file handle
        try:
            self.h_FileHandle = open("data.txt", "r")
            self.b_IsActive = True
        except IOError:
            self.b_IsActive = False
    
    def ProcessData(self):
        # Process data
        if self.b_IsActive:
            # Implementation
            pass
    
    def __del__(self):
        if self.h_FileHandle is not None:
            self.h_FileHandle.close()
```
