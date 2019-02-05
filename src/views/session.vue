<template>
  <div class="about content">
    <title-2>Фотосессии</title-2>
    <p class="intro">Фотосессии могут проводиться в городских студиях или в моей личной. В парках, у вас дома, на празднике.</p>
    <p class="intro">Стоимость и перечень услуг &gt;</p>
    <hr class="toll">
    <tabs>
      <tab title="Малыши">
        <gallery
          path="/photos/baby/"
          :photos="[
            { src: '001.jpg', w: 1024, h: 683 },
            { src: '002.jpg', w: 1024, h: 683 },
            { src: '003.jpg', w: 1024, h: 683 },
            { src: '004.jpg', w: 1024, h: 683 },
            { src: '005.jpg', w: 683, h: 1024 },
            { src: '006.jpg', w: 683, h: 1024 },
            { src: '007.jpg', w: 1024, h: 683 },
            { src: '008.jpg', w: 683, h: 1024 },
            { src: '009.jpg', w: 1024, h: 683 }
            // { src: '009.jpg' }
          ]"
        ></gallery>
      </tab>
      <tab title="дети">
        1
      </tab>
      <tab title="семья">
        2
      </tab>
      <tab title="беременность">
        3
      </tab>
    </tabs>
  </div>
</template>

<script>
  import Title2 from '@/components/common/title-2.vue'
  import Gallery from '@/components/photos/gallery.vue'
  import Tabs from '@/components/common/tabs.vue'
  import Tab from '@/components/common/tab.vue'

  export default {
    name: 'Home',
    components: { Title2, Gallery, Tabs, Tab }
  }
</script>
