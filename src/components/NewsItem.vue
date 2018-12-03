<template>
  <v-container xs12 sm3 offset-sm3>
    <v-layout>
      <v-flex md4 xs12>
        <v-img
         :src="image"
         height="200"
         width="200"
        ></v-img>
      </v-flex>
      <v-flex md8 xs12>
        <h2 class="pl-5">
          {{ title }}
        </h2>
        <p class="pl-5">
          {{ description }}
        </p>
        <br>
        <a
          :href='more'
          class="pl-5"
          target="_blank">
            Read More >
        </a>
      </v-flex>
    </v-layout>
  </v-container>

</template>

<script>
  export default {
    props: {
      image: {type: String},
      title: {type: String},
      description: {type: String},
      more: {type: String}
    }
  }
</script>
