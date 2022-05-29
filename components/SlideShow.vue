<template>
    <div class="container-fluid">
      <client-only>
        <carousel 
          :loop="true" 
          :autoplay="true" 
          :navigationEnabled="true" 
          :paginationEnabled="true"
          :perPage="1"
          :paginationColor="'#c7c5d1'"
          :autoplayTimeout="600000"
        >
          <slide class="text-center" v-for="(sl,idx) in slidesData" :key="idx">
            <div class="caption-container">
              <div class="caption-text">
                {{ sl }}
              </div>
            </div>
            <img :src="`${sl.featured.aws_file_url}/${sl.featured.path}/${sl.featured.filename.raw}`" class="carousel-img">
          </slide>
        </carousel>
      </client-only>
    </div>
</template>

<script>
    export default {
        props:["slidesData"],
    }
</script>

<style scoped>

  .VueCarousel {
    max-height: 100vh;
  }
  
  * >>> .VueCarousel-pagination {
    position: absolute !important;
    bottom: 0;
    text-align: left !important;
    padding: 100px 200px;
  }
  * >>> .VueCarousel-navigation {
    position: absolute;
    bottom: 80px;
    right: 200px;
    z-index: 1000;
    padding: 30px;
  }
  * >>> .VueCarousel-navigation-button {
    color: white !important;
  }

  .carousel-img {
    object-fit: cover;
    width: 100%;
  }

  .caption-container {
    height: 100vh;
    width: 100%;
    position: absolute;
    top: 0;
    left: 0;
  }

  .caption-text {
    margin: 0;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    color: white;
    z-index: 1000;
  }
</style>