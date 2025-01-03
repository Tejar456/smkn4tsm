<template>
  <div class="flex justify-center">
    <!-- ========== HEADER ========== -->
    <header
      data-aos="fade-down"
      class="bg-white fixed top-3 border rounded-2xl border-gray-300 flex flex-wrap md:justify-start md:flex-nowrap z-50 w-[95%] drop-shadow-md"
    >
      <nav
        class="relative max-w-[85rem] w-full md:flex md:items-center md:justify-between md:gap-3 mx-auto px-4 sm:px-6 lg:px-8 py-2"
      >
        <!-- Logo w/ Collapse Button -->
        <div class="flex items-center justify-between">
          <img src="/assets/img/Logo.png" class="w-10 md:mr-2" alt="" />
          <h2
            class="flex-none font-semibold text-xl text-black focus:outline-none focus:opacity-80"
            aria-label="Brand"
          >
            SMKN 4 Tasikmalaya
          </h2>
          <!-- Collapse Button -->
          <div class="md:hidden">
            <button
              type="button"
              class="hs-collapse-toggle relative size-9 flex justify-center items-center text-sm font-semibold rounded-lg border border-gray-200 text-gray-800 hover:bg-gray-100 focus:outline-none focus:bg-gray-100 disabled:opacity-50 disabled:pointer-events-none"
              id="hs-header-classic-collapse"
              aria-expanded="false"
              aria-controls="hs-header-classic"
              aria-label="Toggle navigation"
              data-hs-collapse="#hs-header-classic"
            >
              <svg
                class="hs-collapse-open:hidden size-4"
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
                <line x1="3" x2="21" y1="6" y2="6" />
                <line x1="3" x2="21" y1="12" y2="12" />
                <line x1="3" x2="21" y1="18" y2="18" />
              </svg>
              <svg
                class="hs-collapse-open:block shrink-0 hidden size-4"
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
                <path d="M18 6 6 18" />
                <path d="m6 6 12 12" />
              </svg>
              <span class="sr-only">Toggle navigation</span>
            </button>
          </div>
          <!-- End Collapse Button -->
        </div>
        <!-- End Logo w/ Collapse Button -->

        <!-- Collapse -->
        <div
          id="hs-header-classic"
          class="hs-collapse hidden overflow-hidden transition-all duration-300 basis-full grow md:block"
          aria-labelledby="hs-header-classic-collapse"
        >
          <div
            class="overflow-hidden overflow-y-auto max-h-[75vh] [&::-webkit-scrollbar]:w-2 [&::-webkit-scrollbar-thumb]:rounded-full [&::-webkit-scrollbar-track]:bg-gray-100 [&::-webkit-scrollbar-thumb]:bg-gray-300"
          >
            <div
              class="py-2 md:py-0 flex flex-col md:flex-row md:items-center md:justify-end gap-0.5 md:gap-1"
            >
              <NuxtLink
                class="p-2 flex items-center text-sm text-gray-800 focus:outline-none hover:text-blue-600 focus:text-blue-600"
                to="/"
                aria-current="page"
              >
                Home
              </NuxtLink>

              <!-- Dropdown -->
              <div
                class="hs-dropdown [--strategy:static] md:[--strategy:fixed] [--adaptive:none] [--is-collapse:true] md:[--is-collapse:false]"
              >
                <button
                  id="hs-header-classic-dropdown"
                  type="button"
                  class="hs-dropdown-toggle w-full p-2 flex items-center text-sm text-gray-800 hover:text-blue-600 focus:outline-none focus:text-blue-600e"
                  aria-haspopup="menu"
                  aria-expanded="false"
                  aria-label="Dropdown"
                >
                  Profil
                  <svg
                    class="hs-dropdown-open:-rotate-180 md:hs-dropdown-open:rotate-0 duration-300 shrink-0 size-4 ms-auto md:ms-1"
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
                    <path d="m6 9 6 6 6-6" />
                  </svg>
                </button>

                <div
                  class="hs-dropdown-menu transition-[opacity,margin] duration-[0.1ms] md:duration-[150ms] hs-dropdown-open:opacity-100 opacity-0 relative w-full md:w-52 hidden z-10 top-full ps-7 md:ps-0 md:bg-white md:rounded-lg md:shadow-md before:absolute before:-top-4 before:start-0 before:w-full before:h-5 md:after:hidden after:absolute after:top-1 after:start-[18px] after:w-0.5 after:h-[calc(100%-0.25rem)] after:bg-gray-100"
                  role="menu"
                  aria-orientation="vertical"
                  aria-labelledby="hs-header-classic-dropdown"
                >
                  <div class="py-1 md:px-1 space-y-0.5">
                    <NuxtLink
                      class="py-1.5 px-2 flex items-center text-sm text-gray-800 hover:text-blue-600 focus:outline-none focus:text-blue-600"
                      to="/profil"
                    >
                      Profil
                    </NuxtLink>

                    <NuxtLink
                      class="py-1.5 px-2 flex items-center text-sm text-gray-800 hover:text-blue-600 focus:outline-none focus:text-blue-600"
                      to="sejarah"
                    >
                      Sejarah
                    </NuxtLink>

                    <NuxtLink
                      class="py-1.5 px-2 flex items-center text-sm text-gray-800 hover:text-blue-600 focus:outline-none focus:text-blue-600"
                      to="visimisi"
                    >
                      VIsi & Misi
                    </NuxtLink>
                  </div>
                </div>
              </div>
              <!-- End Dropdown -->

              <NuxtLink
                class="p-2 flex items-center text-sm text-gray-800 hover:text-blue-600 focus:outline-none focus:text-blue-600"
                to="/berita"
              >
                Berita
              </NuxtLink>

              <NuxtLink
                class="p-2 flex items-center text-sm text-gray-800 hover:text-blue-600 focus:outline-none focus:text-blue-600"
                to="/ekskul"
              >
                Ekstrakurikuler
              </NuxtLink>

              <NuxtLink
                class="p-2 flex items-center text-sm text-gray-800 hover:text-blue-600 focus:outline-none focus:text-blue-600"
                to="/gallery"
              >
                Gallery
              </NuxtLink>

              <NuxtLink
                class="p-2 flex items-center text-sm text-gray-800 hover:text-blue-600 focus:outline-none focus:text-blue-600"
                to="/kontak"
              >
                Kontak
              </NuxtLink>
            </div>
          </div>
        </div>
        <!-- End Collapse -->
      </nav>
    </header>
    <!-- ========== END HEADER ========== -->
  </div>
</template>
