find_package(BISON)
find_package(FLEX)

BISON_TARGET(MyParser pddlparser.yy ${CMAKE_CURRENT_BINARY_DIR}/pddlparser.cpp 
                DEFINES_FILE ${CMAKE_CURRENT_BINARY_DIR}/pddlparser.hpp)
FLEX_TARGET(MyScanner pddlscanner.ll  ${CMAKE_CURRENT_BINARY_DIR}/pddlscanner.cpp)
ADD_FLEX_BISON_DEPENDENCY(MyScanner MyParser)

include_directories(${CMAKE_CURRENT_BINARY_DIR} "../include")
file(GLOB_RECURSE SRC_FILES
    "${CMAKE_CURRENT_SOURCE_DIR}/*.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/*.cc"
)
add_executable(${PROJECT_NAME} ${SRC_FILES} ${BISON_MyParser_OUTPUTS} ${FLEX_MyScanner_OUTPUTS})
#target_link_libraries(${PROJECT_NAME} ${FLEX_LIBRARIES}) # 不需要