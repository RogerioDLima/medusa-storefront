<script setup lang="ts">
const client = useMedusaClient();
const { product_categories } = await client.productCategories.list();
const { collections } = await client.collections.list();
</script>

<template>
  <footer class="bg-zinc-50">
    <div class="container py-20 mt-20 grid grid-cols-[repeat(auto-fill,_minmax(280px,_1fr))] gap-4 gap-y-10">
        <div>
          <img src="@/public/logo.png" height="80" width="80" class="h-[20px] w-auto pr-4" />
        </div>
      <div class="text-sm space-y-4">
          <div class="font-medium">
             @Letras e Logos
          </div>
      </div>
      <div class="text-sm space-y-4">
        <div class="font-medium">

        </div>
      </div>
    </div>
  </footer>
</template>
