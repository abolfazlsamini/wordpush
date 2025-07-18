<template>
  <div
    class="bg-white rounded-xl shadow-md overflow-hidden hover:shadow-lg transition-shadow duration-300"
  >
    <!-- Product Image -->
    <div class="relative pb-[80%] overflow-hidden">
      <img
        :src="image"
        :alt="name"
        class="absolute h-full w-full object-cover hover:scale-105 transition-transform duration-500"
      />
      <!-- Sale Badge -->
      <div
        v-if="onSale"
        class="absolute top-2 right-2 bg-red-500 text-white text-xs font-bold px-2 py-1 rounded-full"
      >
        SALE
      </div>
    </div>

    <!-- Product Details -->
    <div class="p-4">
      <h3 class="text-lg font-semibold text-gray-800 mb-1 truncate">
        {{ name }}
      </h3>
      <p class="text-gray-600 text-sm mb-2 line-clamp-2">{{ description }}</p>

      <!-- Price -->
      <div class="flex items-center justify-between mt-3">
        <div>
          <span class="text-lg font-bold text-gray-900"
            >${{ price.toFixed(2) }}</span
          >
          <span
            v-if="originalPrice"
            class="ml-2 text-sm text-gray-500 line-through"
            >${{ originalPrice.toFixed(2) }}</span
          >
        </div>
        <button
          class="bg-indigo-600 hover:bg-indigo-700 text-white px-3 py-1 rounded-md text-sm transition-colors duration-200"
          @click="$emit('add-to-cart')"
        >
          Add to Cart
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      default: "",
    },
    image: {
      type: String,
      required: true,
    },
    price: {
      type: Number,
      required: true,
    },
    originalPrice: {
      type: Number,
      default: null,
    },
    onSale: {
      type: Boolean,
      default: false,
    },
  },
};
</script>
