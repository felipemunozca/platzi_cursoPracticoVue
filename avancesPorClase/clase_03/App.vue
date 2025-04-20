<!-- 
    N_3.1: Se crea un nuevo archivo en la carpeta components donde se creara una splash screen, es decir, una pantalla inicial con 
        el logo y el nombre de la aplicación, mientras logra cargar el resto de los componentes.
    (Para este proyecto que es ligero, realmente no es necesario crear un splash screen, pero no hay nada malo en aprender a hacerlo 
        para futuros proyectos).

    N_3.8: Para poder hacer la carga asíncrona en el template para que primero muestre el componente Splash y luego Home vamos a 
        utilizar el componente <Suspense> de Vue.
    Suspense es un componente que va a recibir dos template:
        - default -> va a mostrar el componente que tiene que mostrar una vez que todo termine de cargar.
        - fallback -> primer componente que se cargara sobre cualquier otro.
-->
<template>
    <Suspense>
        <template #default>
            <Home />
        </template>
        <template #fallback>
            <Splash />
        </template>
    </Suspense>
</template>

<script>
/**
 * N_3.4: Se importa el componente splashscreen para que cargue en cuanto inicie la aplicación.
 * Luego se agrega el valor de Splash dentro de components, y finalmente, dentro del template.
 * Con esto ya se puede levantar el servidor de desarrollo.
 *
 * N_3.6: Se importa la función defineAsyncComponent que es parte de vue.
 * Se utilizara para cargar ciertos componentes con asincronismo.
 * Ahora utilizaremos esta función con el componente Home, se agrega dos puntos seguidos de la función defineAsyncComponent() y 
 *      dentro se define otra función flecha que debe devolver un import del componente. Pero como se quiere crear un retardo para 
 *      que primero se vea el splash screen y luego el home, se utilizara una promesa para darle unos segundos de diferencia.
 *
 * N_3.7: Se crea una nueva promesa con Promise() y dentro una función flecha y para demorar la carga del componente, se utiliza la 
 *      función setTimeout() y se retardara la carga por 2500 milisegundos o 2.5 segundos.
 * Se agrega el resolve de la promesa para resolverla, donde se agregara el import con la ruta de HomePage.
 * IMPORTANTE: no es necesario agregar el arroba.
 */
import Splash from "@/components/SplashScreen.vue";
// import Home from "@/components/HomePage.vue";
import { defineAsyncComponent } from "vue";

export default {
    components: {
        Splash,
        Home: defineAsyncComponent(
        () =>
            new Promise((resolve) => {
                setTimeout(() => {
                    resolve(import("./components/HomePage.vue"));
                }, 2500);
            })
        ),
    },
};
</script>

<!--
    N_3.5: Ya tenemos la pantalla splash cubriendo al componente App.vue pero falta agregar los estilos CSS propios de este archivo.
    Se utilizan los estilos facilitados por la profesora, y pueden ser cambiados a gusto del estudiante en cualquier momento.
    Se agrega una fuente, y se crean variables de colores que se utilizaran en varios componentes.
-->
<style>
html,
body,
.app {
    min-height: 100vh;
    margin: 0;
    font-family: Arial, Helvetica, sans-serif;
}

* {
    --brand-green: #04b500;
    --brand-blue: #0689b0;
}
</style>

<!-- 
    N_3.9: Se realiza un cambio en el archivo package.json cambiando el código del comando serve: 
    Original:
        "serve": "vue-cli-service serve",
    Nuevo: 
        "serve": "npm run lint --fix && vue-cli-service serve", 
-->
