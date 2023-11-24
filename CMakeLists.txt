# Makefile für die Projektmappe
# QT erfordert mindestens CMak 3.16
cmake_minimum_required(VERSION 3.16)

project(ETEvalTool VERSION 1.0.0 LANGUAGES CXX)

# Mindestens C++17 erforderlich (QT)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Konfiguration für ET2
option(ET2_BUILD_TESTS "Compile unit tests" ON)

if(CMAKE_VERSION VERSION_LESS "3.7.0")
    set(CMAKE_INCLUDE_CURRENT_DIR ON)
endif()

# Setzen der QT6-Distro
set(CMAKE_PREFIX_PATH "E:\\Qt\\6.6.0\\msvc2019_64")

# QT6 suchen
find_package(Qt6 
	REQUIRED COMPONENTS 
	Core
	Core5Compat
	Widgets
	Test)
	
# Erzeuge Einstellungen für qt-projekt
qt_standard_project_setup()

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

# Subdirectories hinzufügen und verwalten
add_subdirectory(app)