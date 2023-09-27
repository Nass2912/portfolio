<template>
    <v-btn icon="" variant="outlined" @click="clickFn">
        <img src="../assets/icons8-resume-100.png" alt="resume logo" style="height: 50px" loading="lazy">
    </v-btn>
</template>

<script>
    export default {
        methods: {
            clickFn(){
                this.$emit('mainer')
            }
        }
    }
</script>

<style lang="scss" scoped>
    .v-btn {
        border: none;
        position: fixed;
        bottom: 5vh;
        right: 2vw;
        height: 9vh;
        width: 9vh;
        background: linear-gradient(90deg, rgba(144,12,63,1) 25%, rgba(199,0,57,1) 100%);
    }
</style>