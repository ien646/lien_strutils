include(FetchContent)
FetchContent_Declare(
  catch2
  GIT_REPOSITORY https://github.com/catchorg/Catch2
  GIT_TAG c4e3767e265808590986d5db6ca1b5532a7f3d13 # v2.13.7
)
FetchContent_MakeAvailable(catch2)

SET(SOURCES
    src/main.cpp
    src/contains.cpp
    src/replace.cpp
    src/split.cpp
    src/toupper_tolower.cpp
    src/trim.cpp
)

add_executable(lien_strutils_tests ${SOURCES})
set_target_properties(lien_strutils_tests PROPERTIES
  CXX_STANDARD 17
  CXX_STANDARD_REQUIRED ON
  CXX_EXTENSIONS OFF
)
target_link_libraries(lien_strutils_tests lien_strutils Catch2::Catch2)