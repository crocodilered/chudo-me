<template>
  <div class="gallery preview-img-list">
    <div
      v-for="(o, i) in images"
      :key="`photo-${i}`"
      :style="{ backgroundImage: 'url(' + o.src + ')' }"
      @click="$photoswipe.open(i, images)"
      class="photo preview-img-item"
    />
  </div>
</template>

<script>
  import Vue from 'vue'
  import VuePhotoSwipe from 'vue-photoswipe'

  Vue.use(VuePhotoSwipe)

  export default {
    name: 'Gallery',
    props: ['path', 'photos'],
    computed: {
      images () {
        if (this.path && this.photos && this.photos.length > 0) {
          return this.photos.map(item => {
            return {
              src: this.path + '/' + item.src,
              w: item.w,
              h: item.h
            }
          })
        } else {
          return []
        }
      }
    }
  }
</script>

<style lang="scss" scooped>
  .gallery {
    display: flex;
    justify-content: center;
    align-items: baseline;
    flex-wrap: wrap;

    div.photo {
      display: inline-block;
      width: 300px;
      height: 300px;
      background-size: 500px auto;
      background-position: 50% 50%;
      border: 10px solid #f4f6f7;
      cursor: pointer;
    }

    div.photo:hover {
      border-color: #feeeef;
    }
  }
</style>
