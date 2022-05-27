<template>
  <div class="container-fluid bg-secondary">
      <section id="section1">
        <p class="logo p-5">LOGO</p>
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
      <section id="section6">
        <CarouselQuote
          :list="quoteList"
        ></CarouselQuote>
      </section>
  </div>
</template>

<script>
import staticData from '~/static/homepage.json'
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
  mounted() {
    console.log(staticData)
  }
}
</script>

<style scoped>
  #section5 {
    object-fit: contain;
    background-size: contain !important;
    background-position: center !important;
    background-repeat: no-repeat;
  }
</style>