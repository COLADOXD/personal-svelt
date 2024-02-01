<script lang="ts">
  import { Avatar } from "@skeletonlabs/skeleton";
  import Icon from "@iconify/svelte";
  import AvatarBg from "../assets/descarga.jpeg";

  export let showMenu: boolean;
  export let handleMenu: Function;
  let widthWindow =
    window.innerWidth ||
    document.documentElement.clientWidth ||
    document.body.clientWidth;

  const handleResizing = () => {
    widthWindow =
      window.innerWidth ||
      document.documentElement.clientWidth ||
      document.body.clientWidth;
    if (widthWindow > 900) {
      handleMenu(false);
    }
  };

  window.addEventListener("resize", handleResizing);
</script>

<nav class="h-16 flex justify-between items-center m-8">
  <div class="flex items-center">
    <Avatar src={AvatarBg} width="w-20" rounded="rounded-full" />
    <p class="ml-4 text-xl">Mateo Chacon</p>
  </div>
  {#if widthWindow < 900}
    <button on:click={() => ((showMenu = !showMenu), handleMenu(showMenu))}>
      <Icon icon="fa6-solid:align-justify"></Icon>
    </button>
  {/if}
  {#if widthWindow > 900}
    <div class="flex">
      <p class="my-4 text-xl font-semibold mr-8">All the projects</p>
      <p class="my-4 text-xl font-semibold">About</p>
    </div>
  {/if}
</nav>
