<template>
    <div class="main-div">
        <Header></Header>
        <SidebarElement></SidebarElement>
    </div>
    
</template>

<script>
// import Sidebar from "./components/Sidebar.vue"
import ButtonElement from "./components/ButtonElement.vue";
import SidebarElement from "./components/SidebarElement.vue";
import Header from "./components/Header.vue";

export default {
    components: {
        ButtonElement,
        SidebarElement,
        Header
    },
    data() {
        return {
            count: 0
        }
    },
    mounted() {
        setInterval(() => {
            this.count++
        }, 1000)
    },
    methods: {
        stopCounter() {
            this.count = 0
        }
    }
}
</script>

<style>
    .main-div {
        background-color: #FAEBD7;
        min-height: 100vh;
        margin: 0;
    }

    body, html {
        margin: 0;
        padding: 0;
    }
</style>
