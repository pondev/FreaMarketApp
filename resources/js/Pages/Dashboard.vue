<script setup lang="ts">
import { ref } from 'vue'
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import ProductCard from '@/Components/ProductCard.vue';


const products = ref([
  {
    id: 1,
    image: 'https://picsum.photos/400',
    title: '新品未使用 限定モデル スニーカー',
    price: 12800,
    seller: 'テストユーザー'
  },
  {
    id: 2,
    image: 'https://picsum.photos/401',
    title: '人気ブランド ショルダーバッグ',
    price: 8500,
    seller: 'メルカリ太郎'
  },        
  // More products...
  {
    id: 3,
    image: 'https://picsum.photos/403',
    title: '人気ブランド ショルダーバッグ',
    price: 9500,
    seller: 'サンプル太郎'
  },        
  // More products...
])
</script>

<template>
  <Head title="Dashboard" />

  <AuthenticatedLayout>
      <template #header>
          <h2
              class="text-xl font-semibold leading-tight text-gray-800"
          >
              Dashboard
          </h2>
      </template>

      <div class="py-20">
          <div class="mx-auto max-w-7xl sm:px-6 lg:px-8">
            <div class="overflow-hidden bg-white shadow-sm sm:rounded-lg">
              <main class="max-w-screen-md mx-auto px-4 pt-16 pb-20">
                <div class="grid grid-cols-2 gap-4 mt-4">
                  <ProductCard
                    v-for="product in products"
                    :key="product.id"
                    :image="product.image"
                    :title="product.title"
                    :price="product.price"
                    :seller="product.seller"
                    />
               </div>
            </main>
          </div>
        </div>
      </div>
  </AuthenticatedLayout>
</template>

<!-- <template>
  <AuthenticatedLayout>
    <div class="min-h-screen bg-gray-50">
      <TheHeader />
        <main class="max-w-screen-md mx-auto px-4 pt-16 pb-20">
          <div class="grid grid-cols-2 gap-4 mt-4">
            <ProductCard
              v-for="product in products"
              :key="product.id"
              :image="product.image"
              :title="product.title"
              :price="product.price"
              :seller="product.seller"
            />
          </div>
        </main>
      <TheBottomNav />
    </div>
  </AuthenticatedLayout>
</template> -->