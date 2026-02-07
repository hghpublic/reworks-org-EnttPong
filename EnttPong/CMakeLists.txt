target_sources(${target} PRIVATE
    main.cpp
)

add_subdirectory(components)
add_subdirectory(core)
add_subdirectory(systems)