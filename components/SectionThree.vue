<template>
    <div class="container">
        <div class="row">
            <div class="col-auto" style="width: 12.5%;"></div>
            <div class="col-md-9" style="color: white;">
                <div class="row">
                    <div class="col-md-6"></div>
                    <div class="col-md-6">
                        <h1 v-html="data.title" style="margin-bottom: 50px;"></h1>
                        <p v-html="data.description"></p>
                    </div>
                </div>
            </div>
            <div class="col-auto" style="width: 12.5%;"></div>
        </div>
        <div class="row">
            <div class="col-auto" style="width: 12.5%;"></div>
            <div class="col-md-3 m-2" v-for="(item,idx) in data.dataSlider" :key="idx" style="position: relative;">
                <div 
                    class="card" 
                    :style="{ backgroundImage: `url(${item.featured.aws_file_url}/${item.featured.path}/${item.featured.filename.big})` }"
                    @mouseenter="toggleHover(item.featured_hover, 'enter')"
                >
                    <p class="title">{{ item.link.title }}</p>
                </div>
                <div 
                    class="card overlay"
                    :style="{ backgroundImage: `url(${hoverImage})`, width:`${hoverWidth}` }"
                    @mouseleave="toggleHover(item.featured_hover, 'leave')"
                >
                </div>
            </div>
            <div class="col-auto" style="width: 12.5%;"></div>
        </div>
    </div>
</template>

<script>
    export default {
        props:["data"],
        data() {
            return {
                hoverImage:'',
                hoverWidth: '0%',
            }
        },
        methods: {
            toggleHover(images, state) {
                this.hoverImage = `${images.aws_file_url}/${images.path}/${images.filename.raw}`
                if(state == 'enter')
                    this.hoverWidth = '100%'
                else 
                    this.hoverWidth = '0%'
            }
        }
    }
</script>

<style scoped>
    .card {
        position: relative;
        width: 100%;
        min-height: 450px;
        object-fit: contain;
        background-size: cover;
        background-position: center;
    }

    .title {
        position: absolute;
        bottom: 50px;
        left: 50px;
        color: white;
        text-transform: uppercase;
    }

    .overlay {
        position: absolute;
        bottom: 0;
        left: 0;
        right: 0;
        overflow: hidden;
        width: 0;
        height: 100%;
        transition: .3s;
    }
</style>