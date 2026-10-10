<script lang="ts">
  import type { Snippet } from "svelte";

  interface Props {
    /** 主标题 */
    title?: string;
    /** 描述 */
    description?: string;
    /** 标签 */
    tag?: string;
    /** 主体内容 */
    children?: Snippet;
    /** 底部内容 */
    footer?: Snippet;
    /** CSS 选择器 */
    class?: string;
  }

  let {
    title,
    description,
    tag,
    children,
    footer,
    class: className = "",
  }: Props = $props();
</script>

<section class="stack-card {className}">
  {#if title || description || tag}
    <header class="card-header">
      {#if title}
        <h2 class="header-title">{title}</h2>
      {/if}
      {#if tag}
        <span class="header-tag">{tag}</span>
      {/if}
      {#if description}
        <p class="header-description">{description}</p>
      {:else}
        <div class="dashed-divider"></div>
      {/if}
    </header>
  {/if}

  <div class="card-content">
    {@render children?.()}
  </div>

  {#if footer}
    <div class="dashed-divider bottom-divider"></div>
    <footer class="card-footer">
      {@render footer()}
    </footer>
  {/if}
</section>

<style>
  .stack-card {
    --paper: #fffaf1;
    --ink: #45392f;
    --muted: #827264;
    --line: #bba890;
    --shadow: 5px 5px 0 #9e8b76;
    --radius: 18px;
    --shadow-hover: 7px 7px 0 rgba(69, 57, 47, 0.16);

    position: relative;
    box-sizing: border-box;
    min-width: 0;
    margin: 0;
    padding: 17px;
    overflow: hidden;
    color: var(--ink);
    background: var(--paper);
    border: 2px solid var(--line);
    border-radius: var(--radius);
    box-shadow: var(--shadow);
    font-family: ui-rounded, "Trebuchet MS", "PingFang SC", "Microsoft YaHei", sans-serif;
    line-height: 1.6;
    transition: transform 0.18s ease, box-shadow 0.18s ease,
      border-color 0.18s ease, background 0.18s ease;
  }

  .stack-card::after {
    content: "";
    position: absolute;
    top: -92px;
    right: -78px;
    width: 160px;
    height: 160px;
    border-radius: 50%;
    background: rgba(216, 163, 75, 0.08);
    pointer-events: none;
  }

  .card-header {
    position: relative;
    z-index: 1;
    display: grid;
    grid-template-columns: minmax(0, 1fr) auto;
    grid-template-areas: "title meta" "desc desc";
    align-items: end;
    gap: 0 12px;
    margin-bottom: 15px;
  }

  .header-title {
    grid-area: title;
    min-width: 0;
    margin: 0;
    color: var(--ink);
    font-size: 20px;
    font-weight: 700;
    line-height: 1.15;
    letter-spacing: -0.02em;
    overflow-wrap: anywhere;
  }

  .header-tag {
    grid-area: meta;
    align-self: center;
    justify-self: end;
    min-width: 0;
    color: var(--muted);
    font-size: 10px;
    font-weight: 900;
    line-height: 1.4;
    letter-spacing: 0.11em;
    text-align: right;
    white-space: nowrap;
  }

  .header-description {
    grid-area: desc;
    min-width: 0;
    margin: 5px 0 0;
    padding-bottom: 9px;
    color: var(--muted);
    font-size: 12px;
    font-weight: 400;
    line-height: 1.6;
    letter-spacing: 0;
    border-bottom: 1px dashed var(--line);
    overflow-wrap: anywhere;
  }

  .dashed-divider {
    grid-area: desc;
    width: 100%;
    height: 0;
    margin: 5px 0 9px;
    border-bottom: 1px dashed var(--line);
    opacity: 0.55;
  }

  .bottom-divider {
    position: relative;
    z-index: 1;
    margin: 16px 0 14px;
  }

  .card-content,
  .card-footer {
    position: relative;
    z-index: 1;
    min-width: 0;
  }

  .stack-card:hover {
    transform: translateY(-2px);
    box-shadow: var(--shadow-hover);
  }

</style>