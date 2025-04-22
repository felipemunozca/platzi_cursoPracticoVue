<!-- 
    N_4.1: En esta clase comenzaremos a llenar la aplicación.
    Se crearan dos nuevos componentes para el header y el layout.
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
