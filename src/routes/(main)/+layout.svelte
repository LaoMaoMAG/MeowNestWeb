<script lang="ts">
import favicon from "#lib/assets/favicon.svg";
import type { LayoutProps } from "./$types";
import Header from '#lib/components/Header.svelte';
import Footer from '#lib/components/Footer.svelte';

let { children }: LayoutProps = $props();
</script>


<svelte:head>
  <link rel="icon" href={favicon} />
</svelte:head>

<Header/>

<main class="main-content">
  {@render children()}
</main>

<Footer/>


<style>
  :global(body) {
    background-color: rgb(246, 237, 223);
  }

  .main-content {
    min-height: calc(100vh - 120px);
    padding: 2rem;
  }
</style>