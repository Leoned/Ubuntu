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

## Para instalar driver distintos driver de video en ubuntu (Ejm. Nvidia)
Si por el bucador de controlador de ubuntu se encuntra el driver y se instala, solo queda reiniciar el equipo, si en caso no se soluciona ese procedimiento hacer el siguiente procedimiento mediante linea de comando.

```sudo nvidia-settings```

Si esto no muestra el entorno del driver proceceder lo siguiente

```ubuntu-drivers devices```

En mi caso muestra lo siguiente

```
WARNING:root:_pkg_get_support nvidia-driver-390: package has invalid Support Legacyheader, cannot determine support level
== /sys/devices/pci0000:00/0000:00:01.0/0000:01:00.0 ==
modalias : pci:v000010DEd00001C82sv00001462sd00003351bc03sc00i00
vendor   : NVIDIA Corporation
model    : GP107 [GeForce GTX 1050 Ti]
driver   : nvidia-driver-460 - distro non-free recommended
driver   : nvidia-driver-390 - distro non-free
driver   : nvidia-driver-460-server - distro non-free
driver   : nvidia-driver-465 - distro non-free
driver   : nvidia-driver-418-server - distro non-free
driver   : nvidia-driver-450-server - distro non-free
driver   : xserver-xorg-video-nouveau - distro free builtin
```

Por lo general es mejor optar la instalación por lo recomendado

```udo apt install nvidia-driver-460```

Luego se reinicia el sistema para ver los efetos de cambio con el siguiente comando

```sudo reboot```

Cuando el sistema se reinició, ejecutar el siguiente comando

```nvidia-smi```

Que en mi caso muestra lo siguiente

```
Sun Jun 27 10:29:38 2021       
+-----------------------------------------------------------------------------+
| NVIDIA-SMI 460.80       Driver Version: 460.80       CUDA Version: 11.2     |
|-------------------------------+----------------------+----------------------+
| GPU  Name        Persistence-M| Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
|                               |                      |               MIG M. |
|===============================+======================+======================|
|   0  GeForce GTX 105...  Off  | 00000000:01:00.0  On |                  N/A |
|  0%   33C    P8    N/A /  90W |    618MiB /  4038MiB |      1%      Default |
|                               |                      |                  N/A |
+-------------------------------+----------------------+----------------------+
                                                                               
+-----------------------------------------------------------------------------+
| Processes:                                                                  |
|  GPU   GI   CI        PID   Type   Process name                  GPU Memory |
|        ID   ID                                                   Usage      |
|=============================================================================|
|    0   N/A  N/A      1026      G   /usr/lib/xorg/Xorg                 71MiB |
|    0   N/A  N/A      1619      G   /usr/lib/xorg/Xorg                248MiB |
|    0   N/A  N/A      1758      G   /usr/bin/gnome-shell               76MiB |
|    0   N/A  N/A      5029      G   /usr/lib/firefox/firefox          208MiB |
|    0   N/A  N/A      5357      G   /usr/lib/firefox/firefox            1MiB |
+-----------------------------------------------------------------------------+
```

De preferencia optar por controladores mas estables, si prefiere instalar controladores mas recientes, usaremos el metodo PPA

```sudo add-apt-repository ppa:micahflee/ppa```

Para ver los controladores

```ubuntu-drivers devices```

Caso mio muestra lo siguiente, igual que en los pasos anteriores

```
WARNING:root:_pkg_get_support nvidia-driver-390: package has invalid Support Legacyheader, cannot determine support level
== /sys/devices/pci0000:00/0000:00:01.0/0000:01:00.0 ==
modalias : pci:v000010DEd00001C82sv00001462sd00003351bc03sc00i00
vendor   : NVIDIA Corporation
model    : GP107 [GeForce GTX 1050 Ti]
driver   : nvidia-driver-390 - distro non-free
driver   : nvidia-driver-450-server - distro non-free
driver   : nvidia-driver-460-server - distro non-free
driver   : nvidia-driver-460 - distro non-free recommended
driver   : nvidia-driver-418-server - distro non-free
driver   : nvidia-driver-465 - distro non-free
driver   : xserver-xorg-video-nouveau - distro free builtin
```

Instalar el controlador deseado, Ejm.

```sudo apt install nvidia-driver-465```
