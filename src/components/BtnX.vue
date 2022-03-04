<template>
    <button type="button" :class="btnclass">{{text}}</button>
</template>
<script>
export default {
    props: {
        text: String,
        btnclass: String
    }

}
</script>
<style lang="">
    
</style>