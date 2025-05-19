<template>
  <div class="flex flex-col items-start space-y-3 sm:space-y-4 md:space-y-6 py-4">
    <div class="self-start mb-2 md:mb-0 transform scale-90 sm:scale-100">
      <button
        class="border-3 border-black bg-primary shadow-[8px_8px_0_#000000] inline-flex items-center justify-center whitespace-nowrap h-10 sm:h-12 md:h-14 w-40 sm:w-48 md:w-52 px-3 py-1 font-bold text-xl sm:text-2xl md:text-3xl -rotate-15 text-white"
      >
        Hello <span class="text-2xl sm:text-3xl md:text-4xl ml-1 sm:ml-2">👋</span>
      </button>
    </div>

    <div class="relative mt-2 sm:mt-4 w-full">
      <img
        src="../assets/layerstyle.png"
        alt="Style de calque pour Valentin Moreau"
        class="h-auto w-full max-w-[800px]"
      />
    </div>

    <div class="pl-1 sm:pl-2 md:pl-4 mt-1 sm:mt-2">
      <p class="text-base sm:text-lg md:text-xl lg:text-3xl text-white">
        Concepteur Développeur d'Application
      </p>
      <p class="text-base sm:text-lg md:text-xl lg:text-3xl text-primary font-semibold">
        Vue.js & React / Laravel
      </p>
    </div>

    <div class="pl-1 sm:pl-2 md:pl-4 pt-3 md:pt-4">
      <a
        href="#"
        class="border-3 border-black bg-primary shadow-[8px_8px_0_#000000] inline-flex items-center justify-center whitespace-nowrap h-10 sm:h-12 px-4 sm:px-6 text-base sm:text-2xl font-normal text-white hover:shadow-none hover:translate-y-[8px] hover:translate-x-[8px] transition-all"
      >
        Mon histoire
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="2.5"
          stroke="currentColor"
          class="w-4 h-4 sm:w-5 sm:h-5 ml-2"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M13.5 6H5.25A2.25 2.25 0 003 8.25v10.5A2.25 2.25 0 005.25 21h10.5A2.25 2.25 0 0018 18.75V10.5m-10.5 6L21 3m0 0h-5.25M21 3v5.25"
          />
        </svg>
      </a>
    </div>
  </div>
</template>
