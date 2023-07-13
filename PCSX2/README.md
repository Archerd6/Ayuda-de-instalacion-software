# Compilar PCSX2 en Ubuntu

<div style="text-align: justify">
El script para instalar las dependencias necesarias es `Dependencias-Ubuntu.sh`. Es una sola linea de código en la que se instalan muchas de las dependencias necesarias para compilar mediante `apt install`.

Una vez instaladas las dependencias, solo se tiene que seguir los siguientes pasos:

- Clonar el repositorio
```console
git clone https://github.com/PCSX2/pcsx2.git --recurse
```

- Acceder a la carpeta del repositorio clonado
```console
cd pcsx2
```

- Crear la carpeta `build` y acceder a ella
```console
mkdir -p ./build && cd ./build
```

- Generar los archivos de construcción necesarios para compilar el proyecto.
```console
cmake ..
```

- Iniciar el proceso de compilación utilizando los archivos de construcción
```console
make -j 6
```
</div>

## Versiones anteriores de ubuntu

<div style="text-align: justify">
En algunas versiones no tan recientes de ubuntu no se pueden instalar todas las librerías correctamente, por lo que haría falta una modificación adicional para que se instalen (agregar los repositorios de `backports` de Debian Bullseye)


- Abrimos el archivo que contiene la lista de repositorios de software configurados en el sistema
```console
sudo nano /etc/apt/sources.list
```

- Vamos al final del archivo y pegues las siguientes dos líneas:
```console
deb http://deb.debian.org/debian bullseye-backports main contrib non-free
deb-src http://deb.debian.org/debian bullseye-backports main contrib non-free
```
Estas líneas añaden los repositorios de "backports" de Debian Bullseye, que son repositorios adicionales que contienen paquetes más nuevos que los que se encuentran en la distribución principal. Estos repositorios son útiles si deseas acceder a versiones más recientes de ciertos paquetes.

- Después de pegar las líneas, para guardar el archivo en `nano`, debes presionar `Ctrl+O` y luego presionar Enter para confirmar el nombre del archivo.

- Para salir del editor `nano`, debes presionar `Ctrl+X`.

</div>
