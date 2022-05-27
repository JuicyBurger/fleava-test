<template>
    <div class="container flex center-items">
        <div class="row">
            <div class="col-md-7"></div>
            <div class="col-md-4" style="color: white;">
                <h1 v-html="data.title"></h1>
                <div class="title-line"></div>
                <p v-html="data.description"></p>
                <p :href="`/${data.link.url}`" style="margin: 30px 0px;">{{ data.link.title }}</p>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props:["data"]
    }
</script>

<style scoped>
    .title-line {
        height: 1px;
        background-color: #679334;
        margin: 35px 0 40px;
        position: relative;
    }
</style>