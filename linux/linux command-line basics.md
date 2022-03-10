

# Command line basics

| Comando | descripción                                                                                                                                        | mod                                                                                                |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| uname   | Linux kernel information                                                                                                                           | -r (version information) -v ( build information) -a (all info) -s (same)                           |
| bash    | Bash shell information                                                                                                                             | --version (distro's current bash version)                                                          |
| type    | Shows external commands and built-in (states command is built into shell) include alias                                                            |                                                                                                    |
| which   | Shows command program's (external) absolute directory referency, no show alias                                                                     |                                                                                                    |
| man     | manual pages for command, include: name, synopsis, description and . .  The synopsis section of each command's man page describes its basic syntax |                                                                                                    |
| info    | pages of information, hyperlinks to additional information, not every command has an info page                                                     |                                                                                                    |
| help    | provides help information command, if the program is bash built-in,                                                                                                    |                                                                                                    |
| pwd     | Posición donde nos encontramos                                                                                                                     |                                                                                                    |
| history | historial de la bash, se guarda en ~/.bash_history                                                                                                 | -w (obliga escribir el .bash_history que esta en memoria, al archivo), -c (limpia el history list) |
|         |                                                                                                                                                    |                                                                                                    |


## Ls

| comando | mod  | desc                                                                            |
| ------- | ---- | ------------------------------------------------------------------------------- |
| ls      | -F   | muestra sin tanta información, usa / = directorio, * = ejecutable, @ = sym link |
| ls      | -l   |                                                                                 |
| ls      | -alF |                                                                                 |




## TExt

| comando | desc                                               | ext                                                                                                                     |
| ------- | -------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| cat     | muestra el contenido de un archivo                 |                                                                                                                         |
| head    | muestra las primeras 10 lineas por defecto         | -n # (define la cantidad de lineas, pero sepuede usar el número directamente con - )                                    |
| tail    | lo mismo que el head solo que en la parte de abajo | lo mismo del anterior. -f (sirve para mostrar las últimas líneas, si el archivo se actualiza muestra las nuevas líneas) |
|         |                                                    |                                                                                                                         |
