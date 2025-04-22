<!-- 
    N_4.9: Se agrega un div con la clase header para agregar nuevos estilos CSS.
    Dentro tendrá al componente <slot> que debe llevar un nombre que debe ser igual al definido en el template de HomePage.
-->
<template>
    <div class="header">
        <slot name="header"></slot>
    </div>
</template>

<!-- 
    N_4.10: Se copian y pegan los estilos CSS creados por la profesora y dejados en la sección de recursos del curso.
-->
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
