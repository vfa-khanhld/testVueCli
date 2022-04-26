<template>
  <HeaderComponent />
  <BaseModal
    title="This is the new title from App"
    content="THis is content modal"
    theme="wrong"
  />
  <h1>Hello World</h1>
</template>

<script>
import HeaderComponent from "./components/HeaderComponent.vue";
import ModalComponent from "./components/ModalComponent.vue";

export default {
  name: "App",
  components: {
    HeaderComponent,
    BaseModal: ModalComponent,
  },
  methods: {},
};
</script>
