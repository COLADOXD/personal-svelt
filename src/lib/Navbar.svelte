<script lang="ts">
  import { Avatar } from "@skeletonlabs/skeleton";
  import Icon from "@iconify/svelte";
  import AvatarBg from "../assets/descarga.jpeg";

  export let showMenu: boolean;
  export let handleMenu: Function;
</script>

<nav class="h-16 flex justify-between items-center m-8">
  <div class="flex items-center">
    <Avatar src={AvatarBg} width="w-20" rounded="rounded-full" />
    <p class="ml-4 text-xl">Mateo Chacon</p>
  </div>
  <button on:click={() => ((showMenu = !showMenu), handleMenu(showMenu))}
    ><Icon icon="fa6-solid:align-justify"></Icon></button
  >
</nav>
{#if showMenu}
  <div class="w-full h-full"></div>
{/if}
