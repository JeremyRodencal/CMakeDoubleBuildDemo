add_library(ConsumingLib STATIC)
target_sources(ConsumingLib PUBLIC
    "./DependsGenerated.cpp"
)
target_include_directories(ConsumingLib PUBLIC "../")
target_link_libraries(ConsumingLib PUBLIC GeneratedInterfaceLib)
