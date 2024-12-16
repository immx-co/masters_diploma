<template>
    <!-- <el-radio-group v-model="isCollapse" style="margin-bottom: 20px">
      <el-radio-button :value="false">expand</el-radio-button>
      <el-radio-button :value="true">collapse</el-radio-button>
    </el-radio-group> -->
    <div class="vertical">
        <el-button
        type="info"
        color="#FAEBD7"
        v-model="isCollapse" 
        v-on:click="expendCollapse" 
        :style="buttonStyle">
            {{ buttonText }}
        </el-button>
        <el-menu
            active-text-color="#0000CD"
            background-color="#FAEBD7"
            text-color="#000000"
            default-active="2"
            class="el-menu-vertical-demo"
            :collapse="isCollapse"
            @open="handleOpen"
            @close="handleClose"
        >
        <el-sub-menu index="1">
            <template #title>
            <el-icon><location /></el-icon>
            <span>Аугментировать</span>
            </template>
            <el-menu-item-group>
            <!-- <template #title><span>Group One</span></template> -->
            <el-menu-item index="1-1">Resize</el-menu-item>
            <el-menu-item index="1-2">Noise</el-menu-item>
            <el-menu-item index="1-3">Normalize</el-menu-item>
            <el-menu-item index="1-4">ColorJitter</el-menu-item>
            <el-menu-item index="1-5">Grayscale</el-menu-item>
            <el-menu-item index="1-6">Padding</el-menu-item>
            <el-menu-item index="1-7">RandomAffine</el-menu-item>
            <el-menu-item index="1-8">RandomHorizontalFlip</el-menu-item>
            <el-menu-item index="1-9">Rotation</el-menu-item>
            </el-menu-item-group>
        </el-sub-menu>
        <el-sub-menu index="2">
            <template #title>
            <el-icon><location /></el-icon>
            <span>Обучить</span>
            </template>
            <el-menu-item-group title="Детектор">
                <el-menu-item index="2-1">YOLOv5</el-menu-item>
                <el-menu-item index="2-2">YOLOv8</el-menu-item>
                <el-menu-item index="2-3">YOLOv10</el-menu-item>
            </el-menu-item-group>
            
            <el-menu-item-group title="Классификатор">
                <el-menu-item index="2-4">EfficientNet</el-menu-item>
                <el-menu-item index="2-5">MixNet</el-menu-item>
                <el-menu-item index="2-6">ResNet</el-menu-item>
            </el-menu-item-group>
        </el-sub-menu>
        <el-sub-menu index="3">
            <template #title>
            <el-icon><location /></el-icon>
            <span>Оценить</span>
            </template>
            <el-menu-item index="3-1">Детектор</el-menu-item>
            <el-menu-item index="3-2">Классфикатор</el-menu-item>
        </el-sub-menu>
        <el-sub-menu index="4">
            <template #title>
            <el-icon><location /></el-icon>
            <span>Протестировать</span>
            </template>
            <el-menu-item index="4-1">Детектор</el-menu-item>
            <el-menu-item index="4-2">Классфикатор</el-menu-item>
        </el-sub-menu>
        </el-menu>
    </div>
    
        <!-- <el-menu-item-group title="Group Two">
          <el-menu-item index="1-3">item three</el-menu-item>
        </el-menu-item-group>
        <el-sub-menu index="1-4">
          <template #title><span>item four</span></template>
          <el-menu-item index="1-4-1">item one</el-menu-item>
        </el-sub-menu> -->
      <!-- <el-menu-item index="2">
        <el-icon><icon-menu /></el-icon>
        <template #title>Navigator Two</template>
      </el-menu-item>
      <el-menu-item index="3" disabled>
        <el-icon><document /></el-icon>
        <template #title>Navigator Three</template>
      </el-menu-item>
      <el-menu-item index="4">
        <el-icon><setting /></el-icon>
        <template #title>Navigator Four</template>
      </el-menu-item> -->
    
</template>
  
<script>
    export default {
        name: "SidebarElement",
        methods: {
            handleOpen(key, keyPath) {
                console.log(key, keyPath)
            },
            handleClose(key, keyPath) {
                console.log(key, keyPath)
            },
            expendCollapse() {
                console.log("Вызвана функция expendCollapse")
                this.isCollapse = !this.isCollapse
                this.updateButtonText()
            },
            updateButtonText() {
                this.buttonText = this.isCollapse ? ">>>" : "<<<"
            }
        },
        computed: {
            buttonStyle() {
                return {
                    width: this.buttonText === "<<<" ? "200px" : "66px",
                    transition: "width 0.4s ease-in"
                }
            }
        },
        data() {
            return {
                isCollapse: true,
                buttonText: ">>>",
                
            }
        }
    }
</script>
  
<style>
  .el-menu-vertical-demo:not(.el-menu--collapse) {
    width: 200px;
    min-height: 400px;
  }

  .vertical {
    display: block;
  }
</style>
  