<script>
  import { fade } from "svelte/transition";

  export let carouselPhotos;

  let index = 0;

  setInterval(() => {
    if (index < carouselPhotos.length - 1) index++;
    else index = 0;
  }, 3000);
  // <Slideshow carouselPhotos={[image1,image2]} client:load />
</script>

<img
  transition:fade
  alt="gallery"
  class="absolute inset-0 w-full h-full object-cover object-center"
  src={carouselPhotos[index]}
/>
