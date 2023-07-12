# Script para instalar dependencias necesarias para compilar PCSX2 en Ubuntu

Una vez instaladas las dependencias:


```console
git clone https://github.com/PCSX2/pcsx2.git --recurse
```

```console
cd pcsx2
```

```console
mkdir -p ./build && cd ./build
```

```console
cmake ..
```

```console
make -j 6
```
