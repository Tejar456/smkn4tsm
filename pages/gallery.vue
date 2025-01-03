<template>
  <div>
    <div class="max-w-[85rem] px-4 pt-14 sm:px-6 lg:px-8 lg:pt-20 mx-auto">
      <!-- Title -->
      <div class="max-w-2xl mx-auto text-center mb-10 lg:mb-14">
        <h2 class="text-2xl font-bold md:text-4xl md:leading-tight">Gallery</h2>
        <p class="mt-1 text-gray-600">Gallery SMKN 4 Tasikmalaya</p>
      </div>
      <!-- End Title -->
      <!-- Grid -->
      <div class="flex justify-center">
        <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-6 pb-20">
          <div
            v-for="(foto, i) in fotos"
            :key="i"
            data-aos="fade-up"
            :data-aos-delay="i * 200"
            class="w-96 overflow-hidden h-60 rounded-2xl relative group"
          >
            <img :src="foto.foto" alt="foto" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
useHead({
  title: "Gallery",
  meta: [{ name: "description", content: `Halaman Gallery` }],
});
const supabase = useSupabaseClient();
const fotos = ref([]);

const getFoto = async () => {
  const { data } = await supabase.from("gallery").select(`*`);
  if (data) fotos.value = data;
};

onMounted(() => {
  getFoto();
});
</script>
