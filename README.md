# OpenGlConfiguration

> [!IMPORTANT]
> Necesitas actualizar la carpeta include.

<!--
# Configuracion de entorno Parte 2
Añadir en C/C++ / Preprocesador / Definicines de procesador: 
- GLEW_STATIC;WIN32;

Añadir en Vinculador / Entrada / Dependencias adicionales:
- glew32s.lib
# Codigo de prueba 
Aca solo es para confirmar que todo se hizo correctamente tienen que copiar el codigo de entrega en el archivo mandado por el docente
```cpp
#include <GL/glew.h>
#include <GLFW/glfw3.h>
#include <iostream>

int main(void)
{
	GLFWwindow* window;

	/* Initialize the library */
	if (!glfwInit())
		return -1;

	/* Create a windowed mode window and its OpenGL context */
	window = glfwCreateWindow(800, 600, "OpenGL", NULL, NULL);
	if (!window)
	{
		glfwTerminate();
		return -1;
	}

	/* Make the window's context current */
	glfwMakeContextCurrent(window);

	if (glewInit() != GLEW_OK)
		std::cout << "Error!" << std::endl;

	std::cout << glGetString(GL_VERSION) << std::endl;


	const char* renderer = reinterpret_cast<const char*>(glGetString(GL_RENDERER));
	std::cout << "Tarjeta gráfica: " << renderer << std::endl;

	glfwTerminate();
	return 0;
}
```


# Configuracion de entorno Parte 1 

Añadir En C/C++ / General / Directorios de inclusion adicionales: 

- $(SolutionDir)include\;%(AdditionalIncludeDirectories)

Añadir En Vinculador/ General / Directorios de bibliotecas adicionales: 

- $(SolutionDir)libs\;%(AdditionalLibraryDirectories)

Para finalizar añadir en  Vinculador/ Entrada / Dependencias adicionales:

- glfw3.lib;opengl32.lib;%(AdditionalDependencies)



# codigo de prueba
```cpp
#include <GLFW/glfw3.h>
int main(void)
{
	GLFWwindow* window;

	/* Initialize the library */
	if (!glfwInit())
		return -1;

	/* Create a windowed mode window and its OpenGL context */
	window = glfwCreateWindow(800, 600, "Mi Primera Pantalla en OpenGL", NULL, NULL);
	if (!window)
	{
		glfwTerminate();
		return -1;
	}

	/* Make the window's context current */
	glfwMakeContextCurrent(window);

	/* Loop until the user closes the window */
	while (!glfwWindowShouldClose(window))
	{
		/* Render here */
		glClear(GL_COLOR_BUFFER_BIT);

		glBegin(GL_TRIANGLES);
		glVertex2f(-0.5f, -0.5f);
		glVertex2f(0.0f, 0.5f);
		glVertex2f(0.5f, -0.5f);
		glEnd();

		/* Swap front and back buffers */
		glfwSwapBuffers(window);
		/* Poll for and process events */
		glfwPollEvents();
	}

	glfwTerminate();
	return 0;
}
```
--->

