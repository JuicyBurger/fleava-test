<template>
  <div class="container-fluid">
      <section id="section1">
        <p class="logo p-5">LOGO</p>
        <SlideShow
          :slidesData="slidesData"
        ></SlideShow>
      </section>
      <section id="section2">
        
      </section>
      <section id="section3">
        Section 3
      </section>
      <section id="section4">
        Section 4
      </section>
      <section id="section5">
        Section 5
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
    }
  },
  mounted() {
    console.log(staticData)
  }
}
</script>
