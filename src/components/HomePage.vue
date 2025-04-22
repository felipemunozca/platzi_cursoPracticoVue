<template>
  <Layout>
    <template #header>
      <Header></Header>
    </template>
  </Layout>
</template>

<script>
import Layout from "./LayoutComponent.vue";
import Header from "./HeaderComponent.vue";

export default {
  components: {
    Layout,
    Header,
  },
};
</script>
