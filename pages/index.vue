<template>
  <div>
    <ProductCard :product="product" />
    <!-- <ProductCardInTs :product="product" /> -->
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { Product } from '../types'

export default Vue.extend({
  name: 'IndexPage',
  data() {
    return {
      product: {
        id: '9712983189273912',
        name: 'Citi Credit Card',
        categories: ['cashback', 'rewards'],
      } as Product,
    }
  },
})
</script>
