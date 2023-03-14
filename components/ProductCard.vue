<template>
  <div>
    <h1>{{ product.name }}</h1>

    <ul>
      <li v-for="category in categories" :key="category">
        {{ category }}
      </li>
    </ul>
  </div>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'ProductCard',
  props: {
    product: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      country: 'sg',
    }
  },
  computed: {
    categories() {
      return this.product.categories.map((category) => {
        return this.formatCategory(category)
      })
    },
  },
  methods: {
    formatCategory(category) {
      if (this.country === 'sg') {
        return category.toUpperCase()
      }

      return category
    },
  },
})
</script>

<styles lang="scss" scoped></styles>
