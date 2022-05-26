<template>
    <div class="container flex center-items">
        <div class="row" style="padding: 100px;">
            <div class="col-lg-6 col-md-12 col-sm-12">
                <img :src="`${data.featured.aws_file_url}/${data.featured.path}/${data.featured.filename.big}`" alt="example resort image" class="featured-img">
            </div>
            <div class="col-lg-6 col-md-12 col-sm-12 flex center-items" style="position: relative;">
                <div class="bg-shade bg-box"></div>
                <div style="z-index: 100; padding: 100px;">
                    <h1 v-html="data.title" style="margin-bottom: 50px;"></h1>
                    <p v-html="data.description"></p>
                    <p :href="`/${data.link.url}`" style="margin: 20px 0px;">{{ data.link.title }}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props:["data"],
        mounted() {

        }
    }
</script>

<style scoped>
.featured-img {
    position: relative;
    width: auto;
    height: 650px;
    z-index: 101;
}

.center-items {
    justify-content: center;
    align-items: center;
}

.bg-box {
    position: absolute;
    top: 0;
    left: -300px;
    width: 150%;
    height: -webkit-fill-available;
}

</style>