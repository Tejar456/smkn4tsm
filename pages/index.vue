<template>
  <div>
    <Hero />
    <Sambutan />
    <!-- Title -->
    <div class="max-w-2xl mx-auto text-center mb-8 lg:mb-8">
      <h2 class="text-2xl font-bold md:text-4xl md:leading-tight">Berita</h2>
      <p class="mt-1 text-gray-600">Berita Terbaru SMKN 4 Tasikmalaya</p>
    </div>
    <!-- End Title -->
    <Articel />
    <!-- Card -->
    <div class="mt-8 pb-5 text-center">
      <a
        class="py-3 px-4 inline-flex items-center gap-x-1 text-sm font-medium rounded-full border border-gray-200 bg-white text-blue-600 shadow-sm hover:bg-gray-50 focus:outline-none focus:bg-gray-50 disabled:opacity-50 disabled:pointer-events-none"
        href="#"
      >
        Read more
        <svg
          class="shrink-0 size-4"
          xmlns="http://www.w3.org/2000/svg"
          width="24"
          height="24"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
        >
          <path d="m9 18 6-6-6-6" />
        </svg>
      </a>
    </div>
    <!-- End Card -->
    <Stat />
    <Jurusan />
    <Kerjasama />
    <Mitra />
  </div>
</template>

<script setup>
useHead({
  title: "Home",
  meta: [{ name: "description", content: `Halaman utama` }],
});
</script>
