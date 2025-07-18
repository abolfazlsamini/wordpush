<template>
  <div class="min-h-screen bg-gray-50">
    <!-- Navbar -->
    <nav class="bg-white shadow-sm sticky top-0 z-10">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between h-16">
          <!-- Logo -->
          <div class="flex items-center">
            <span class="text-xl font-bold text-indigo-600">ShopVue</span>
          </div>

          <!-- Navigation Links -->
          <div class="hidden sm:ml-6 sm:flex sm:space-x-8">
            <a
              href="#"
              class="border-indigo-500 text-gray-900 inline-flex items-center px-1 pt-1 border-b-2 text-sm font-medium"
            >
              Home
            </a>
            <a
              href="#"
              class="border-transparent text-gray-500 hover:border-gray-300 hover:text-gray-700 inline-flex items-center px-1 pt-1 border-b-2 text-sm font-medium"
            >
              Products
            </a>
            <a
              href="#"
              class="border-transparent text-gray-500 hover:border-gray-300 hover:text-gray-700 inline-flex items-center px-1 pt-1 border-b-2 text-sm font-medium"
            >
              Categories
            </a>
            <a
              href="#"
              class="border-transparent text-gray-500 hover:border-gray-300 hover:text-gray-700 inline-flex items-center px-1 pt-1 border-b-2 text-sm font-medium"
            >
              About
            </a>
          </div>

          <!-- Cart/User -->
          <div class="flex items-center">
            <button
              class="p-1 rounded-full text-gray-400 hover:text-gray-500 focus:outline-none"
            >
              <span class="sr-only">Cart</span>
              <svg
                class="h-6 w-6"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.293 2.293c-.63.63-.184 1.707.707 1.707H17m0 0a2 2 0 100 4 2 2 0 000-4zm-8 2a2 2 0 11-4 0 2 2 0 014 0z"
                />
              </svg>
            </button>
            <span class="ml-1 text-sm font-medium text-gray-700">0</span>
          </div>
        </div>
      </div>
    </nav>

    <!-- Main Content -->
    <main class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8">
      <h1 class="text-3xl font-bold text-gray-900 mb-8">Featured Products</h1>

      <!-- Product Grid -->
      <div
        class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-6"
      >
        <ProductItem
          v-for="(product, index) in products"
          :key="index"
          v-bind="product"
          @add-to-cart="addToCart(product)"
        />
      </div>
    </main>
  </div>
</template>

<script>
import ProductItem from "./components/ProductItem.vue";

export default {
  components: {
    ProductItem,
  },
  data() {
    return {
      products: [
        {
          name: "Wireless Headphones",
          description:
            "Premium noise-cancelling wireless headphones with 30-hour battery life.Premium noise-cancelling wireless headphones with 30-hour battery life.",
          image:
            "https://images.unsplash.com/photo-1505740420928-5e560c06d30e?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60",
          price: 199.99,
          originalPrice: 249.99,
          onSale: true,
        },
        {
          name: "Smart Watch Pro",
          description:
            "Track your fitness and stay connected with this advanced smartwatch.",
          image:
            "https://images.unsplash.com/photo-1523275335684-37898b6baf30?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60",
          price: 299.99,
        },
        {
          name: "Bluetooth Speaker",
          description: "Portable waterproof speaker with crystal clear sound.",
          image:
            "https://images.unsplash.com/photo-1572569511254-d8f925fe2cbb?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60",
          price: 89.99,
          originalPrice: 119.99,
          onSale: true,
        },
        {
          name: "4K Camera",
          description:
            "Professional camera with 4K video recording and 20MP photos.",
          image:
            "https://images.unsplash.com/photo-1516035069371-29a1b244cc32?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60",
          price: 599.99,
        },
        {
          name: "Gaming Keyboard",
          description:
            "Mechanical RGB gaming keyboard with customizable macros.",
          image:
            "https://images.unsplash.com/photo-1540932239986-30128078f3c5?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60",
          price: 129.99,
        },
        {
          name: "Wireless Mouse",
          description: "Ergonomic wireless mouse with precision tracking.",
          image:
            "https://images.unsplash.com/photo-1527814050087-3793815479db?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60",
          price: 49.99,
        },
      ],
    };
  },
  methods: {
    addToCart(product) {
      console.log("Added to cart:", product.name);
      // Here you would typically update your cart state
    },
  },
};
</script>

<style>
/* Custom line-clamp for description */
.line-clamp-2 {
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
</style>
