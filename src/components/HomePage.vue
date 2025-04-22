<!-- 
  N_5.1: Luego de revisar el Layout original en el Figma, la estructura principal de la vista se dividirá en 3 secciones:
    - la cabecera o header.
    - el contenido o resume.
    - el historial o movements.
  Se agregan dos nuevos <template> con sus respectivos id:
    # resume
    # movements

  N_5.2: Dentro de la carpeta components se crea una nueva carpeta llamada Resume. Y dentro de esta carpeta se crea un nuevo archivo llamado index.vue

  N_5.5: Se crea un nuevo archivo llamado Movements.vue
-->
<template>
  <Layout>
    <template #header>
      <Header></Header>
    </template>
    <template #resume>
      <Resume />
    </template>
    <template #movements>
      <Movements />
    </template>
  </Layout>
</template>

<script>
import Layout from "./LayoutComponent.vue";
import Header from "./HeaderComponent.vue";
/**
 * N_5.3: Se importa el nueva archivo donde ira el contenido principal.
 * Luego se agrega dentro de los componentes disponibles para utilizar dentro de la sección <template>.
 */
import Resume from "./Resume/IndexComponent.vue";
/**
 * N_5.6: Se importa el nuevo archivo donde ira el historial de movimientos.
 * Luego se agrega dentro de components para utilizarlo dentro del template.
 */
import Movements from "./MovementsComponent.vue";

export default {
  components: {
    Layout,
    Header,
    Resume,
    Movements,
  },
};
</script>
