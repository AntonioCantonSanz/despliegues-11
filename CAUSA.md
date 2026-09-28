Informe del Bug Visual: Causas y Solución

1. Inicio del Ejercicio y Fork

El primer paso consistió en realizar un "Fork" del repositorio original para tener una copia en mi propia cuenta de GitHub y poder trabajar sobre ella.

2. Descripción del Problema (El Bug)

Al abrir y revisar el archivo index.html en el navegador, la página parecía correcta a simple vista, pero faltaban los enlaces de navegación del menú superior.

Al pasar el ratón o seleccionar el texto de esa zona, se confirmó que los enlaces ("Servicios" y "Contacto") estaban ahí, pero eran invisibles porque tenían el mismo color que el fondo.

3. Identificación de la Causa Raíz

Revisando el código fuente en VS Code, específicamente en el archivo styles.css, se localizó el error en la línea 20. La regla CSS .nav__menu a asignaba un color: white; a los enlaces, lo que provocaba que se camuflaran con el fondo blanco de la cabecera.

La solución fue modificar ese valor por un color visible (por ejemplo, el verde del logo o un tono oscuro).

4. Control de Versiones (Commit y Push)

Una vez guardado el arreglo en styles.css, se registraron los cambios en Git y se subieron al repositorio remoto en GitHub con un mensaje descriptivo de la solución.

5. Despliegue en Producción

Finalmente, se configuró GitHub Pages para desplegar la página web directamente desde la rama main.

Primero, el sistema comenzó a compilar el entorno:


Y tras un par de minutos, el sitio web quedó publicado y accesible públicamente con el bug solucionado:


Enlace final del proyecto: https://antoniocantonsanz.github.io/despliegues-11/

git add causas.md
git add "Captura de pantalla 2026-09-28 094942.png"
git add "Captura de pantalla 2026-09-28 095731.png"
git add "Captura de pantalla 2026-09-28 095248.png"
git add "Captura de pantalla 2026-09-28 095536.png"
git commit -m "Añade archivo causas.md con la explicación del bug y capturas"
git push origin main