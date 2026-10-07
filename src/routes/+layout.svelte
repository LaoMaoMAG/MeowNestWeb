<script lang="ts">
import favicon from "#lib/assets/favicon.svg";
import type { LayoutProps } from "./$types";
import { onMount } from "svelte";

let { children }: LayoutProps = $props();

let isMobile: boolean = $state(false);

onMount(() => {
  isMobile = window.innerWidth <= 768;
});
</script>


<svelte:head>
  <link rel="icon" href={favicon} />
  <title>猫猫の小窝</title>
</svelte:head>


{#if isMobile}
	<div class="mobile-warning">
  <h1>请使用 PC 访问</h1>
  <p>该网站暂时不支持移动端访问</p>
</div>
{:else}
	{@render children()}
{/if}


<style>
:global(body) {
  background-color: rgb(246, 237, 223);
}

.mobile-warning {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.mobile-warning h1 {
  margin-bottom: 8px;
}

.mobile-warning p {
  opacity: 0.7;
}
</style>
