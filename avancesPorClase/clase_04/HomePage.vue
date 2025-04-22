<!--
    N_4.8: Se declara el componente Layout y dentro, se comenzara a definir cada slot de cada sección.
    Se agrega la componente <template> el cual va a tener su propio nombre utilizando el numeral #, se recomienda que el nombre 
        sea indicativo de que es, por lo que sera header.
    Dentro del <template> se agrega el componente Header.
-->
<template>
    <Layout>
        <template #header>
            <Header></Header>
        </template>
    </Layout>
</template>

<script>
/**
 * N_4.6: Se importa los componentes Layout y Header para comenzar a definir las secciones.
 */
import Layout from "./LayoutComponent.vue";
import Header from "./HeaderComponent.vue";

export default {
    /**
     * N_4.7: Se agrega la propiedad components.
     * Dentro se agrega los componentes Layout y Header.
     */
    components: {
        Layout,
        Header,
    },
};
</script>
