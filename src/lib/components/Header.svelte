<script lang="ts">
  import favicon from "#lib/assets/favicon.svg";
</script>

<header class="header">
  <nav>
    <div>
      <img src={favicon} alt="Logo" width="30" height="30" />
      <div class="logo-copy">
        <b class="logo-text">猫猫の小窝</b>
        <b class="logo-tag">MEOWNEST.NET · HOME</b>
      </div>
    </div>

    <div>
      <a href="/">猫窝</a>
      <a href="/">传送门</a>
      <a href="/">茶话会</a>
      <a href="/">友人帐</a>
      <a href="/about">关于喵?</a>
    </div>
    
    
    <div>
      <a href="/test">测试</a>
    </div>
  </nav>
</header>

<style>
  .header {
    padding: 1rem;
    background: #fffaf1;
    color: white;
    min-width: 0;
    margin: 0;
    border: 2px solid #bba890; /* 边框 */
    border-radius: 18px; /* 圆角 */
  }

  nav {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 1rem;
  }

  nav a {
    margin-right: 1rem;
    color: black;
    text-decoration: none;
  }

  nav a:hover {
    text-decoration: underline;
  }

  .logo-text {
    color: #45392f;
  }

  .logo-copy {
    flex-direction: column;
    align-items: flex-start;
    gap: 0.1rem;
  }

  .logo-tag {
    color: #827264;
    font-size: 0.6rem;
  }

  div {
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    gap: 1rem;
  }

</style>