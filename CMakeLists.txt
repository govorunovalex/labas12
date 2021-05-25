� ��cmake_minimum_required(VERSION 2.8)
#Проверка версии CMake.
    set(PROJECT_NAME Test)
#Создаем обычную локальную переменную с именем проекта
    project($
	    {
	    PROJECT_NAME}

)
#Название проекта
    set(text_editor text_editor)
#Переменная с именем библиотеки
    set(text_editor_lib text_editor_lib)
#Переменная с именем библиотеки
    set(text_editor_test text_editor_test)
    set(CMAKE_CONFIGURATION_TYPES "Debug;Release" CACHE STRING "Configs"
	FORCE)
#Создается переменная CMAKE_CONFIGURATION_TYPES со значением "Debug;Release" и меткой/разделом Configs, переменная сохраниется в специальном файле доступном из всех файлов,
    if (NOT CMAKE_BUILD_TYPE)
#проверка имеющихся у компилятора вариантов сборки
    set(CMAKE_BUILD_TYPE Release)
#Если нет то устанавливаем Release
	endif()
	include_directories($
			    {
			    CMAKE_CURRENT_SOURCE_DIR}
			    /text_editor_lib)
    include_directories($
			{
			CMAKE_CURRENT_SOURCE_DIR}

			/gtest)
    add_subdirectory(text_editor)
#Собираем проект в поддиректории vector
    add_subdirectory(text_editor_lib)
#Собираем проект в поддиректории lib
    add_subdirectory(text_editor_test)
    add_subdirectory(gtest)
#file(GLOB hdrs "*.h*") #Добавляем в переменную hdrs все файлы с расширением .h
#file(GLOB srcs "*.cpp") #Добавляем в переменную srcs все файлы с расширением .h
