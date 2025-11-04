cmake_minimum_required(VERSION 3.14)
project(HelloTest)

Вмикаємо тести
enable_testing()

Знаходимо Google Test (встановіть через vcpkg або apt, якщо потрібно)
find_package(GTest REQUIRED)

Основна програма
add_executable(hello_main main.cpp)

Тести
add_executable(runTests test.cpp)
target_link_libraries(runTests GTest::gtest GTest::gtest_main)

Додаємо тест
add_test(NAME HelloUnitTest COMMAND runTests)
