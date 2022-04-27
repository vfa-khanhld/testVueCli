<template>
  <HeaderComponent />
  <teleport to="body">
    <!-- Vi muon thg base modal ngang cap thg App nen dung teleport component de dem no ra ngoai, ngang cap cho de quan ly -->
    <BaseModal
      v-if="isShowModal"
      title="This is the new title from App"
      content="THis is content modal"
      theme="content"
      @cancel="onToggleModal"
    >
      <template v-slot:header>
        <div>
          <h2>This is Header</h2>
        </div>
      </template>
      <template v-slot:footer>
        <div>
          <button @click="onToggleModal">Close</button>
        </div>
      </template>
      <label>Password</label>
      <input type="password" />
    </BaseModal>
  </teleport>
  <button @click="onToggleModal">Toggle Modal</button>
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
  methods: {
    onToggleModal() {
      console.log("running toggle modal");
      this.isShowModal = !this.isShowModal;
    },
  },
  data() {
    return {
      isShowModal: false,
    };
  },
};
</script>
