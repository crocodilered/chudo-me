<template>
  <div class="home content">
    <div class="resp-image">
      <img alt="" src="@/assets/homepage-collage.jpg" style="width: 100%">
    </div>
    <title-2>Фотопроекты</title-2>
    <hr class="lo">
    <title-3>"Смайлики"</title-3>
    <title-4>Наши дети улыбаются</title-4>
    <div class="slider">
      <img src="@/assets/smiles/smile1.jpg" alt="">
      <img src="@/assets/smiles/smile2.jpg" alt="">
      <img src="@/assets/smiles/smile3.jpg" alt="">
      <img src="@/assets/smiles/smile4.jpg" alt="">
      <img src="@/assets/smiles/smile5.jpg" alt="">
      <img src="@/assets/smiles/smile6.jpg" alt="">
      <!--img src="@/assets/smiles/smile7.jpg" alt=""-->
    </div>
  </div>
</template>

<script>
  import Title2 from '@/components/common/title-2.vue'
  import Title3 from '@/components/common/title-3.vue'
  import Title4 from '@/components/common/title-4.vue'

  export default {
    name: 'Home',
    components: { Title2, Title3, Title4 }
  }
</script>

<style lang="scss">
  .slider {
    overflow: hidden;

    img {
      height: auto;
    }
  }

  @media (max-width: 420px) {
    /* Mobile */
    .slider {
      img {
        width: 33.33%;
      }
    }
  }

  @media (min-width: 421px) {
    /* Desktop */
    .slider {
      white-space: nowrap;

      img {
        width: 16.66%;
      }
    }
  }
</style>
