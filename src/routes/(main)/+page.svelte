<script>
    import Card from "#lib/components/Card.svelte";
</script>

<Card class="main-card">
    <section>
        <div class="welcome-container">
        
            <div class="welcome-title">
                <span>Welcome to</span>
                <strong>猫猫の小窝</strong>
            </div>

        </div>

        <div>
            <p>这里是内容</p>
        </div>
    </section>
</Card>

<div style="height: 10px;"></div>

<Card>
    <p>测试内容</p>
</Card>

<style>
    :global(.main-card) {
        padding: 18px;
    }

    section {
        height: 100%;
        display: grid;
        grid-template-columns: minmax(0, 1.18fr) minmax(350px, 0.82fr);
        gap: 18px;
    }

    section > div {
        min-width: 0;
    }

    .welcome-container {
        min-height: 520px;
        padding: 42px 38px 28px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        position: relative;
        z-index: 1;
    }

    .welcome-title {
        margin-top: 22px;
        line-height: .95;
        letter-spacing: -.06em;
    }

    .welcome-title span {
        display: block;
        font-size: clamp(30px, 4vw, 48px);
        color: var(--muted);
        letter-spacing: -.045em;
    }   

    .welcome-title strong {
        display: block;
        margin-top: 8px;
        font-size: clamp(62px, 8vw, 104px);
        font-weight: 950;
        text-shadow: 4px 4px 0 rgba(69, 57, 47, .08);
        animation: title-float 5s ease-in-out infinite;
    }
</style>