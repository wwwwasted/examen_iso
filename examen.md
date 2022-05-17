## Examen 1 Evaluación 3 Jimena González Rico

1.- Desde tu directorio personal, crea un fichero en /tmp llamado ev3ex1.txt que contenga tu nombre utilizando una única orden (por supuesto sin utilizar ningún editor).
```bash
jimena@A201_PC01:~$ echo Jimena > /tmp/ev3ex1.txt
```
2.- Muestra por pantalla el número de ficheros que tiene el directorio /bin (es decir, la salida tiene que ser únicamente un número).
```bash
jimena@A201_PC01:~$ ls /bin | wc -l
```
3.- Muestra por pantalla todos los archivos del directorio /bin que tengan por lo menos dos vocales en su nombre, suponiendo que te encuentras en tu directorio personal.
```bash

```
4.- Estando en tu directorio personal, muestra por pantalla la quinta línea del fichero /etc/passwd.
```bash
jimena@A201_PC01:~$ cat /etc/passwd | sed '5!d'
```
5.- Sabemos que el fichero /usr/share/dict/spanish contiene un listado de palabras en castellano. Calcula el número de palabras de este fichero que tienen un número impar de letras. Por tanto, la salida del comando deberá ser un único número.
```bash

```
6.- Indica qué expresiones regulares utilizarías para identificar los siguientes patrones, utiliza la sintaxis del motor ERE y suponiendo que la cadena buscada es el único contenido de cada línea. Se valora la precisión en la expresión regular para que detecte únicamente el elemento que se pide.

a) Un NIF. Ejemplos: 2345678f, 71.555.333N, 10.333.222-T, …
```bash
jimena@A201_PC01:~$ sed -nE '/[0-9]{8}[A-Z]{1}/p' fichero
```
b) Una matrícula de coche (formato nuevo y antiguo). Ejemplos: 2288FSF, 4441KSD, LE3308G, A1234AJ, …
```bash
FORMATO NUEVO: jimena@A201_PC01:~$ sed -nE '/[0-9]{4}[A-Z]{3}/p' fichero
FORMATO ANTIGUO: jimena@A201_PC01:~$ sed -nE '/[A-Z]{1,2}[0-9]{4}[A-Z]{2}/p' fichero
```
c) Una fecha de la forma 04/05/2021
```bash
jimena@A201_PC01:~$ sed -nE '/[1-31]{1,2}[1-12]{1,2}[0-9999]{1-4}/p' fichero
```
d) Una dirección MAC. Ejemplos: 00-09-0F-FE-00-01, 3C:A0:67:43:D3:92, …
```bash
jimena@A201_PC01:~$ sed -nE '/[0-9A-Fa-f]{2}[: -]{1}([0-9A-Fa-f]{2}[: -]{1}[0-9A-Fa-f]{2}[: -]{1}([0-9A-Fa-f]{2}/p'
```
e) Una dirección IP. Ejemplos: 192.168.1.31, 10.0.0.1, 172.255.255.1, …
```bash

```
7.- En clase hicimos una práctica en la que utilizábamos el editor sed para extraer datos de un fichero csv y convertirlos a formato json aunque es algo que se puede extrapolar a cualquier formato.

Supón que tienes un fichero CSV con la siguiente estructura:

nombre, apellidos, email, telefono, localidad
Victor, González Rodríguez, vgonzalez@mail.com, 666444555, León
Luis, Fernández Fernández, luis@mail.com, 888777666, Villabalter
...
Indica qué órdenes deberías introducir para automatizar la extracción de datos a un fichero XML de la forma:

<usuario>
    <nombre>Victor González Rodríguez</nombre>
    <telefono>666444555</telefono>
</usuario>
Observa que hay información del fichero CSV que se descarta (mail y localidad). Por otro lado, obviaremos las etiquetas de apertura y cierre del documento XML por claridad, limitándote a generar el código XML indicado.
```bash

```