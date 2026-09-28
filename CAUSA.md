# Resolución del Bug Visual: Enlaces Invisibles en Menú de Navegación

## 1. Identificación del problema
Tras realizar el *fork* del repositorio original y clonarlo en local:

![Mi fork](mi%20fork.png)

Abrí el archivo `index.html` en el navegador. En una primera revisión, el menú de navegación superior parecía estar vacío a la derecha del logotipo. 

Sin embargo, al seleccionar el área con el ratón, se reveló que los enlaces "Servicios" y "Contacto" sí estaban presentes, pero tenían un color de texto blanco sobre un fondo de cabecera también blanco, haciéndolos completamente invisibles al usuario.

![Página con el bug](foto%20sin%20cambio%20de%20la%20pagina.png)

## 2. Análisis del código y causa raíz
Al inspeccionar el código fuente para encontrar el origen de este comportamiento, revisé la hoja de estilos (`styles.css`). 

El error se encontraba en la línea 20 del archivo CSS. La regla que afecta a los enlaces dentro del menú de navegación (`.nav__menu a`) tenía definida la propiedad `color: white;`. Como el contenedor padre (`.header`) tiene definido un fondo blanco, se producía el camuflaje del texto.

![Código CSS original](foto%20sin%20cambio%20de%20codigo.png)

## 3. Corrección del bug
Para solucionar este problema de contraste y accesibilidad, modifiqué la regla CSS de la línea 20 cambiando el color blanco por un color gris oscuro para que los enlaces destaquen sobre el fondo blanco y mantengan la coherencia con el resto del diseño.

El código modificado quedó así:

![Código CSS corregido](foto%20con%20cambio%20de%20codigo.png)

Y el resultado visual en la página web se aprecia a continuación:

![Página web corregida](foto%20con%20cambio%20de%20la%20pagina.png)

## 4. Registro de cambios (Commit y Push)
Una vez comprobado en el entorno local que el cambio solucionaba el problema visual sin romper ninguna otra parte de la interfaz, procedí a registrar la solución en el control de versiones.

Se ejecutaron los comandos necesarios en la terminal para añadir el archivo modificado, crear el *commit* con un mensaje descriptivo de la acción realizada y subir los cambios a la rama principal (`main`) del repositorio remoto en GitHub:

![Comandos de la terminal](terminal%20aplicando%20cambios.png)

## 5. Despliegue en GitHub Pages
El último paso fue publicar la solución. Accedí a la configuración del repositorio en GitHub (pestaña *Settings* > *Pages*) y configuré el despliegue automático desde la rama `main`. 

Tras unos minutos de procesamiento por parte de GitHub, la página quedó desplegada y accesible públicamente, confirmando que el flujo de trabajo de integración y despliegue se completó con éxito.

![Despliegue en GitHub Pages](url%20del%20pages.png)


Trabajo realizado por Manuel Ruiz y Antonio Cantón.