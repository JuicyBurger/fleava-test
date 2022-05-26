<template>
    <div class="container">
        <div class="row">
            <div class="col-md-5">
                <h1 v-html="data.title_one"></h1>
                <h1 v-html="data.title_two"></h1>
                <p v-html="data.description"></p>
                <a :href="`/${data.link.url}`">{{ data.link.title }}</a>
            </div>
        </div>
        <div class="row">
            <div class="col-md-12">
                {{ data.featured }}
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