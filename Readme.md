# TIPS
## Para instalar extras restringido, como fuente y otros
```sduo apt install ubuntu-restricted-extras```
## Gestionar archivo comprimidos
```sudo apt-get install rar unace p7zip p7zip-full p7zip-rar unrar lzip lhasa arj sharutils mpack lzma lzop cabextract```
## para poder retocar ubuntu
```sudo apt install gnome-tweak-tool```
## Cuando aparece (base) en la terminal
Esto sucede por haber instalado y ejecutado Anaconda y la terminal conda, para desactivar ello seguir estos pasos en la terminal.

Esto también puede ser porque ```auto_activate_base``` está configurado en True. Puede verificar esto usando el siguiente comando

```conda config --show | grep auto_activate_base```

Para establecerlo falso

```conda config --set auto_activate_base False```
## Para instalar archivo .sh
Ubicarse en la ruta

```sudo chmod +x archivo.sh```

Para instalar

```sudo ./archivo.sh```
## Para instalar .deb
Ejecutar en la terminal, ubicarse en la ruta del archivo y poner el siguiente código

```sudo dpkg -i archivo.deb```
## Para instalar .run
Ejecutar la terminar y ubicarse en la ruta del archivo

```sudo chmod 777 archivo.run```

Luego

```sudo ./archivo.run```
