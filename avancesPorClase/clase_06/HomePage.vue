<!--
    N_6.1: En esta clase vamos a trabajar en completar el componente Resume al cual se le agregaran 2 props: 
        - uno para un label de texto
        - uno para mostrar el monto de dinero
    De momento estos props tendrán valores manuales para completar la maquetación y realizar pruebas de funcionamiento.

    N_6.2: Dentro de componente <Resume/> se agrega:
        - una variable para un label que tendrá un valor en cadena de texto. IMPORTANTE: para poder escribir dentro de comillas 
            dobles, dentro se deben utilizar comillas simples "''" y asi el valor se convierte a cadena de texto. 
        - una variable para un monto total que sera de 1.000.000
    
    N_6.7: Ya que se crearon nuevas props en el archivo IndexComponent, se debe realizar una refactorización del código en las 
        variables:
        - La variable :total-label es la que tendrá el texto por defecto
        - la variable :total-amount tendrá el valor en números
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
            />
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
    /**
     * N_6.11: Si a la variable reactiva label dentro de <Resume/> no se le agrega un valor, se produce un error, por lo que una 
     *      forma de darle libertad es creando una nueva variable para asignarle ese valor.
     * Se agrega la propiedad data.
     * Se crea la variable amount, que por defecto tendrá el valor de null.
     * 
     * N_6.14: Se crea la variable label, que por defecto tendrá el valor de null y se agrega dentro de la definición de <Resume/>.
     */
    data() {
        return {
            label: null,
            amount: null,
        };
    },
};
</script>