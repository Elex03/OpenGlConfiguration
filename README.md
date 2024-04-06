# OpenGlConfiguration

# Configuracion de entorno 

Añadir En C/C++ / General / Directorios de inclusion adicionales: 

- $(SolutionDir)include\;%(AdditionalIncludeDirectories)

Añadir En Vinculador/ General / Directorios de bibliotecas adicionales: 

- $(SolutionDir)libs\;%(AdditionalLibraryDirectories)

Para finalizar añadir en  Vinculador/ Entrada / Dependencias adicionales:

- glfw3.lib;opengl32.lib;%(AdditionalDependencies)

