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

<script lang="ts">
import { defineComponent, PropType } from 'vue'
import { Product } from '../types'

export default defineComponent({
  name: 'ProductCardInTs',
  props: {
    product: {
      type: Object as PropType<Product>,
      required: true,
    },
  },
  data() {
    return {
      country: 'sg' as string,
    }
  },
  computed: {
    categories(): Array<string> {
      return this.product.categories.map((category) => {
        return this.formatCategory(category)
      })
    },
  },
  methods: {
    formatCategory(category: string): string {
      if (this.country === 'sg') {
        return category.toUpperCase()
      }

      return category
    },
  },
})
</script>

<styles lang="scss" scoped></styles>
