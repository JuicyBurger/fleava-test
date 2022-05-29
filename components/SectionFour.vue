<template>
    <div class="container flex center-items">
        <div class="row">
            <div class="col-auto" style="width: 12.5%;"></div>
            <div class="col-md-4">
                <img :src="`${data.featured.aws_file_url}/${data.featured.path}/${data.featured.filename.big}`" alt="static image" class="left-image">
            </div>
            <div class="col-md-5 bg-white" style="padding: 100px;">
                <h1 v-html="data.title_one"></h1>
                <h1 v-html="data.title_two" class="text-green"></h1>
                <div class="title-line" style="transform: translateX(150px);"></div>
                <p v-html="data.description"></p>
                <a :href="`/${data.link.url}`">{{ data.link.title }}</a>
            </div>
            <div class="col-auto" style="width: 12.5%;"></div>
        </div>
    </div>
</template>

<script>
    export default {
        props:["data"]
    }
</script>

<style scoped>
    .left-image {
        width: 100%;
        height: 100%;
    }

    @media (min-width: 768px) {
        .left-image-md {
            width: 200%;
            height: 100%;
        } 
    }
</style>