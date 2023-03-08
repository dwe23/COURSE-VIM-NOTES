# COURSE-VIM-NOTES
## BUSQUEDA
- Aquí tienes un **truco extra** al utilizar el manual de la ayuda de Vim: supón que quieres aprender más sobre lo que hace `Ctrl-P` en el modo insertar. Si solo buscas `:h CTRL-P`, te enviará a lo que hace `Ctrl-P` en el modo normal. Esa no es la ayuda sobre `Ctrl-P` que estabas buscando. En este caso, deberás buscar esto `:h i_CTRL-P`. El prefijo `i_` representa al modo insertar. Pon atención sobre a qué modo pertenece lo que andas buscando.

## _VIMRC
- Supongamos que necesitamos configurar las **opciones de numeración de línea** (set number). Si todavía no tienes un **archivo vimrc**, vamos a crear uno. Normalmente este archivo tendrá el nombre de `.vimrc` y se ubica en la raíz del directorio personal del usuario del sistema. Dependiendo de tu sistema operativo, la ubicación puede ser diferente. En sistemas basados en Unix como GNU/Linux o macOS estará en` ~/.vimrc`. Para ver donde deberías ubicar tu archivo, echa un vistazo a :h vimrc.
- Dentro del archivo añade una línea con lo siguiente ``set number``. Guárdalo (:w) y después haz que Vim lo tenga en cuenta ejecutando `:source %`. Ahora deberías ver los números de línea mostrados en el margen izquierdo.
    - De manera alternativa, si no quieres realizar cambios en los ajustes que se guarden de forma permanente, siempre puedes ejecutar el comando set en la línea de comandos, ejecutando ``:set number``. La contrapartida de este método es que estos ajustes son temporales. Cuando cierres Vim los cambios y opciones desaparecen

## CAPITULO 1: EJECUTANDO VIM

### GUARDANDO UN FICHERO
- También puedes escribir ``:w`` de forma abreviada. Si este es un archivo nuevo, necesitarás darle un nombre antes de **guardarlo**. Vamos a llamarlo archivo.txt. Ejecuta: ``:w archivo.txt``

### ABRIENDO UN ARCHIVO
- Desde la terminal, para **abrir** el archivo hola1.txt, ejecuta: ``vim hola1.txt``
- También puedes **abrir varios archivos** a la vez: ``vim hola1.txt hola2.txt hola3.txt``

### VER VERSION
- Para comprobar la version actual de vim en la **terminal** ``vim --version``
- Para ver la version actual **dentro** de vim ``:version``

### LINEA DE COMANDOS
- Para explorar el **historial** de la linea de comandos escribimos ``:history``
    - Para que el comando funciones, vim necesite la **funcionalidad** ``+cmdline_history``
#### EJEMPLO 
-  En Vim, puedes **sustituir** texto con el comando ``:s`` (abreviatura de :substitute). Si quieres abrir ``hola.txt`` y sustituir todo el texto *"donut"* con *"rosquilla"*, ejecuta:``vim +%s/donut/rosquilla/g hola.txt``

- También puedes añadir la opción ``-c`` seguida de un comando de Vim en vez de la sintaxis ``+``:
#### EJEMPLO 
`` vim -c %s/tarta/rosquilla/g hola.txt ``
``vim -c %s/tarta/rosquilla/g -c %s/rosquilla/huevo/g -c %s/huevo/donut/g hola.txt``

### ABRIENDO MULTIPLES VENTANAS
- Abrir  **ventanas horizontales**
    -  Para abrir Vim con 5 ventanas horizontales y ocupar las dos primeras con los archivos ``hola1.txt`` y ``hola2.txt``, ejecuta: ``vim -o5 hola1.txt hola2.txt``
- Abrir **ventanas verticales**
    - Para abrir Vim con 2 ventanas verticales ``vim -O2``

### SUSPENDER
- Vim se ejecuta en segundo plano, puedes presionar la combinación de teclas ``Ctrl-z``. También puedes ejecutar los comandos ``:stop`` o ``:suspend``. Para volver a retomar la sesión suspendida de Vim, ejecuta ``fg`` desde la terminal.

## CAPITULO2: BUFFERS, VENTANAS Y PESTANAS
## CAPITULO3: BUSCAR ARCHIVOS 
## CAPITULO4: LA GRAMATICA DE VIM 
## CAPITULO5: MOVIENDOTE POR UN ARCHIVO 
## CAPITULO6: EL MODO INSERTAR 
## CAPITULO7: EL COMANDO DEL PUNTO 
## CAPITULO8: REGISTROS
## CAPITULO9: MACROS 
## CAPITULO10: DESHACER 
## CAPITULO11: MODO VISUAL
## CAPITULO12: BUSCAR Y SUSTITUIR 
## CAPITULO13: EL COMANDO GLOBAL
## CAPITULO14: COMANDOS EXTERNOS 
## CAPITULO15: EL MODO DE LINEA DE COMANDO 
## CAPITULO16: ETIQUETAS
## CAPITULO17: PLEGADO DE TEXTO(FOLD)
## CAPITULO18: GIT 
## CAPITULO19: COMPILAR
## CAPITULO20: VISTAS SESIONES Y VIMINFO
## CAPITULO21: OPERACIONES EN MULTIPLES ARCHIVOS 
## CAPITULO22: VIMRC
## CAPITULO23: EL GESTOR DE COMPLEMENTOS DE VIM(PACKAGES)
## CAPITULO24: LOS EJECUTABLES(RUNTIME) DE VIM
## CAPITULO25: TIPOS DE DATOS BASICOS DE VIMSCRIPT 
## CAPITULO26: CONDICIONALES Y BUCLES EN VIMSCRIPT 
## CAPITULO27: VARIABLES DE VIMSCRIPT Y SU AMBITO 
## CAPITULO28: FUNCIONES DE VIMSCRIPT 
## CAPITULO29: EJEMPLO DE COMO ESCRIBIR TU PROPIO COMPLEMENTO DE VIM