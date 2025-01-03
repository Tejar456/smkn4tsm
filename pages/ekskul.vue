<template>
  <div>
    <div class="max-w-[85rem] px-4 pt-14 sm:px-6 lg:px-8 lg:pt-20 mx-auto">
      <!-- Title -->
      <div class="max-w-2xl mx-auto text-center mb-10 lg:mb-14">
        <h2 class="text-2xl font-bold md:text-4xl md:leading-tight">
          Ekstrakurikuler
        </h2>
        <p class="mt-1 text-gray-600">Ekstrakurikuler SMKN 4 Tasikmalaya</p>
      </div>
      <!-- End Title -->
      <!-- Grid -->
      <div class="flex justify-center">
        <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-6 pb-20">
          <!-- Card -->
          <div
            v-for="(ekskul, i) in ekskuls"
            :key="i"
            data-aos="fade-up"
            :data-aos-delay="i * 200"
          >
            <a
              class="group flex flex-col items-center h-[21rem] border border-gray-200 hover:border-transparent hover:shadow-lg focus:outline-none focus:border-transparent focus:shadow-lg transition duration-300 rounded-xl p-5"
              href="#"
            >
              <div class="aspect-w-16 aspect-h-11">
                <img
                  class="w-full h-60 object-cover rounded-xl"
                  :src="ekskul.foto"
                  alt="cover"
                />
              </div>
              <div class="my-6">
                <h3 class="text-xl font-semibold text-center text-gray-800">
                  {{ ekskul.nama }}
                </h3>
              </div>
            </a>
          </div>
          <!-- End Card -->
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const supabase = useSupabaseClient();
const ekskuls = ref([]);

const getEkskul = async () => {
  const { data, error } = await supabase.from("ekskul").select(`*`);
  if (data) ekskuls.value = data;
};

onMounted(() => {
  getEkskul();
});
</script>
