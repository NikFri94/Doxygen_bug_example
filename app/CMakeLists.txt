# Makefile für Subprojekt Hauptanwendung

# Set paths to resource files
# Example:
#set(CMAKE_AUTOUIC_SEARCH_PATHS "res/MainWindow")

qt_add_executable(ET2_App
	src/main.cpp
)

# Linker
target_link_libraries(ET2_App
    PRIVATE
        Qt6::Widgets
)

# Setzen der Anwendungseigenschaften
set_target_properties(ET2_App
    PROPERTIES
        WIN32_EXECUTABLE ON
        MACOSX_BUNDLE ON
)