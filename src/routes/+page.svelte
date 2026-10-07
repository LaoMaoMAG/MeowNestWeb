<script lang="ts">
import Card from "#lib/components/Card.svelte";
</script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation</p>

<Card>
  <p>这里是内容</p>
</Card>

<Card title="测试"
  description="这是个测试的组件"
  tag="TEST">

  <div>
    <p>这里是内容</p>
  </div>

  {#snippet footer()}
    <span>Example 1</span>
    <span>Example 2</span>
    <span>Example 3</span>
    <span>Example 4</span>
    <span>Example 5</span>
  {/snippet}
  
</Card>
