# OpenGlConfiguration

# Configuracion de entorno PArte 2
Añadir en C/C++ / Preprocesador / Definicines de procesador: 
- GLEW_STATIC;WIN32;


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

