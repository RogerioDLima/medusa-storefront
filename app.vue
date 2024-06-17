<script setup lang="ts">
const client = useMedusaClient();
const { products } = await client.products.list();
</script>

<template>
  <NuxtLayout class="text-zinc-950 bg-white">
    <NuxtPage />
  </NuxtLayout>
</template>