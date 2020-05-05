<template>
  <div>
    <v-row>
      <v-col md="4">
        <h2 class="text-center mb-5">
          Recently Read Books
        </h2>
        <v-row v-for="(item,index) in recentBooks" :key="index">
          <BookCard
            class="mb-5"
            :book-title="item.title"
            :book-author="item.author"
            :book-description="item.description"
          >
            <template v-slot:button>
              <nuxt-link :to="`/books/${item.title}`">
                <v-btn>
                  View
                </v-btn>
              </nuxt-link>
              <v-btn @click.stop="edit(item,index)">
                Edit
              </v-btn>
              <v-btn @click.stop="remove(item.category, index)">
                Remove
              </v-btn>
            </template>
          </BookCard>
        </v-row>
      </v-col>
      <v-col md="4">
        <h2 class="text-center mb-5">
          Favourite Books
        </h2>
        <v-row v-for="(item,index) in favouriteBooks" :key="index">
          <BookCard
            class="mb-5"
            :book-title="item.title"
            :book-author="item.author"
            :book-description="item.description"
          >
            <template v-slot:button>
              <v-btn @click.stop="edit(item,index)">
                Edit
              </v-btn>
              <v-btn @click.stop="remove(item.category, index)">
                Remove
              </v-btn>
            </template>
          </BookCard>
        </v-row>
      </v-col>
      <v-col md="4">
        <h2 class="text-center mb-5">
          Best of the Best
        </h2>
        <v-row v-for="(item,index) in bestOfTheBest" :key="index">
          <BookCard
            class="mb-5"
            :book-title="item.title"
            :book-author="item.author"
            :book-description="item.description"
          >
            <template v-slot:button>
              <v-btn @click.stop="edit(item,index)">
                Edit
              </v-btn>
              <v-btn @click.stop="remove(item.category, index)">
                Remove
              </v-btn>
            </template>
          </BookCard>
        </v-row>
      </v-col>
    </v-row>
  </div>
</template>

<script>
import BookCard from '@/components/BookCard'

export default {
  components: {
    BookCard
  },

  data () {
    return {
      recentBooks: [],
      favouriteBooks: [],
      bestOfTheBest: []
    }
  }
}
</script>
