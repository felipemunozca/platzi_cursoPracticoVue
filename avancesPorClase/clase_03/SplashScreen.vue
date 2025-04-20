<!-- 
    N_3.3: Se agrega la etiqueta <template> y dentro lo primero sera agregar un contenedor con la clase "splashscreen".
    Dentro del contenedor, se agregara el logo mediante una etiqueta <img> y en la propiedad src, se agrega la ruta comenzando por 
        el arroba.
    Luego se agrega el nombre de la aplicación utilizando las etiquetas <h1> y <span>.
-->
<template>
    <div class="splashscreen">
        <img src="@/assets/cashflow-icon.svg" alt="Logo" />
        <h1><span>Cash</span>Flow</h1>
    </div>
</template>

<!-- 
    N_3.2: Se agrega la etiqueta <style> y dentro de se agregan las clases y reglas CSS que creo la profesora en la sección de 
        recursos de la clase.
    Estos estilos pueden ser modificados a mi gusto a futuro.
-->
<style scoped>
.splashscreen {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    height: 100vh;
}
h1 {
    color: var(--brand-blue);
}
h1 span {
    color: var(--brand-green);
}
</style>
