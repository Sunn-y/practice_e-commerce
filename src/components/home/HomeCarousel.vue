<template>
  <v-carousel
    cycle
    interval="3000"
    height="650"
    hide-delimiter-background
    show-arrows-on-hover
  >
    <v-carousel-item
      v-for="(item,i) in items"
      :key="i"
      :src="item.src"
    ></v-carousel-item>
  </v-carousel>
</template>

<script>
  export default {
    data () {
      return {
        items: [
          {
            src: 'https://cdn.pixabay.com/photo/2017/05/11/19/44/fruit-2305192_1280.jpg',
          },
          {
            src: 'https://cdn.pixabay.com/photo/2017/07/07/12/31/lime-2481346_1280.jpg',
          },
          {
            src: 'https://cdn.pixabay.com/photo/2017/01/20/15/06/orange-1995056_1280.jpg',
          },
          {
            src: 'https://cdn.pixabay.com/photo/2014/12/09/21/01/still-life-562357_1280.jpg',
          },
        ],
      }
    },
  }
</script>