<template>
  <div>
    <div
      data-aos="fade-up"
      class="flex justify-center bg-white border border-gray-200 shadow-sm rounded-xl p-4 md:p-5"
    >
      <iframe
        class="w-3/4 h-[500px] mt-20"
        src="https://www.youtube.com/embed/5l2u9rHS36k?si=MK3n4iCRvUY6kVv1&autoplay=1"
        title="YouTube video player"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
        referrerpolicy="strict-origin-when-cross-origin"
        allowfullscreen
      ></iframe>
    </div>
  </div>
</template>

<script setup>
useHead({
  title: "Profil",
  meta: [{ name: "description", content: `Halaman Profil` }],
});
</script>
