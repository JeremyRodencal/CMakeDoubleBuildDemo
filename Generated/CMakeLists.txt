set(GENERATION_INPUT "${PROJECT_SOURCE_DIR}/inputs/input.txt")
set(GENERATION_OUTPUT "${CMAKE_CURRENT_SOURCE_DIR}/Generated.hpp")
cmake_path(NATIVE_PATH GENERATION_INPUT NORMALIZE GENERATION_INPUT_NORMALIZED)
cmake_path(NATIVE_PATH GENERATION_OUTPUT NORMALIZE GENERATION_OUTPUT_NORMALIZED)
add_custom_command(
    COMMAND copy "${GENERATION_INPUT_NORMALIZED}" "${GENERATION_OUTPUT_NORMALIZED}"
    DEPENDS "${GENERATION_INPUT}"
    OUTPUT "${GENERATION_OUTPUT}"
)

add_library(GeneratedInterfaceLib INTERFACE
    "${GENERATION_OUTPUT}"
)
