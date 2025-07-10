cmake_minimum_required(VERSION 3.15)

project(DatasetVerifier LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

ADD_EXECUTABLE(dataset_verifier src/main.cpp;
src/verifier.cpp)

target_include_directories(dataset_verifier external)

# Enable Ctest testing tool.
enable_testing()

# Define the test runner executable.
add_executable(run_tests
tests/verifier.test.cpp
src/verifier.cpp # Compile the class we are testing.
)

# Give the test runner access to doctest and filesystem headers.
target_include_directories(run_tests PRIVATE external)

# Register the executable with CTest.
add_test(NAME VerifierTests COMMAND run_tests)