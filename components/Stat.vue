<template>
  <div ref="statsSection">
    <div class="max-w-2xl mx-auto text-center mb-10">
      <h2 class="text-2xl font-bold md:text-4xl md:leading-tight">
        Data Statistik
      </h2>
    </div>
    <!-- Features -->
    <div class="px-4 py-10 sm:px-6 lg:px-8 lg:py-14 mx-auto bg-blue-600">
      <!-- Grid -->
      <div class="grid gap-6 grid-cols-2 sm:gap-12 lg:grid-cols-4 lg:gap-8">
        <!-- Stats -->
        <div>
          <h4 class="text-lg sm:text-xl font-semibold text-white text-center">
            Siswa
          </h4>
          <p
            class="mt-2 sm:mt-3 text-4xl sm:text-6xl font-bold text-white text-center"
          >
            {{ siswa }}
          </p>
        </div>
        <!-- End Stats -->
        <div>
          <h4 class="text-lg sm:text-xl font-semibold text-white text-center">
            Guru
          </h4>
          <p
            class="mt-2 sm:mt-3 text-4xl sm:text-6xl font-bold text-white text-center"
          >
            {{ guru }}
          </p>
        </div>
        <!-- End Stats -->
        <div>
          <h4 class="text-lg sm:text-xl font-semibold text-white text-center">
            Rombel
          </h4>
          <p
            class="mt-2 sm:mt-3 text-4xl sm:text-6xl font-bold text-white text-center"
          >
            {{ rombel }}
          </p>
        </div>
        <!-- End Stats -->
        <div>
          <h4 class="text-lg sm:text-xl font-semibold text-white text-center">
            Program Keahlian
          </h4>
          <p
            class="mt-2 sm:mt-3 text-4xl sm:text-6xl font-bold text-white text-center"
          >
            {{ kompetensiKeahlian }}
          </p>
        </div>
        <!-- End Stats -->
      </div>
      <!-- End Grid -->
    </div>
    <!-- End Features -->
  </div>
</template>

<script setup>
const siswa = ref(0);
const guru = ref(0);
const rombel = ref(0);
const kompetensiKeahlian = ref(0);
const statsSection = ref(null);

let hasAnimated = false;

const animateNumber = (refVar, target, duration = 2000) => {
  let start = 0;
  const increment = target / (duration / 16);
  const animate = () => {
    start += increment;
    if (start < target) {
      refVar.value = Math.floor(start);
      requestAnimationFrame(animate);
    } else {
      refVar.value = target;
    }
  };
  animate();
};

const startAnimation = () => {
  if (!hasAnimated) {
    animateNumber(siswa, 1500);
    animateNumber(guru, 85);
    animateNumber(rombel, 45);
    animateNumber(kompetensiKeahlian, 5);
    hasAnimated = true;
  }
};

onMounted(() => {
  const observer = new IntersectionObserver(
    (entries) => {
      if (entries[0].isIntersecting) {
        startAnimation();
      }
    },
    { threshold: 0.5 }
  );

  if (statsSection.value) {
    observer.observe(statsSection.value);
  }
});
</script>
