<script>
  import { fade } from "svelte/transition";
  let menuState = [false, false, false, false];
</script>

<!-- Menu -->
<section class="relative w-full px-8 text-gray-700 bg-white body-font ">
  <div
    class="container flex flex-col flex-wrap items-center justify-between py-5 mx-auto md:flex-row max-w-7xl"
  >
    <a
      href="/"
      class="relative z-10 flex items-center w-auto text-2xl font-extrabold leading-none text-gray-500 select-none"
      >Vox Costruzioni</a
    >

    <nav
      class="top-0 left-0 z-0 flex items-center justify-center w-full h-full py-5 -ml-0 space-x-5 text-base md:-ml-5 md:py-0 md:absolute"
    >
      <a
        on:mouseenter={() => (menuState[0] = true)}
        on:mouseleave={() => (menuState[0] = false)}
        href="/"
        class="relative font-medium leading-6 text-gray-600 transition duration-150 ease-out hover:text-gray-900"
      >
        <span class="block">Home</span>

        <span
          class="absolute bottom-0 left-0 inline-block w-full h-0.5 -mb-1 overflow-hidden"
        >
          {#if menuState[0] == true}
            <span
              class="absolute inset-0 inline-block w-full h-1 h-full transform bg-gray-900"
            />
          {/if}
        </span>
      </a>
      <a
        on:mouseenter={() => (menuState[1] = true)}
        on:mouseleave={() => (menuState[1] = false)}
        href="/who"
        class="relative font-medium leading-6 text-gray-600 transition duration-150 ease-out hover:text-gray-900"
      >
        <span class="block">Chi siamo</span>

        <span
          class="absolute bottom-0 left-0 inline-block w-full h-0.5 -mb-1 overflow-hidden"
        >
          {#if menuState[1] == true}
            <span
              class="absolute inset-0 inline-block w-full h-1 h-full transform bg-gray-900"
            />
          {/if}
        </span>
      </a>
      <a
        on:mouseenter={() => (menuState[2] = true)}
        on:mouseleave={() => (menuState[2] = false)}
        href="/lavori"
        class="relative font-medium leading-6 text-gray-600 transition duration-150 ease-out hover:text-gray-900"
      >
        <span class="block">Lavori</span>

        <span
          class="absolute bottom-0 left-0 inline-block w-full h-0.5 -mb-1 overflow-hidden"
        >
          {#if menuState[2] == true}
            <span
              class="absolute inset-0 inline-block w-full h-1 h-full transform bg-gray-900"
            />
          {/if}
        </span>
      </a>
      <a
        on:mouseenter={() => (menuState[3] = true)}
        on:mouseleave={() => (menuState[3] = false)}
        href="/contatti"
        class="relative font-medium leading-6 text-gray-600 transition duration-150 ease-out hover:text-gray-900"
      >
        <span class="block">Contatti</span>

        <span
          class="absolute bottom-0 left-0 inline-block w-full h-0.5 -mb-1 overflow-hidden"
        >
          {#if menuState[3] == true}
            <span
              class="absolute inset-0 inline-block w-full h-1 h-full transform bg-gray-900"
            />
          {/if}
        </span>
      </a>
    </nav>

    <div
      class="relative z-10 inline-flex items-center space-x-3 md:ml-5 lg:justify-end"
    >
      <span class="inline-flex rounded-md shadow-sm">
        <a
          href="tel:3356169220"
          class="inline-flex items-center justify-center px-4 py-2 text-base font-medium leading-6 text-white whitespace-no-wrap bg-green-600 border border-white-700 rounded-md shadow-sm hover:bg-green-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500"
        >
          Chiama Ora
        </a>
      </span>
    </div>
  </div>
</section>
