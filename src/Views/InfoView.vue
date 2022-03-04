<template>
  <div class="info">
    <HeaderC title="Billing" />
    <div class="account_bubbles">
        <div v-for="info in infoM" :key="info.account_id">
            <h3>{{info.first_name}}</h3>
        </div>
    </div>
  </div>
</template>
<script>
import HeaderC from "../components/HeaderC.vue";

export default {
  name: "InfoView",
  components: {
    HeaderC,
  },
  props: {
    infoM: Array,
  },
};
</script>
<style scoped></style>
