<script lang="ts">
import Card from "#lib/components/Card.svelte";
</script>

<h1>测试页面</h1>

<Card>
  <p>这里是内容</p>
</Card>

<br />

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
