<template>
    <div class="demo-image">
        <div class="alignment-centered">
            <span class="demonstration">{{ currentImage }}</span>
            <el-image style="width: 700px; height: 600px" :src="currentImage" fit="cover"></el-image>
            <div class="margin-pagination">
                <el-pagination
                    background
                    layout="prev, pager, next"
                    :total="1000"
                    :current-page="currentPage"
                    @current-change="handlePageChange">
                </el-pagination>
            </div>
            
        </div>
        
            
    </div>
</template>
  
<script>
export default {
    name: "DetectorTest",
    data() {
        return {
            urls: [
                'synthetic\\test_data\\synthetic_dataset_1001.jpg',
                'synthetic\\test_data\\photo_2024-10-17_16-20-36.jpg',
                'synthetic\\test_data\\photo_2024-10-17_16-21-35.jpg',
                'synthetic\\test_data\\photo_2024-10-17_16-23-14.jpg',
            ],
            currentPage: 1
        }
    },
    computed: {
        currentImage() {
            return this.urls[this.currentPage - 1];
        }
    },
    methods: {
        handlePageChange(page) {
            this.currentPage = page;
        }
    }
}
</script>
  
<style scoped>
    .demo-image .block {
        padding: 30px 0;
        text-align: center;
        border-right: solid 1px var(--el-border-color);
        display: inline-block;
        width: 20%;
        box-sizing: border-box;
        vertical-align: top;
    }
    .demo-image .demonstration {
        display: block;
        color: var(--el-text-color-secondary);
        font-size: 14px;
        margin-bottom: 20px;
    }

    .alignment-centered {
        text-align: center;
    }

    .margin-pagination {
        margin-left: 150px;
    }
</style>
  