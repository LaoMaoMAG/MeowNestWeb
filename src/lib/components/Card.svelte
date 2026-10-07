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
            <div class="header-left">
                <h2>{title}</h2>
                {#if description}
                    <p>{description}</p>
                {/if}
            </div>
            {#if tag}
                <span class="header-tag">{tag}</span>
            {/if}
        </header>

        <div class="dashed-divider"></div>
    {/if}

    <div class="card-content">
        {@render children?.()}
    </div>

    {#if footer}
        <div class="dashed-divider bottom-divider"></div>
        <footer>
            {@render footer()}
        </footer>
    {/if}
</section>

<style>
/* 卡片 */
.stack-card {
  --paper: #fffaf1;
  --ink: #45392f;
  --muted: #827264;
  --line: #bba890;
  --shadow: 5px 5px 0 #9e8b76;
  --radius: 18px;
  position: relative;
  overflow: hidden;
  box-sizing: border-box;
  min-width: 0;
  margin: 0;
  padding: 22px 26px;
  background: var(--paper);
  border: 2px solid var(--line);
  border-radius: var(--radius);
  box-shadow: var(--shadow);
  color: var(--ink);
  font-family: ui-rounded, "Trebuchet MS", "PingFang SC", "Microsoft YaHei",
    sans-serif;
  line-height: 1.6;
  transition:
    transform 0.18s ease,
    box-shadow 0.18s ease,
    border-color 0.18s ease,
    background 0.18s ease;
}

/* 卡片内圆 */
.stack-card::after {
  content: "";
  position: absolute;
  width: 160px;
  height: 160px;
  right: -78px;
  top: -92px;
  border-radius: 50%;
  background: rgba(216, 163, 75, 0.08);
  pointer-events: none;
}

/* 头部 */
.card-header {
  position: relative;
  z-index: 1;
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  gap: 16px;
}

/* 头部标题 */
.header-left h2 {
  margin: 0;
  font-size: 1.3rem;
  font-weight: 700;
  color: var(--ink);
  letter-spacing: 0.02em;
}

/* 头部描述 */
.header-left p {
  margin: 8px 0 0;
  font-size: 0.82rem;
  color: var(--muted);
  line-height: 1.55;
}

/* 头部标签 */
.header-tag {
  flex-shrink: 0;
  padding-top: 6px;
  font-size: 0.72rem;
  font-weight: 700;
  color: var(--muted);
  letter-spacing: 0.18em;
  text-transform: uppercase;
}

/* 虚线 */
.dashed-divider {
  position: relative;
  z-index: 1;
  width: 100%;
  height: 0;
  border-bottom: 1px dashed var(--line);
  opacity: 0.55;
  margin: 18px 0 22px;
}
</style>
