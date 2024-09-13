# radioPlayer

radioPlayer es un bashscript diseñado para reproducir emisoras online mediante el uso de vlc.
\
Está pensado principalmente para dispositivos con sistemas operativos Linux portable.

## Funcionalidad

El script tiene un formato muy simple; un menú que ejecuta un comando para reproducir una emisora online. 

Las distintas emisoras online se reproducen mediante el enlace al servidor de reproducción online de cada una, almacenadas en el script.
\
Si un usuario desea agregar mas emisoras, solo debe modificar el script para agregar mas opciones a la lista introduciendo el enlace al servidor de reproducción.


**Ejemplo de una emisora agregada:**
```bash
[2]="https://ice4.somafm.com/poptron-128-aac|PopTron [Pop, Indie]"
```

## Uso

Previamente es necesario tener instalado vlc
```bash
 $ sudo apt install vlc -y

# una vez instalado vlc, el comando utilizado es cvlc
$ ./radioPlayer.sh
Selección de emisora:
1) Gay FM [Electro, EDM, Pop, Remixes]
2) PopTron [Pop, Indie]
3) UnderGround 80s [SynthPop, New Wave]
4) Left Coast 70s [Mellow Rock]
0) Salir
Selecciona el número de la emisora: 1
Reproduciendo emisora... Presiona Enter para detener.
VLC media player 3.0.8 Vetinari (revision 3.0.8-0-gf350b6b5a7)

