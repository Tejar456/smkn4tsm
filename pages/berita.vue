<template>
  <div>
    <!-- Title -->
    <div class="max-w-2xl mx-auto text-center mt-14 lg:mt-20">
      <h2 class="text-2xl font-bold md:text-4xl md:leading-tight">Berita</h2>
      <p class="mt-1 text-gray-600">Berita SMKN 4 Tasikmalaya</p>
    </div>
    <!-- End Title -->
    <Articel />
    <Articel />
    <Articel />
  </div>
</template>

<script setup>
useHead({
  title: "Berita",
  meta: [{ name: "description", content: `Halaman Berita` }],
});
</script>
