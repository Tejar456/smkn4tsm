<template>
  <!-- Card Blog -->
  <div class="max-w-[85rem] px-4 py-10 sm:px-6 lg:px-8 lg:py-14 mx-auto">
    <!-- Grid -->
    <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-6">
      <!-- Card -->
      <div
        data-aos="fade-up"
        v-for="(articel, i) in articels"
        :key="i"
        :data-aos-delay="i * 200"
      >
        <nuxt-link
          :to="`baca/${articel.id}`"
          class="group flex flex-col h-full border border-gray-200 hover:border-transparent hover:shadow-lg focus:outline-none focus:border-transparent focus:shadow-lg transition duration-300 rounded-xl p-5"
        >
          <div class="aspect-w-16 aspect-h-11">
            <img
              class="w-full h-60 object-cover rounded-xl"
              :src="articel.cover"
              alt="cover"
            />
          </div>
          <div class="my-6">
            <h3 class="text-xl font-semibold text-gray-800">
              {{ articel.judul }}
            </h3>
          </div>
          <div class="mt-auto flex items-center gap-x-3">
            <div>
              <h5 class="text-sm text-gray-800">{{ articel.tanggal }}</h5>
            </div>
          </div>
        </nuxt-link>
      </div>
      <!-- End Card -->
    </div>
    <!-- End Grid -->
  </div>
  <!-- End Card Blog -->
</template>

<script setup>
const supabase = useSupabaseClient();
let articels = ref([]);

const getArticel = async () => {
  const { data } = await supabase.from("berita").select(`*`);
  if (data) articels.value = data;
};

onMounted(() => {
  getArticel();
});
</script>
