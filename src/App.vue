<template>
    <div class="main-div">
        <Header></Header>
        <div class="div-horizont">
            <SidebarElement></SidebarElement>
            <div class="alignment-center">
                <DetectorTest></DetectorTest>
            </div>
        </div>
    </div>
    
</template>

<script>
import ButtonElement from "./components/ButtonElement.vue";
import SidebarElement from "./components/SidebarElement.vue";
import Header from "./components/Header.vue";
import DetectorTest from "./components/DetectorTest.vue";

export default {
    components: {
        ButtonElement,
        SidebarElement,
        Header,
        DetectorTest
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

    .div-horizont {
        display: flex;
    }

    .alignment-center {
        margin-left: 425px;
        margin-top: 50px;
    }
</style>
