<script>
  import { onMount } from "svelte";

  let menuState = [false, false, false, false];
  // Show mobile icon and display menu
  let showMobileMenu = false;
  let open = false;
  // List of navigation items
  const navItems = [
    { label: "Home", href: "/" },
    { label: "Chi siamo", href: "/who" },
    { label: "Lavori", href: "/lavori" },
    { label: "Contatti", href: "/contatti" },
  ];

  // Mobile menu click event handler
  const handleMobileIconClick = () => (showMobileMenu = !showMobileMenu);

  // Media match query handler
  const mediaQueryHandler = (e) => {
    // Reset mobile state
    if (!e.matches) {
      showMobileMenu = false;
    }
  };

  // Attach media query listener on mount hook
  onMount(() => {
    const mediaListener = window.matchMedia("(max-width: 767px)");

    mediaListener.addListener(mediaQueryHandler);
  });
</script>

<svelte:head>
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta
      name="keywords"
      content="impresa edile,costruzioni,Ristrutturazioni,vox costruzioni"
    />
    <title>Vox Costruzioni</title>
  </head>
</svelte:head>

<nav
  class={`relative w-full px-8 text-gray-700 body-font h-[100px] ${
    showMobileMenu ? "bg-white" : "bg-white"
  }`}
>
  <div
    class="container flex items-center justify-between py-5 mx-auto md:flex-row max-w-7xl"
  >
    <!-- Logo -->
    <a
      href="/"
      class="relative z-10 flex items-center w-auto text-2xl font-extrabold leading-none text-gray-500 select-none"
      >Vox Costruzioni <span class="text-green-600">&nbsp; S.A.S.</span></a
    >
    <ul
      class={`cursor-pointer md:flex md:justify-around hidden md:p-0 navbar-list${
        showMobileMenu ? " mobile" : ""
      }`}
    >
      {#each navItems as item, i}
        <li
          class=" mt-20 lg:mt-0 relative px-10"
          on:mouseenter={() => (menuState[i] = true)}
          on:mouseleave={() => (menuState[i] = false)}
        >
          <a href={item.href} class="justify-center"
            >{item.label}

            <span
              class="absolute bottom-0 left-0 inline-block w-full h-0.5 overflow-hidden"
            >
              {#if menuState[i] == true}
                <span
                  class="absolute inset-0 inline-block w-full h-0.5 transform bg-gray-900"
                />
              {/if}
            </span></a
          >
        </li>
      {/each}
    </ul>
    <!-- End Button -->
    <div
      class="relative z-10  items-center space-x-3 md:ml-5 lg:justify-end hidden lg:flex "
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
    <button
      class="text-gray-500 hover:text-gray-700 cursor-pointer mr-0 border-none focus:outline-none md:hidden"
      class:open
      on:click={() => ((open = !open), handleMobileIconClick())}
    >
      <svg width="30" height="22">
        <line id="top" x1="0" y1="2" x2="32" y2="2" />
        <line id="middle" x1="0" y1="12" x2="24" y2="12" />
        <line id="bottom" x1="0" y1="22" x2="32" y2="22" />
      </svg>
    </button>
  </div>
</nav>

<style>
  @media only screen and (min-width: 767px) {
    .navbar-list {
      display: flex;
      padding: 0;
    }

    .navbar-list a {
      display: inline-flex;
    }
  }

  .navbar-list {
    margin: 0;
  }

  .navbar-list.mobile {
    width: 100%;
    justify-content: space-between;
    background-color: rgba(0, 0, 0, 0.9);
    position: fixed;
    display: block;
    height: 100%;
    bottom: 0;
    left: 0;
    z-index: 10;
  }

  .navbar-list a {
    color: #6b7280;
    text-decoration: none;
    display: flex;
    width: auto;
    height: 45px;
    align-items: center;
    font-size: 13px;
  }

  svg {
    min-height: 24px;
    transition: transform 0.3s ease-in-out;
  }

  svg line {
    stroke: currentColor;
    stroke-width: 3;
    transition: transform 0.3s ease-in-out;
  }

  button {
    z-index: 20;
  }

  .open svg {
    transform: scale(0.7);
  }

  .open #top {
    transform: translate(6px, 0px) rotate(45deg);
  }

  .open #middle {
    opacity: 0;
  }

  .open #bottom {
    transform: translate(-12px, 9px) rotate(-45deg);
  }
</style>
