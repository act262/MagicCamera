cmake_minimum_required(VERSION 3.4.1)

# all cpp source here
aux_source_directory(. SRC)
aux_source_directory(bitmap SRC)
aux_source_directory(beautify SRC)

add_library(MagicBeautify
        SHARED
        ${SRC})

find_library(log-lib log)
find_library(jnigraphics-lib jnigraphics)
find_library(GLESv2-lib GLESv2)

target_link_libraries(MagicBeautify
        ${log-lib}
        ${jnigraphics-lib}
        ${GLESv2-lib})