<template>
    <div class="container">
        <div class="row">
            <div class="col-md-7"></div>
            <div class="col-md-5">
                <h1 v-html="data.title"></h1>
                <p v-html="data.description"></p>
            </div>
        </div>
        <div class="row">
            <div class="col-md-4" v-for="(item,idx) in data.dataSlider" :key="idx">
                {{ item.link.title }}
                <p>{{ item.featured }}</p>
                <p>{{ item.featured_hover }}</p>
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

</style>