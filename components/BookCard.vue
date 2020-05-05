<template>
  <v-card class="mx-auto" max-width="400">
    <v-img src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg" height="200px" />
    <v-card-title>{{ booktitle }}</v-card-title>
    <v-card-subtitle>{{ bookauthor }}</v-card-subtitle>
    <v-card-text>{{ bookdescription }}</v-card-text>
    <v-card-actions>
      <v-spacer />
      <slot name="button" />
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  props: {
    bookTitle: { type: String, required: true },
    bookAuthor: { type: String, required: true },
    bookDescription: { type: String, required: true }
  }
}
</script>
