<script lang="ts">
import { page } from "$app/state";
</script>

<svelte:head>
  <title>{page.status} · Error</title>
</svelte:head>

<div class="error-page">
  <div class="error-code">{page.status}</div>

  <h1>
		{#if page.status === 404}
			页面跑丢了喵
		{:else}
			出现了一点问题喵
		{/if}
	</h1>

  <p>{page.error?.message ?? '发生了未知错误。'}</p>

  <a href="/">返回主页</a>
</div>

<style>
.error-page {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 24px;
}

.error-code {
  font-size: 6rem;
  font-weight: 800;
  line-height: 1;
  opacity: 0.15;
}

h1 {
  margin: 16px 0 8px;
}

p {
  opacity: 0.65;
  margin: 0 0 24px;
}

a {
  color: #0070f3;
  text-decoration: none;
  font-weight: 500;
}
</style>
