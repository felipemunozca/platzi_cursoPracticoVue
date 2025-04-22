<!-- 
    N_4.2: El header va a ser un único elemento que se agrupara dentro de una etiqueta <header> principal.
    Dentro tendrá el logo, el titulo y un elemento <span> vació que solo se utiliza para alinear 3 elementos en 3 filas.

    N_4.3: Dentro de la imagen, se agrega un evento click con una función reload que se creara a continuación.
-->
<template>
    <header>
        <img @click="reload" src="@/assets/cashflow-icon.svg" alt="Logo" />
        <h1><span>Cash</span>Flow</h1>
        <span></span>
    </header>
</template>

<script>
export default {
    /**
     * N_4.4: Se agrega la propiedad methods.
     * Dentro se define la función reload() la cual solo utilizara javascript vanilla para recargar la pagina, cuando se presione 
     *      la imagen.
     */
    methods: {
        reload() {
            location.reload();
        },
    },
};
</script>

<!--
    N_4.5: Se copian y pegan las clases de CSS hechas por la profesora desde la sección de recursos.
    Importante recordar, que al agregar scoped a la etiqueta <style> las clases CSS que se crearon solo aplicaran a las etiquetas 
        declaradas en este archivo. 
-->
<style scoped>
header {
    display: flex;
    justify-content: space-around;
    align-items: center;
    width: 100vw;
}

img,
span {
    width: 48px;
}

h1 {
    font-size: 1.4rem;
    color: var(--brand-blue);
}

h1 span {
    color: var(--brand-green);
}
</style>
