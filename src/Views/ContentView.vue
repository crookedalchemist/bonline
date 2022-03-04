<template>
    <div class="content">
        <SideBar/>
        <InfoView v-bind:infoM="infoM"/>
    </div>
</template>
<script>
import SideBar from '../components/SideBar.vue'
import InfoView from './InfoView.vue'

export default {
    name: 'ContentView',
    components: {
        SideBar,
        InfoView
    },
    data() {
    return {
      infoM: [],
    };
  },
}
</script>
<style scoped>
    .content{
        display: flex;
        
    }
</style>