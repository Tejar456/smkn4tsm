<template>
  <div>
    <!-- Comment Form -->
    <div
      class="max-w-[85rem] px-4 py-10 sm:px-6 lg:px-8 lg:py-14 mx-auto mt-14"
    >
      <div class="mx-auto max-w-2xl drop-shadow-md"></div>
      <div class="text-center">
        <h2 class="text-xl text-gray-800 font-bold sm:text-3xl">Kontak</h2>
      </div>
      <!-- Card -->
      <div
        class="mt-5 p-4 relative z-10 bg-white border rounded-xl sm:mt-10 md:p-10"
      >
        <form @submit.prevent="submitMasage()">
          <div class="mb-4 sm:mb-8">
            <label
              for="hs-feedback-post-comment-name-1"
              class="block mb-2 text-sm font-medium"
              >Nama</label
            >
            <input
              v-model="form.nama"
              type="text"
              id="hs-feedback-post-comment-email-1"
              class="py-3 px-4 block w-full border rounded-lg text-sm focus:border-blue-500 focus:ring-blue-500 disabled:opacity-50 disabled:pointer-events-none"
            />
          </div>

          <div class="mb-4 sm:mb-8">
            <label
              for="hs-feedback-post-comment-email-1"
              class="block mb-2 text-sm font-medium"
              >Email</label
            >
            <input
              v-model="form.email"
              type="email"
              id="hs-feedback-post-comment-email-1"
              class="py-3 px-4 block w-full border rounded-lg text-sm focus:border-blue-500 focus:ring-blue-500 disabled:opacity-50 disabled:pointer-events-none"
            />
          </div>

          <div>
            <label
              for="hs-feedback-post-comment-textarea-1"
              class="block mb-2 text-sm font-medium"
              >Pesan</label
            >
            <div class="mt-10">
              <textarea
                v-model="form.pesan"
                id="hs-feedback-post-comment-textarea-1"
                name="hs-feedback-post-comment-textarea-1"
                rows="3"
                class="py-3 px-4 block w-full border rounded-lg text-sm focus:border-blue-500 focus:ring-blue-500 disabled:opacity-50 disabled:pointer-events-none"
              ></textarea>
            </div>
          </div>

          <div class="mt-6 grid">
            <button
              type="submit"
              class="w-full py-3 px-4 inline-flex justify-center items-center gap-x-2 text-sm font-medium rounded-lg border border-transparent bg-blue-600 text-white hover:bg-blue-700 focus:outline-none focus:bg-blue-700 disabled:opacity-50 disabled:pointer-events-none"
            >
              Submit
            </button>
          </div>
        </form>
      </div>
      <!-- End Card -->
    </div>
  </div>
  <!-- End Comment Form -->
</template>

<script setup>
const supabase = useSupabaseClient();
const form = ref({
  nama: "",
  email: "",
  pesan: "",
});
const submitMasage = async () => {
  const { error } = await supabase.from("kontak").insert([form.value]);
  if (!error) {
    alert("Berhasil");
  }
};
</script>
