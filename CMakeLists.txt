include(FetchContent)

FetchContent_Declare(
    Common
    GIT_REPOSITORY https://github.com/cmake-paul/common.git
    GIT_TAG main
)

FetchContent_MakeAvailable(Common)

add_library(PlatformB)

add_subdirectory(include)
add_subdirectory(src)

target_link_libraries(
    PlatformB
    PUBLIC
    Common
)

register_with_common(IMPLEMENTATION PlatformB)
