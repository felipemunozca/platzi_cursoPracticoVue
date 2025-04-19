<!--
    N_2.0: El primer paso sera la Creación del proyecto: 
    
        * PASO 1: Se abre la terminal y se escribe el comando:
            > vue create nombre_proyecto
        * El nombre del proyecto sera "cashflow"
        
        * PASO 2: Seleccionar las siguientes opciones de configuración:

            2.1. seleccionar la version, en este caso:
            > manually select features

            2.2. seleccionar paquetes:
            (*) babel
            (*) linter/formatter

            2.3. seleccionar la version de vue: 
            > 3.x

            2.4. seleccionar la version de linter:
            > ESLint + Prettier

            2.5. seleccionar como revisar errores:
            (*) Lint on save

            2.6. seleccionar como guardar las configuraciones de los paquetes:
            > In dedicated config files

            2.7. guardar la configuración por defecto para futuros proyectos?:
            > N

        * PASO 3: de vuelta en la consola, moverse a la nueva carpeta creada con el comando: 
        > cd cashflow

        * PASO 4: finalmente, levantar VISUAL STUDIO CODE con el comando:
        > code .

        * IMPORTANTE: Los dos últimos pasos son muy importantes, ya que sino linter solo estará molestando con errores ya que no 
        encuentra la ruta de ciertos archivos y mostrara en rojo muchas partes del código por defecto.

    N_2.1: Lo primero sera limpiar completamente el proyecto que se creo por defecto.
    Se borra todo el código de las etiquetas <template>, <script> y <style>.

    N_2.2: Se borra el componente HelloWorld.vue y el logo de vue dentro de la carpeta assets.

    N_2.3: Se descargan los iconos que utilizaremos desde el Figma en la sección de "archivos de clase" en Platzi y se pegan dentro 
        de la carpeta assets.

    N_2.4: Se crea un nuevo archivo en la carpeta components llamado HomePage.vue 
    (Si no se usa multi palabra, se produce un error al intentar levantar el servidor local) 

    N_2.8: Se agrega el nombre del componente dentro del template para poder ver el texto al levantar el servidor.

    N_2.9: MUY IMPORTANTE: antes de levantar el servidor, correr el comando
    > npm run lint 
    Para que revise todo el proyecto y nos alerte de posibles problemas.
    Si no existen problemas, levantar el servidor con el comando: 
    > npm run serve
-->
<template>
    <Home />
</template>

<script>
/**
 * N_2.6: Se importa el nuevo componente agregando al comienzo de la ruta el arroba @ seguido de la ruta completa y la extension 
 *      del archivo.
 */
import Home from "@/components/HomePage.vue";

/**
 * N_2.7: Se agrega la propiedad export default {}.
 * Dentro se agrega components, seguido del nombre de nuestro componente recién importado.
 */
export default {
    components: {
        Home,
    },
};
</script>

<style></style>