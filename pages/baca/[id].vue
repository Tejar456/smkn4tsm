<template>
  <div>
    <!-- Blog Article -->
    <div
      class="max-w-3xl px-4 pt-6 lg:pt-10 pb-12 mt-14 sm:px-6 lg:px-8 mx-auto"
    >
      <div v-for="(berita, i) in articel" :key="i" class="max-w-2xl">
        <!-- Content -->
        <div class="space-y-5 md:space-y-8">
          <div class="space-y-3">
            <h2 class="text-2xl font-bold md:text-3xl">
              {{ articel.judul }}
            </h2>
            <figure>
              <img
                class="w-full object-cover rounded-xl"
                :src="articel.cover"
                alt="Blog Image"
              />
            </figure>

            <p class="text-lg text-gray-800">
              {{ articel.konten }}
            </p>
          </div>
        </div>
      </div>
    </div>
    <!-- End Blog Article -->
  </div>
</template>

<script setup>
const supabase = useSupabaseClient();
const route = useRoute();
let articel = ref(0);

const getBeritaById = async () => {
  const { data, error } = await supabase
    .from("berita")
    .select(`*`)
    .eq("id", route.params.id);
  if (data) {
    articel.value = data[0];
  }
};

onMounted(() => {
  getBeritaById();
});
</script>
