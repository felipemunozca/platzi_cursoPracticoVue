<!--
    N_7.2: Se realiza un cambio al elemento <Resume/> ya que ahora no se puede cerrar solo /> sino que debe ser cerrado utilizando 
        otra etiqueta de cierre para asi poder colocar dentro, los template de #graphic y #action.
    De momento, solo tendrán texto para ver como quedan ordenados en el layout.
-->
<template>
    <Layout>
        <template #header>
            <Header></Header>
        </template>
        <template #resume>
            <Resume
                :total-label="'Ahorro total'"
                :label="label"
                :total-amount="1000000"
                :amount="amount"
            >
                <template #graphic> graphic </template>
                <template #action> action </template>
            </Resume>
        </template>
        <template #movements>
            <Movements />
        </template>
    </Layout>
</template>

<script>
import Layout from "./LayoutComponent.vue";
import Header from "./HeaderComponent.vue";
import Resume from "./Resume/IndexComponent.vue";
import Movements from "./MovementsComponent.vue";

export default {
    components: {
        Layout,
        Header,
        Resume,
        Movements,
    },
    data() {
        return {
            label: null,
            amount: null,
        };
    },
};
</script>
