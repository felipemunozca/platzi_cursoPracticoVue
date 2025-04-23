<!--
    N_7.1: Para completar el diseño faltaría agregar la parte de los gráficos y el botón para agregar nuevos movimientos.
    Se agrega un div con <slot> con el nombre graphic.
    Se agrega un div con <slot> con el nombre action.

    N_7.5: Finalmente, se reemplaza el valor de amountVisual por la nueva función computada para obtener el numero formateado.
-->
<template>
    <main>
        <p>{{ labelVisual }}</p>
        <!-- <h1>{{ amountVisual }}</h1> -->
        <h1>{{ amountCurrency }}</h1>
        <div class="graphic">
            <slot name="graphic"></slot>
        </div>
        <div class="action">
            <slot name="action"></slot>
        </div>
    </main>
</template>

<script>
/**
 * N_7.3: Para poder darle un formato de moneda al numero que se agrega como amount, se puede utilizar un característica que ya 
 *      existe en JavaScript que es el objeto para internalización que permite crear una notación de currency (moneda local).
 * Se crea una constante que sera igual a una nueva instancia de Intl.NumberFormat() para formatear un numero. Dentro se definen, 
 *      el idioma, español de Mexico, el estilo sera en formato de moneda y el formato de moneda sera en pesos mexicanos.
 */
/*
const currencyFormatter = new Intl.NumberFormat("es-MX", {
    style: "currency",
    currency: "MXN",
});
*/

/**
 * N_7.6: Se cambia el formato de la moneda a peso chileno, utilizando la siguiente configuración.
 */
const currencyFormatter = new Intl.NumberFormat("es-CL", {
    style: "currency",
    currency: "CLP",
});

export default {
    props: {
        totalLabel: {
            type: String,
        },
        label: {
            type: String,
            default: null,
        },
        totalAmount: {
            type: Number,
        },
        amount: {
            type: Number,
            default: null,
        },
    },
    /**
     * N_7.4: Se crea una nueva función computada que se encargara de retornar el valor de amountVisual formateandolo con la 
     *      función para obtener la moneda.
     */
    computed: {
        labelVisual() {
            return this.label !== null ? this.label : this.totalLabel;
        },
        amountVisual() {
            return this.amount !== null ? this.amount : this.totalAmount;
        },
        amountCurrency() {
            return currencyFormatter.format(this.amountVisual);
        },
    },
};
</script>