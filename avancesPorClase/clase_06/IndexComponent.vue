<!--
    N_6.4: Se comienza a editar el template.
    El texto del label se agregara dentro de una etiqueta <p> utilizando una variable que se recibirá desde el props.
    Para el caso del monto sera lo mismo, una etiqueta <h1> con una variable.

    N_6.10: Se comentan las variables originales, para ahora utilizar propiedades computadas para imprimir dentro del template. 
-->
<template>
    <main>
        <!-- <p>{{ label }}</p> -->
        <!-- <h1>{{ amount }}</h1> -->
        <p>{{ labelVisual }}</p>
        <h1>{{ amountVisual }}</h1>
    </main>
</template>

<script>
export default {
    /**
     * N_6.5: Se utilizan las Options API para definir un JSON de configuración
     * Se agrega la propiedad props que dentro tendrá la variable label que es de tipo string y la variable amount que es de 
     *      tipo numérico.
     * 
     * N_6.6: Ya que el programa esta pensado para tener un gráfico, cuando se haga clic dentro del gráfico cambiara el label y 
     *      el valor total, por lo que conviene crear nuevas props: 
     *      - totalLabel que tendrá el texto original (por defecto) de la etiqueta.
     *      - totalAmount que tendrá el valor total de movimientos.
     * Con eso ahora label y amount cambiaran sus valores cuando se haga clic en cierta parte del gráfico.
     * 
     * N_6.9: Se agrega a la variable amount que por defecto tendrá un valor nulo, de esta forma sino se manda nada, la computada 
     *      no generara errores y buscara el valor total para mostrar.
     * 
     * N_6.13: Se agrega a la variable label que por defecto tendrá un valor nulo, de esta forma sino se manda nada, la computada 
     *      no generara errores.
     */
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
     * N_6.8: Para poder comparar los valores que se envían por ejemplo entre total-label y label o total-amount y amount se 
     *      puede crear una función computada que verifique los valores.
     * Se agrega la propiedad computed.
     * Se declara una nueva función llamada amountVisual que retornara mediante un if ternario: SI se manda al componente un monto 
     *      especifico que es DISTINTO de null, entonces que se imprima ese valor en el template, en caso contrario que muestre el 
     *      valor guardado en totalAmount.
     * 
     * N_6.12: Se crea una nueva función computada, esta vez para obtener y reemplazar el valor del label llamada labelVisual.
     * utilizando un if ternario retornara: SI se manda al componente un texto en el label especifico que es DISTINTO de null, 
     *      entonces que se imprima ese texto en el template, en caso contrario que muestre el texto guardado en totalLabel.
     */
    computed: {
        labelVisual() {
            return this.label !== null ? this.label : this.totalLabel;
        },
        amountVisual() {
            return this.amount !== null ? this.amount : this.totalAmount;
        },
    },
};
</script>

<!--
    N_6.3: Se copian y pegan los estilos CSS que creo la profesora para este componente desde la sección de Recursos.
-->
<style scoped>
main {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    width: 100%;
}

h1,
p {
    margin: 0;
    text-align: center;
}

h1 {
    margin-top: 14px;
    color: var(--brand-green);
}

.graphic {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    padding: 48px 24px;
    box-sizing: border-box;
}
</style>
