<template>
  <div>
    <div class="max-w-2xl mx-auto text-center mb-10">
      <h2 class="text-2xl font-bold md:text-4xl md:leading-tight">
        Mitra Industri
      </h2>
    </div>
    <!-- Grid -->
    <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-6 mb-10">
      <!-- Card -->
      <div v-for="(mitra, i) in mitras" :key="i">
        <div class="group flex items-center justify-center">
          <div class="aspect-w-16 aspect-h-11">
            <img
              class="w-16 h-auto md:w-24 lg:w-28 mx-auto my-auto sm:mx-0 object-contain"
              :src="mitra.foto"
              alt="mitra"
            />
          </div>
        </div>
      </div>
      <!-- End Card -->
    </div>
    <!-- End Grid -->
  </div>
</template>

<script setup>
const supabase = useSupabaseClient();
const mitras = ref([]);

const getMitra = async () => {
  const { data } = await supabase.from("mitra").select(`*`);
  if (data) mitras.value = data;
};

onMounted(() => {
  getMitra();
});
</script>
