set(CMAKE_CXX_STANDARD 11)

add_executable(testPro test.cpp ${CMAKE_SOURCE_DIR}/helloWorld.h ${CMAKE_SOURCE_DIR}/helloWorld.cpp)

find_package(Catch2 CONFIG REQUIRED)
target_link_libraries(testPro PRIVATE Catch2::Catch2)
target_include_directories(testPro PUBLIC ${CMAKE_SOURCE_DIR} /home/ec2-user/Catch2/include)

enable_testing()
add_test(NAME testPro COMMAND testPro)
