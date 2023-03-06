# COURSE-VIM-NOTES
## CAPITULO 1: EJECUTANDO VIM
### BUSQUEDA
- Aquí tienes un **truco extra** al utilizar el manual de la ayuda de Vim: supón que quieres aprender más sobre lo que hace `Ctrl-P` en el modo insertar. Si solo buscas `:h CTRL-P`, te enviará a lo que hace `Ctrl-P` en el modo normal. Esa no es la ayuda sobre `Ctrl-P` que estabas buscando. En este caso, deberás buscar esto `:h i_CTRL-P`. El prefijo `i_` representa al modo insertar. Pon atención sobre a qué modo pertenece lo que andas buscando.
### _VIMRC
- Supongamos que necesitamos configurar las **opciones de numeración de línea** (set number). Si todavía no tienes un **archivo vimrc**, vamos a crear uno. Normalmente este archivo tendrá el nombre de `.vimrc` y se ubica en la raíz del directorio personal del usuario del sistema. Dependiendo de tu sistema operativo, la ubicación puede ser diferente. En sistemas basados en Unix como GNU/Linux o macOS estará en` ~/.vimrc`. Para ver donde deberías ubicar tu archivo, echa un vistazo a :h vimrc.
- Dentro del archivo añade una línea con lo siguiente ``set number``. Guárdalo (:w) y después haz que Vim lo tenga en cuenta ejecutando `:source %`. Ahora deberías ver los números de línea mostrados en el margen izquierdo.
    - De manera alternativa, si no quieres realizar cambios en los ajustes que se guarden de forma permanente, siempre puedes ejecutar el comando set en la línea de comandos, ejecutando ``:set number``. La contrapartida de este método es que estos ajustes son temporales. Cuando cierres Vim los cambios y opciones desaparecen
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