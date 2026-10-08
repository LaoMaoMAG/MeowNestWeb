<script lang="ts">
  import type { LayoutProps } from "../$types";
  import Header from "#lib/components/Header.svelte";
  import Footer from "#lib/components/Footer.svelte";

  let { children }: LayoutProps = $props();
</script>

<div class="main-container">
  <Header />

  <main class="content-container">
    {@render children()}
  </main>

  <Footer />
</div>

<style>
  .main-container {
    min-height: 100vh;
    width: min(1180px, calc(100% - 28px));
    margin: 0 auto;
  }
  
  .content-container {
    min-height: calc(100vh - 120px);
    margin: 20px 0px;
  }
</style>
