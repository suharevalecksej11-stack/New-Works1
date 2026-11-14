<script setup>
defineProps({
  name: String,
  price: String,
  image: String,
  dotColor: String,
  dotBorder: Boolean
})

const emit = defineEmits(['addToCart'])
</script>

<template>
  <article class="product-tile">
    <button class="add-btn" @click="emit('addToCart')">+</button>
    <div class="tile-image-wrapper">
      <img :src="image" alt="" class="tile-img" />
    </div>
    <div class="tile-info">
      <h3 class="tile-name">{{ name }}</h3>
      <div
        class="color-dot"
        :style="{
          backgroundColor: dotColor,
          border: dotBorder ? '1px solid #ddd' : 'none'
        }"
      ></div>
      <span class="tile-price">{{ price }}</span>
    </div>
  </article>
</template>
