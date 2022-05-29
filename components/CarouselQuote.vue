<template>
    <div class="container flex center-items" style="padding: 100px 0px;">
      <div class="row">
        <div class="col-md-4"></div>
        <div class="col-md-4">
          <client-only>
            <carousel 
              :loop="true" 
              :autoplay="true" 
              :navigationEnabled="false" 
              :paginationEnabled="true"
              :perPage="1"
              :paginationColor="'#c7c5d1'"
              :autoplayTimeout="6000"
            >
              <slide class="text-center" v-for="(li,idx) in list" :key="idx">
                <h4 class="quote-text" style="letter-spacing: unset; line-height: 2.5rem;" v-html="li.description"></h4>
                <p class="quote-text" style="margin-top: 50px;" v-html="li.title"></p>
              </slide>
            </carousel>
          </client-only>
        </div>
        <div class="col-md-4"></div>
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

.VueCarousel-slide {
  text-align: center;
}