# Práctica 08. Funciones. Paso de parámetros. Parámetros en línea de comandos.

### Objetivos
Los objetivos de esta práctica son que el alumnado:
* Desarrolle programas sencillos en C++ que utilicen funciones y todos los tipos de sentencias estudiadas

### Rúbrica de evaluacion de esta práctica
Se señalan a continuación los aspectos más relevantes (la lista no es exhaustiva)
que se tendrán en cuenta a la hora de evaluar esta práctica:
* El alumnado ha de acreditar conocer los conceptos expuestos en el material de referencia de esta práctica.
* El alumnado ha de acreditar que ha realizado todos los ejercicios propuestos, así como ser capaz de desarrollar otros similares.
* Ha de acreditar que es capaz de escribir un fichero Makefile para automatizar el proceso de compilación de sus programas.
* El código que escriba ha de estar escrito de acuerdo a los estándares definidos en la Guía de Estilo de Google para C++.
* Todos los identificadores que utilice en su programa (constantes, variables, etc.) deberán ser
  siempre significativos. No utilice nunca identificadores de una única letra, tal vez con la excepción de las
  variables que utilice para iterar en un bucle.
* Antes de su ejecución, todos los programas que desarrolle, deben imprimir en pantalla un
  mensaje indicando la finalidad del programa así como la información que precisará del usuario para su correcta ejecución.

### Trabajo previo: introducción a Git y GitHub

GitHub es un un servicio en la nube con una interfaz web que ayuda a los desarrolladores a almacenar y administrar su código, 
así como a llevar un registro y control de cualquier cambio que se realice sobre ese código. 
Git es un sistema distribuido de control de versiones.
En Git todo el código y su historial de cambios se encuentran disponibles en el ordenador del desarrollador.
En la web puede Ud. encontrar multitud de tutoriales sobre el uso de GitHub y git.
[Este tutorial](https://www.diegocmartin.com/tutorial-git/) puede ser un buen punto de comienzo para estudiar
estas herramientas y esta [guía simple](https://rogerdudler.github.io/git-guide/) también puede servir para un
uso inicial de ellas.

A la hora de estudiar estas herramientas ha de tener en cuenta que el uso que en esta asignatura se va a
realizar de las mismas es básico: cada estudiante va a utilizar git/GitHub exclusivamente para almacenar el
código fuente de cada una de las prácticas que desarrolla. 
No se pretende que compartan código a través de git ni que colaboren en el desarrollo de código usando estas
herramientas.
También ha de tener en cuenta que un entorno de desarrollo colaborativo de programas es el escenario más
habitual y en el que estas herramientas muestran su relevancia.

Para crear un repositorio de código hay básicamente dos opciones: crear uno partiendo de cero o bien clonar
(copiar) un repositorio (que ha de ser público) del que se conozca su dirección.
En esta práctica se va a optar por la primera aproximación: crear un repositorio propio para alojar los
programas de esta práctica.

Comience su trabajo con GitHub utilizando la cuenta que creó en la primera práctica de la asignatura.
Acceda a su cuenta y siga 
[estas instrucciones](https://docs.github.com/en/free-pro-team@latest/github/getting-started-with-github/create-a-repo)
para crear un repositorio en su cuenta de GitHub.
Elija `IB-2020-2021-Practica7-Funciones` como nombre para su repositorio (en lugar de `hello-world`).
Haga que su repositorio sea privado.
El repositorio que ha creado no contiene programas y apenas contendrá un fichero README.md.
GitHub utiliza profusamente ficheros de texto con formato Markdown.
El fichero README.md (así lo indica su extensión) es un fichero Markdown.
Markdown es un lenguaje de marcas que permite aplicar formato (negrita, itálicas, imágenes, listas, etc.) a un
fichero de texto.
Este fichero que está Ud. leyendo está escrito en formato Markdown.
El formato fue ideado para elaborar textos cuyo destino iba a ser la web con más rapidez y sencillez que si se
empleara HTML.

No es neceario que aprenda Markdown en esta asignatura, pero si tiene interés por ello, esta referencia 
[Qué es Markdown, para qué sirve y cómo usarlo](https://www.genbeta.com/guia-de-inicio/que-es-markdown-para-que-sirve-y-como-usarlo)
puede servirle de introducción,
[este tutorial](https://guides.github.com/features/mastering-markdown/) es una buena referencia para un
conocimiento más profundo y por último 
[StackEdit](https://stackedit.io/) es un editor de Markdown con una interfaz web, que puede resultarle útil.

Antes de comenzar a trabajar ahora con Git, añada su clave ssh a su cuenta GitHub.
Esta tarea es posible que la realizara en la primera práctica de la asignatura, pero en caso contrario ha de
hacerlo Ud. ahora siguiendo 
[estas instrucciones](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account)
En esa página siga el enlace 
[Generated a new SSH key and added it to the ssh-agent](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
para generar una clave ssh en su máquina virtual (también puede hacer lo mismo con otros sistemas Linux con
los que trabaje habitualmente, como su instalación de VirtualBox o WSL).

Una vez configurada su clave ssh y creado su repositorio en GitHub, siga 
[estas otras instrucciones](https://docs.github.com/en/free-pro-team@latest/github/creating-cloning-and-archiving-repositories/cloning-a-repository)
para clonar el repositorio que ha creado en GitHub usando git.
Para ello, en su máquina virtual linux de la asignatura en el directorio en el que esté organizando sus
prácticas, cree un directorio con nombre `practica07-Funciones` y ejecute en linux el comando:
```
git clone git@github.com:username/IB-2020-2021-Practica7-Funciones.git practica07-Funciones
```
La dirección de su repositorio en GitHub (en el comando anterior es
`git@github.com:username/IB-2020-2021-Practica7-Funciones.git`) ha de obtenerla (cópiela de allí) en la web de GitHub tal como
se indica en las instrucciones anteriores.
De las tres opciones disponibles (HTTPS, ssh, GitHub Cli) utilice la opción ssh.

A continuación ya está todo listo para que acceda al directorio de trabajo de esta práctica (el directorio que
en este documento se ha llamado `practica07-Funciones`) y desarrolle en él todos los ejercicios de esta
práctica.
Resulta recomendable que dentro de ese directorio cree subdirectorios para cada uno de los ejercicios.
Ahora todo el trabajo ha de realizarlo de la forma habitual, editando sus programas con VSC dentro de ese
directorio y realizando todas las pruebas que considere oportunas.
Después de cada sesión de trabajo recuerde "subir" sus cambios a la nube de GitHub.
Para ello, la secuencia habitual de comandos `git` a ejecutar suele ser la siguiente:
```
$ git pull
$ git add .
$ git commit -m "Texto alusivo a los cambios realizados"
$ git push
```
* El primero de ellos `git pull` es siempre conveniente porque de ese modo se asegura que se descarga al
ordenador la última versión del código que esté alojado en la nube de GitHub.
* `git add .` actualiza el índice de git con el contenido del directorio actual (nótese el punto -directorio
  actual, el de trabajo- en el comando).
* `git commit` registra el el repositorio los cambios que se hayan realizado. A esos cambios les asocia el
mensaje de texto que aparece en el comando. 
* `git push` Actualiza (sube los cambios a la nube) el repositorio en la nube.

Explicaciones más detalladas de este "workflow" las puede hallar en el primer
[tutorial](https://www.diegocmartin.com/tutorial-git/)
que se propone en este documento.


### Ejercicios 
Al realizar los siguientes ejercicios cree dentro del repositorio de esta práctica un directorio diferente
para cada uno de los ejercicios.
Ponga a cada uno de esos directorios nombres significativos.
Haga que cada uno de sus programas conste de 3 ficheros:
* Un fichero `mi_programa.cc` (programa principal) que contendrá la función `main` e incluirá el fichero de cabecera `funciones.h`
* El fichero `funciones.h` que contendrá las declaraciones de las diferentes funciones que se utilizan en el
  programa principal para resolver el ejercicio en cuestión.
* El fichero `funciones.cc` que contendrá el código (definiciones) de las funciones declaradas en el fichero
  de cabecera.

Modifique los nombres de los ficheros que aquí se proponen para adaptarlos al ejercicio en cuestión.

1. Escriba un programa `primes.cc` que 
```
Introduzca un número: 100
2 3 5 7 11 13 17 19 23 29 31 37 41 43 47 53 59 61 67 71 73 79 83 89 97
```

2. 

3.- 

4.- 

### Referencias
* [Tutorial de Git. Manual básico con ejemplos](https://www.diegocmartin.com/tutorial-git/) 
* [Qué es Markdown, para qué sirve y cómo usarlo](https://www.genbeta.com/guia-de-inicio/que-es-markdown-para-que-sirve-y-como-usarlo)
* [Mastering Markdown](https://guides.github.com/features/mastering-markdown/)
* [StackEdit](https://stackedit.io/)
* [git - the simple guide](https://rogerdudler.github.io/git-guide/)
* [Google C++ Style Guide](https://google.github.io/styleguide/cppguide.html)
* 
