<template>
  <div class="d-flex flex-column">

    <div class="d-flex flex-row">
      <div>
        <v-btn x-small
               color="error"
               @click="decrease">
          -
        </v-btn>
      </div>
      <h3 class="flex-grow-1 text-lg text-center">
        {{ quantity }}
      </h3>
      <div>
        <v-btn x-small
               color="primary"
               @click="increase">+</v-btn>
      </div>
    </div>

    <div class="text-center"
         style="height: 60px; font-size: 14px">{{ product.name }}
      <br />
      <span v-if="product.brand"
            style="font-size: 12px; font-weight: bold">({{ product.brand }})</span>
    </div>

  </div>
</template>

<script>
export default {
  props: ['product'],

  data () {
    return {
      quantity: 0
    }
  },

  mounted () {
    this.quantity = this.product.quantity
  },

  methods: {
    decrease () {
      if (this.quantity > 0) {
        this.product.quantity--
        this.quantity--
      }
    },

    increase () {
      this.product.quantity++
      this.quantity++
    }
  },
}
</script>
