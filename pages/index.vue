<template>
  <div class="container-fluid bg-secondary">
      <section id="section1">
        <div class="logo">
          <img :src="`https://jannataresort.com/_nuxt/img/1336c61.png`" alt="logo image" width="120" height="94">
        </div>
        <SlideShow
          :slidesData="slidesData"
        ></SlideShow>
      </section>
      <section id="section2">
        <SectionTwo 
          :data="sectionTwoData"
        />
      </section>
      <section id="section3" class="bg-dark" style="padding: 150px 0px;">
        <SectionThree
          :data="sectionThreeData"
        />
      </section>
      <section id="section4">
        <SectionFour
          :data="sectionFourData"
        />
      </section>
      <section id="section5" 
        :style="{ background: `linear-gradient(rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.4)), url(${sectionFiveData.featured.aws_file_url}/${sectionFiveData.featured.path}/${sectionFiveData.featured.filename.big})` }"
      >
        <SectionFive
          :data="sectionFiveData"
        />
      </section>
      <section id="section6" style="min-height: inherit;">
        <CarouselQuote
          :list="quoteList"
        ></CarouselQuote>
      </section>
  </div>
</template>

<script>
import staticData from '~/static/homepage.json'
// import SmoothScroll from '~/static/smooth-scroll.js'
export default {
  name: 'IndexPage',
  data() {
    return {
      quoteList: staticData.components[5].model.dataSlider,
      slidesData: staticData.components[0].model.dataSlider,
      sectionTwoData:staticData.components[1].model,
      sectionThreeData:staticData.components[2].model,
      sectionFourData:staticData.components[3].model,
      sectionFiveData:staticData.components[4].model,
    }
  },
  mounted () {
      // if(!window.smoothScroll){
      //   window.smoothScroll = SmoothScroll(document, 120, 12);
      // }
  }
}
</script>

<style scoped>
  #section5 {
    object-fit: contain;
    background-size: contain !important;
    background-position: center !important;
    background-repeat: no-repeat;
    background-size:100% 100% !important;
  }

  .logo {
    position: absolute;
    top: 0;
    width: 100%;
    text-align: center;
    z-index: 1000;
    padding: 100px;
  }
</style>