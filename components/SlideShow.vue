<template>
    <div class="container-fluid">
        <div class="slideshow-container">
            <div class="navigator-container">
                <div style="text-align:center">
                    <span v-for="(sl,idx) in slidesData" :key="idx" class="slideshow-dot" @click="slideIndex = idx"></span>
                    <!-- <span class="slideshow-dot" @click="currentSlide(2)"></span>
                    <span class="slideshow-dot" @click="currentSlide(3)"></span> -->
                </div>
            </div>
            <transition name="slide-img">
                <template v-for="(sl,idx) in slidesData">
                    <div class="slideshow-slides" :key="idx" v-if="slideIndex == idx">
                        <img :src="`${sl.featured.aws_file_url}/${sl.featured.path}/${sl.featured.filename.raw}`" style="width:100%; height: 100%;">
                        <div class="caption-text">Caption Text</div>
                    </div>
                </template>
            </transition>
        </div>
    </div>
</template>

<script>
    export default {
        props:["slidesData"],
        data() {
            return {
                slideIndex: 0,
            }
        },
        methods: {

        },
        mounted() {
        }
    }
</script>

<style scoped>
.navigator-container {
    position: absolute;
    bottom: 50px;
    width: 100%;
    z-index: 1000;
}

.slideshow-container {
    height: 100vh;
}

.slideshow-slides {
    position: absolute;
    width: 100%;
    height: 100%;
}

.caption-text {
  color: #f2f2f2;
  font-size: 15px;
  padding: 8px 12px;
  position: absolute;
  bottom: 8px;
  width: 100%;
  text-align: center;
}

.slideshow-dot {
  cursor: pointer;
  height: 15px;
  width: 15px;
  margin: 0 2px;
  background-color: #bbb;
  border-radius: 50%;
  display: inline-block;
  transition: background-color 0.6s ease;
}

.active, .slideshow-dot:hover {
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