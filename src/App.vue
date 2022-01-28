<template>
  <v-app>
    <v-container>
      <v-row>
        <v-col cols="12" lg="4" v-for="(image, key) in images" :key="key">
          <v-img :src="image" @click="open(image)">

          </v-img>
          <v-dialog v-model="dialog">
            <v-img :src="selectedImage"></v-img>
          </v-dialog>
        </v-col>
      </v-row>
    </v-container>

    
  </v-app>
</template>

<script>

    export default {
    data: () => ({
      selectedImage: null,
      dialog: false,
      images: [
        'https://scx2.b-cdn.net/gfx/news/2020/abstractart.jpg',
        'https://www.icanvas.com/blog/wp-content/uploads/2019/10/benefits-of-art-abstract.png',
        'https://d1zdxptf8tk3f9.cloudfront.net/ckeditor_assets/pictures/2509/content_geordanna-cordero-fields-762612-unsplash.jpg',
      ]
    }),

    methods: {
      open(image) {
        this.selectedImage = image;
        this.dialog = true;
      }
    }
  }
</script>
