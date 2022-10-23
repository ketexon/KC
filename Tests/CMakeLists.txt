add_executable(
    KCTest1
    test1.cpp
)

target_link_libraries(
    KCTest1
    PRIVATE Catch2::Catch2WithMain
    PRIVATE KC
)

catch_discover_tests(KCTest1)