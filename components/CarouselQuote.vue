<template>
    <div class="container-fluid">
        <div class="carousel-container">
            <transition name="slide-img">
                <template v-for="(li,idx) in list">
                    <div class="carousel-slides" :key="idx" v-if="slideIndex == idx" style="text-align:center">
                        <p class="quote-text" v-html="li.description"></p>
                        <p class="quote-text" v-html="li.title"></p>
                    </div>
                </template>
            </transition>
        </div>
        <div style="text-align:center">
            <span v-for="(sl,idx) in list" :key="idx" class="dot" @click="slideIndex = idx"></span>
        </div>
    </div>
</template>

<script>
    export default {
        props:["list"],
        data() {
            return {
                slideIndex: 1,
            }
        },
        methods: {
        },
        mounted() {
        }
    }
</script>

<style scoped>
.carousel-slides {
    position: absolute;
    width: 100%;
    height: fit-content;
    margin: auto;
}
.carousel-container {
    width: 100%;
    position: relative;
    margin: auto;
    height: fit-content;
}

.quote-text {
  padding: 30px;
  text-align: center;
  margin-left: 20%;
  margin-right: 20%;
}

.dot {
  cursor: pointer;
  height: 15px;
  width: 15px;
  margin: 0 2px;
  background-color: #bbb;
  border-radius: 50%;
  display: inline-block;
  transition: background-color 0.6s ease;
}

.active, .dot:hover {
  background-color: #717171;
}

.slide-img-enter-from {
  left: -100%;
}
.slide-img-enter-to {
  left: -100%;
  transform: translate(100%, 0);
}
.slide-img-enter-active {
  transition: transform 1s ease-in-out;
}
.slide-img-leave-to {
  transform: translate(100%, 0);
}
.slide-img-leave-active {
  transition: transform 1s ease-in-out;
}
</style>