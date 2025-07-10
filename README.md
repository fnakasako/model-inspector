Zero-Copy Safetensors Inspector

A high-performance C++ command-line utility to inspect the metadata of .safetensors files without loading the large tensor data into memory. This tool uses memory mapping (mmap) for efficient, zero-copy access to the file's header, making it extremely fast for quickly checking model information.

FeaturesInstant Metadata Reading: Reads and displays the model's metadata JSON almost instantly, regardless of file size.Zero-Copy Access: Uses memory-mapped I/O to avoid reading the entire file into RAM, resulting in minimal memory usage.Clean C++ Implementation: Built with modern C++ (C++17) and follows RAII principles for safe resource management.Simple CLI: A straightforward command-line interface for ease of use.

Core ConceptsThis project is an exercise in high-performance C++ and systems programming, focusing on:Memory Mapping (mmap): Understanding how to map a file directly into memory to avoid costly I/O operations.RAII (Resource Acquisition Is Initialization): Safely managing system resources like file handles and memory maps.Binary Data Parsing: Manually parsing the binary structure of the .safetensors format.

Building the ProjectThis project uses CMake.# Clone the repository


git clone github.com/fnakasako/model-inspector
cd zero-copy-inspector

# Configure the build
cmake -B build

# Compile the project
cmake --build build
UsageTo inspect a model file, simply provide the path to the .safetensors file../build/model-inspector inspect /path/to/your/model.safetensors
