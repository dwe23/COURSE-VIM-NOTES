# COURSE-VIM-NOTES
---
## BUSQUEDA
- Aquí tienes un **truco extra** al utilizar el manual de la ayuda de Vim: supón que quieres aprender más sobre lo que hace `Ctrl-P` en el modo insertar. Si solo buscas `:h CTRL-P`, te enviará a lo que hace `Ctrl-P` en el modo normal. Esa no es la ayuda sobre `Ctrl-P` que estabas buscando. En este caso, deberás buscar esto `:h i_CTRL-P`. El prefijo `i_` representa al modo insertar. Pon atención sobre a qué modo pertenece lo que andas buscando.

## _VIMRC
- Supongamos que necesitamos configurar las **opciones de numeración de línea** (set number). Si todavía no tienes un **archivo vimrc**, vamos a crear uno. Normalmente este archivo tendrá el nombre de `.vimrc` y se ubica en la raíz del directorio personal del usuario del sistema. Dependiendo de tu sistema operativo, la ubicación puede ser diferente. En sistemas basados en Unix como GNU/Linux o macOS estará en` ~/.vimrc`. Para ver donde deberías ubicar tu archivo, echa un vistazo a :h vimrc.
- Dentro del archivo añade una línea con lo siguiente ``set number``. Guárdalo (:w) y después haz que Vim lo tenga en cuenta ejecutando `:source %`. Ahora deberías ver los números de línea mostrados en el margen izquierdo.
    - De manera alternativa, si no quieres realizar cambios en los ajustes que se guarden de forma permanente, siempre puedes ejecutar el comando set en la línea de comandos, ejecutando ``:set number``. La contrapartida de este método es que estos ajustes son temporales. Cuando cierres Vim los cambios y opciones desaparecen

## CAPITULO 1: EJECUTANDO VIM
***

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
---
### BUFFERS
#### QUE SON LOS BUFFERS
- Espacio en la memoria en el que puedes escribir y editar algún texto
- Al abrir vim abres un buffer
EJEMPLO 
    - Cuando presiono ``vim index1.html index2.html`` se me **abren** 2 buffers
- Puedes **mostrar** todos los buffers mediante el comando ``:buffers`` (también puedes usar ``:ls`` o ``:files``).

#### FORMAS DE DESPLAZARSE EN LOS BUFFERS
IR AL SIGUIENTE O PREVIO BUFFER

- ``:bnext`` o de manera **abreviada** puedes utilizar ``:bn`` para ir al **buffer siguiente** (``:bprevious`` o ``:bp`` para ir al **buffer previo**).

IR A UN BUFFER BUSCANDO POR SU NOMBRE
    
- ``:buffer + nombre_de_archivo``. De manera **abreviada** puedes utilizar ``:b``. Vim puede autocompletar el nombre de archivo con Tab.

BUSCAR UN BUFFER POR SU NUMERO
    
- ``:buffer + n``, donde n es el número del buffer. También puedes reemplazar ``:buffer`` por ``:b``. Por ejemplo, escribiendo: ``:buffer 2`` o ``:b 2`` te llevará al buffer número 2.

SALTAR DIFFERNTES BUFFERS

- Salta a la antigua posición en la lista de saltos con ``Ctrl-O`` y a la nueva posición con ``Ctrl-I``. (Estos no son métodos específicos para buffers, pero pueden ser utilizados para saltar entre diferentes buffers. Explicaré más detalles sobre los saltos en el capítulo 5.)

IR A UN BUFFER PREVIAMENTE EDITADO
    
- Ir al buffer previamente editado con ``Ctrl-^``.

#### ELIMINAR BUFFERS
- Para eliminar el buffer en el que estas actualmente presiona ``:bdelete`` 
    - Este comando puede seguir luego del numero del buffer. Ej ``bdelete 3`` o el nombre 
    del arhivo Ej `:bdelete buffer_name``

### LEAVE OUT VIM
- Cerrar todos los buffers a la vez ``:qall``
- Cerrar todos los buffers sin guardar cambios ``:qall!``
- Guardar y salir ``:wqall``

### WINDOWS
#### QUE ES UNA VENTANA
- Una ventana es una división gráfica en un buffer

#### ATAJOS
``split nombre_del_archivo`` abre una ventana **horizontalmente**
``vsplit nombre_del_archivo`` abre una ventana **verticalmente**
``Ctrl-W H ``   Mueve el cursor a la ventana de la **izquierda**
``Ctrl-W J ``  Mueve el cursor a la ventana **inferior**
``Ctrl-W K``Mueve el cursor a la ventana **superior**
``Ctrl-W L``    Mueve el cursor a la ventana de la **derecha**
``:buffer nombre_del_archivo`` Para **cambiar** de buffer en una misma ventana
``:new nombre_de_archivo ``      Crea una **nueva ventana**
``:quit`` **Cerrar una ventana**
``:h window`` Para **mas informacion**
- En el modo normal 
``Ctrl-W V ``   Abre una nueva **división vertical**
``Ctrl-W S``    Abre una nueva **división horizontal**
``Ctrl-W C``    **Cierra** una ventana
``Ctrl-W O ``   Hace que la **ventana actual** sea la **única** en la pantalla y cierra las demás ventanas

### TABS 
- Una pestaña en una **colección de ventana**
- Cuando cierras una pestaña en Vim, **no estás cerrando un archivo**. Recuerda, Vim almacena los archivos en la memoria mediante los buffers. Cerrar una pestaña (o una ventana) no hace que ese archivo desaparezca, todavía permanecen abierto en de los buffers.
#### COMANDOS
``:tabnew archivo.txt``    Abre archivo.txt en una **nueva pestaña**
``:tabclose``              Cierra la **pestaña actual**
``:tabnext``            Ir a la **próxima pestaña**
``:tabprevious``        Ir a la **pestaña previa**
``:tablast``            Ir a la **última pestaña**
``:tabfirst``           Ir a la **primera pestaña**
``gt``  **Moverse** entre pestanas (puede ir acompanado con el numero de buffer)
``vim -p archivo1.js archivo2.js archivo3.js`` **Arrancar** vim con multiples pestanas

**OJO** Tmux no es igual a pestanas
## CAPITULO3: SEARCH FILES 
***
``:edit archivo.txt`` To **open** a file 
>We can use ``*`` as a wildcard
EXAMPLE 
``:edit *.yml<Tab>`` vim will show all the files that contain ``.yml`` extension

>To search even inside your files to your project you can use ``**``. You can move through the files that have the similiar filters  with ``<tab>``
EXAMPLE 
``:edit **/*.md<Tab>`` In this example we are going inside of one of our files and we are searching all the markdown files that are inside this file

>We can use vim file explorer named ``netrw`` to the following ways
``:edit .`` To open netrw in a current file
``:edit name_file`` To open netrw in a scpecific file

### Find and Path 
To difference to ``:edit`` ``:find`` allow to you to specify in what files do you want to do a research. For example if you want research ``sport.txt`` in only ``/carpet1`` and   ``/carpet2``, you can do it using ``find``
To save the directories that you want to do the research, we use the command ``path``
``:set path?``To see the directories saved 
``,`` Is a caracter that separated each directory saved
``.``Is to related to the currency file
``:set path+=$PWD/**`` To attach all the file that you have in the currency directory to the path
``:set path-=`` To remove the current directory use
``:set path+=``To add the current directory use
``:set path=.`` To search relative to the directory of the current file
``:set path=,,``To search in the current directory use an empty string between two commas. 
> You can see the difference between to two last clicking on the following link 
[link to see the difference](https://thunder-giraffe-8fd.notion.site/set-path-don-t-store-your-paths-when-you-leave-vim-e59002ef35144a23813c192db4eb184f)
### GREP
- Search **phrases** in a differents files 
#### EXTERNAL GREP
- It has the following **sintaxis**  ``:vim /patrón/ archivo``
EXAMPLE 
    - If we want to search all the **file that contains the character** ``hola``, you can do
    that writing the following  ``:vim hola name_to_file``
    - We can include **wildcards** Ej ``:vim hola VIM_COURSE/*``,``:vim hola VIM_COURSE/**.txt``,etc
-  To see all the results we can use quickfix. There are some commands to use this: 
``:copen ``       **Abrir** la ventana quickfix
``:cclose``      **Cerrar** la ventana quickfix
``:cnext``        Ir al **siguiente** error
``:cprevious ``   Ir al error **anterior**
``:colder  ``     Ir a la lista de errores **mas antigua**
``:cnewer``       Ir a la lista de errores **mas nueva**
#### INTERNAL GREP
- You can see the structure clicking the following link: 
[link to see the estructure](https://thunder-giraffe-8fd.notion.site/GREP-dc7059cf7604412281e57d8d831c4aa1)
#### NETRW
- At the same you open vim, you can start netrw
```
vim .   To the file when you are
vim src/client/  To your selected file
:Explore     Inicia netrw en el archivo actual
:Sexplore    No es broma. Inicia netrw en una pantalla dividida en la mitad superior
:Vexplore    Inicia netrw en una pantalla dividida en la mitad izquierda
%    Crear un nuevo archivo
d    Crear un nuevo directorio
R    Renombra un archivo o directorio
D    Elimina un archivo o directorio
```
- On this, you can use **vim movements**
- If you other **alternative**, you can use nerdtree
## CAPITULO4: LA GRAMATICA DE VIM'
### SUSTANTIVOS(MOVIMIENTOS)
```
h    Izquierda
j    Abajo
k    Arriba
l    Derecha
w    Mover el cursor hacia adelante al principio de la palabra siguiente
}    Saltar al siguiente párrafo
$    Ir al final de la línea
```
### VERBOS(OPERADORES)
```
y    **Copiar** un texto (*yank* en Vim sería la acción de copiar, de ahí la letra `y`)
d    **Eliminar** un texto y guardarlo en el registro (*delete* en Vim sería la acción de eliminar, de ahí la letra `d`)
c    **Eliminar** un texto, guardarlo en el registro y comenzar en el modo de insertar
```
### OBJETOS DE TEXTO (mas sustantivos)
- Selecciona un objeto entre parentesis y lo elimina. Lo puede hacer de las siguietnes formas 
```
i + objeto    Dentro del objeto de texto
a + objeto    Fuera del objeto de texto
```
EJEMPLO 
```
const hello = function() {
  console.log("Hello Vim");
  return true;
}
```
- Para eliminar por completo el texto **"Hello Vim"**: di(.
- Para eliminar el contenido de la **función (rodeado por {})**: di{.
- Para eliminar la palabra **"Hello"**: diw.

LISTA DE OBJETOS 
```
w         Una palabra
p         Un párrafo
s         Una frase (*sentence* en inglés)
( o )     Un par de ( )
{ o }     Un par de { }
[ o ]     Un par de [ ]
< o >     Un par de < >
t         Etiquetas XML (*tags* en inglés)
"         Un par de " "
'         Un par de ' '
`         Un par de ` `
```
## CAPITULO5: MOVIENDOTE POR UN ARCHIVO 
- Para inhabilitar las direccionales del teclado escribir el siguiente codigo:
```
noremap <Up> <NOP>
noremap <Down> <NOP>
noremap <Left> <NOP>
noremap <Right> <NOP>
```

## CAPITULO6: EL MODO INSERTAR 
## CAPITULO7: EL COMANDO DEL PUNTO 
- Como repetir una accion
Repetiremos la accion de cambiar una palabra por otra 
1. Buscar una palabra con ``\`` 
2. Escribir ``cw(palabra a reemplazar)``
3. ``n`` Para encontrar la siguiente coincidencia 


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
