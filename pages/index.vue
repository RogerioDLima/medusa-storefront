<script setup lang="ts">
const client = useMedusaClient();
const { products } = await client.products.list();
</script>

<template>
  <section class="h-screen relative mb-20">
    <div class="items-center container relative h-full grid grid-cols-2">
      <div class="py-20 flex-1 pr-10">
        <h1 class="text-6xl font-extrabold text-zinc-900 mb-4">
          Um design de qualidade que dará vida a sua marca 
        </h1>
        <p class="flex-1 text-zinc-600 text-base mb-10">
          Do conceito à realidade, soluções completas para uma aparência profissional e impactante ao seu negócio.
        </p>
        <nuxt-link to="#section-products">
          <Button size="lg">
            Explore nossos produtos
          </Button>
        </nuxt-link>
      </div>
    </div>
    <div class="absolute w-full h-full top-0 left-0 grid grid-cols-2 pointer-events-none">
      <div class="col-start-2 w-full h-full overflow-hidden">
        <img src="@/public/hero.png" class="w-full h-full object-center object-cover" />
      </div>
    </div>
  </section>
  <section id="#section-products" class="container my-40">
    <h2 class="font-extrabold mb-4 text-3xl">
      Sua Marca, Nossa Missão
    </h2>
    <div class="grid grid-cols-[repeat(auto-fill,_minmax(280px,_1fr))] gap-4">
      <ProductCard v-for="product in products" 
        :key="product.id" 
        :image="product.images ? product.images[0].url : ''" 
        :title="(product.title as string)" 
        :price="product.variants[0].prices[0].amount / 100"
        :handle="(product.handle as string)"
        :variant-id="(product.variants[0].id as string)"
      />
    </div>
  </section>
</template>
