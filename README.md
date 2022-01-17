# adsr
[read in english](https://github.com/teaecetyrannis/adsr/blob/main/README_EN.md)
<br><br>
objeto para generar envolventes adsr, inspirado en el objeto adsr~ de max/msp, desarrollado en [pure data](https://github.com/pure-data/pure-data)


## instalación
descargar el archivo adsr.zip de la [última release](https://github.com/teaecetyrannis/adsr/releases/tag/v1.0), extraer y agregar la carpeta contenedora al path de pure data, luego se puede iniciar desde cualquier parche creando el objeto `[adsr~]`


## funcionamiento
- la primera inlet recibe velocity (entre 0 y 1, a menos que no asuste la posibilidad de disorsión e inversión de fase en caso de usar números negativos)
- la segunda inlet recibe una serie de mensajes:
    - `[att $1(` tiempo de ataque en ms
    - `[dec $1(` tiempo de decaimiento en ms
    - `[sus $1(` valor del sostenimiento (otra vez entre 0 y 1, de otra manera podría ocurrir distorsión o inversión de fase)
    - `[rel $1(` tiempo de relajamiento en ms
    - `[legato $1(` prende o apaga el legato (valor distinto a cero y cero, respectivamente)
    - `[anticlick $1(` prende o apaga (valor distinto a cero y cero, respectivamente) una rampa a 0 de 10ms antes de atacar nuevamente cuando legato está apagado que sirve para evitar generar clicks por el inmediato salto al 0 que se da cuando está apagado
    - `[state(` escribir en un mensaje el estado actual de la abstracción
