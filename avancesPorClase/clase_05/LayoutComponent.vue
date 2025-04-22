<!--
    N_5.8: Al igual que con el header, se deben crear slots para las dos partes nuevas del layout, resume y movements.
    Se agrega un nuevo div con clase resume, para que obtenga las clases CSS que la profesora creo en la clase anterior, y dentro 
        se agrega un <slot> con el mismo nombre que el mismo nombre que se definió en HomePage.vue utilizando numeral #.
    De la misma forma, se crea un div y un slot para movements.

    N_5.9: Ya que la idea es que la sección de movements este oculta y solo aparezca cuando se presiona en el contenedor que parece 
        tener un botón que señaliza que eso se puede presionar o arrastrar (si se esta en un smartphone), se debe crear una nueva 
        estructura para movements.
    Lo primero es mover todo a un nuevo div con la clase head, para utilizar las clases CSS creadas por la profesora en clases 
        anteriores.
    Dentro se agrega un nuevo div con la clase grip, que sera esa especie de botón alargado y delgado.
    Se agrega un nuevo div con la clase body que sera el cuerpo del componente y este es el elemento que va a llevar el <slot>.
    
    N_5.10: Ya que la estructura de movements esta definida, se puede comenzar a definir las acciones.
    Dentro del div con la clase body, se crea una reactividad utilizando v-show y cambiar el valor de la variable "showMovements" a 
        verdadero o falos y asi mostrar u ocultar el componente.
    Antes se debe crear un evento que active el cambio por lo que se agrega @click para que cada vez que alguien haga clic en head, 
        el valor de la variable cambiara a su valor contrario.
-->
<template>
    <div class="header">
        <slot name="header"></slot>
    </div>
    <div class="resume">
        <slot name="resume"></slot>
    </div>
    <!--
    <div class="movements">
        <slot name="movements"></slot>
    </div>
    -->
    <div class="movements">
        <div class="head" @click="showMovements = !showMovements">
            <div class="grip"></div>
        </div>
        <div class="body" v-show="showMovements">
            <slot name="movements"></slot>
        </div>
    </div>
</template>

<!--
    N_5.13: Si se levanta el servidor, se producirá un error debido a que no hay una función setup definida, por lo que para 
        solucionarlo, se puede agregar la propiedad setup a la etiqueta <script> y con eso ya se puede levantar el servidor y 
        probar si se puede mostrar y ocultar el componente movements.
-->
<script setup>
/**
 * N_5.11: Se importa la función ref que es parte de vue.
 * Se utilizara para volver a una variable reactiva.
 */
import { ref } from "vue";

/**
 * N_5.12: Se declara la variable "showMovements" que se utilizara en el head y body del div movements.
 * La cual sera igual a la función ref() que utilizara un valor booleano y sera false por defecto. (El componente estará oculto 
 *      por defecto).
 */
const showMovements = ref(false);
</script>

<style scoped>
.header,
.resume,
.movements {
    display: flex;
    justify-content: space-around;
    align-items: center;
    padding: 14px 0;
    box-sizing: border-box;
}

.header {
    position: fixed;
    width: 100vw;
}

.resume {
    min-height: 100vh;
}

.movements {
    z-index: 1;
    position: absolute;
    flex-direction: column;
    bottom: 0;
    width: 100vw;
    background-color: white;
    box-shadow: 0 -8px 16px #e5e5e5;
    border-radius: 24px;
}

.movements .head {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 24px;
    width: 100%;
    box-sizing: border-box;
}

.movements .body {
    height: 75vh;
    width: 100%;
}

.movements .head .grip {
    width: 120px;
    height: 8px;
    background-color: #e5e5e5;
    border-radius: 4px;
}
</style>
