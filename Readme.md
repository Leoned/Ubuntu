# TIPS
## Cuando aparece (base) en la terminal
Esto sucede por haber instalado y ejecutado Anaconda y la terminal conda, para desactivar ello seguir estos pasos en la terminal.

Esto también puede ser porque ```auto_activate_base``` está configurado en True. Puede verificar esto usando el siguiente comando
```conda config --show | grep auto_activate_base```

Para establecerlo falso
```conda config --set auto_activate_base False```
