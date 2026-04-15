<script>
  let { title = '', subtitle = '', cards = [], id = '' } = $props();


</script>

<section {id} class="approach-section">
  <div class="section-container">
    <div class="section-header">
      <h2 class="section-title">{title}</h2>
      <p class="section-subtitle">{subtitle}</p>
    </div>

    <div class="cards-grid">
      {#each cards as card (card.id)}
        <div class="card-wrapper">
          <div class="default-card">
            {#if card.icon}
              <div class="card-icon">{@html card.icon}</div>
            {/if}
            <h3 class="card-title">{card.title}</h3>
            {#if card.description}
              <p class="card-description">{card.description}</p>
            {/if}
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>

<style>
  .approach-section {
    width: 100%;
    background-color: var(--color-bg-primary);
    overflow: hidden;
  }

  .section-container {
    display: flex;
    flex-direction: column;
    gap: var(--spacing-12);
    align-items: center;
    padding: var(--spacing-80);
    min-height: 1022px;
    justify-content: center;
  }

  .section-header {
    display: flex;
    flex-direction: column;
    gap: var(--spacing-40);
    align-items: center;
    justify-content: center;
    text-align: center;
    width: 100%;
    margin-bottom: var(--spacing-40);
  }

  .section-title {
    font-size: var(--text-4xl);
    font-weight: var(--font-weight-bold);
    font-family: var(--font-inter);
    color: var(--color-text-primary);
    margin: 0;
    line-height: 1.2;
  }

  .section-subtitle {
    font-size: var(--text-2xl);
    font-weight: var(--font-weight-regular);
    font-family: var(--font-inter);
    color: var(--color-text-secondary);
    margin: 0;
    line-height: 1.4;
    white-space: nowrap;
  }

  .cards-grid {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: var(--spacing-40);
    width: 100%;
    padding: var(--spacing-32);
  }

  .card-wrapper {
    width: 100%;
  }

  .default-card {
    display: flex;
    flex-direction: column;
    gap: var(--spacing-40);
    align-items: center;
    justify-content: center;
    padding: var(--spacing-40);
    border-radius: var(--radius-md);
    background-color: var(--color-bg-secondary);
    position: relative;
    overflow: hidden;
    transition: all 0.3s ease;
  }

  .default-card::before {
    content: '';
    position: absolute;
    inset: 0;
    pointer-events: none;
    border-radius: inherit;
    background-color: var(--color-bg-secondary);
  }

  .default-card::after {
    content: '';
    position: absolute;
    inset: 0;
    pointer-events: none;
    border-radius: inherit;
    box-shadow: inset -6px -5px 8px 0px var(--color-neomorph-light),
      inset 3px 4px 4px 0px var(--color-neomorph-shadow);
  }

  .card-icon {
    position: relative;
    z-index: 1;
    width: 182px;
    height: 182px;
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--color-link-hover);
  }

  :global(.card-icon svg) {
    width: 100%;
    height: 100%;
  }

  .card-title {
    position: relative;
    z-index: 1;
    font-size: var(--text-xl);
    font-weight: var(--font-weight-semibold);
    font-family: var(--font-inter);
    color: var(--color-text-primary);
    margin: 0;
    text-align: center;
  }

  .card-description {
    position: relative;
    z-index: 1;
    font-size: var(--text-base);
    font-weight: var(--font-weight-regular);
    font-family: var(--font-inter);
    color: var(--color-text-secondary);
    margin: 0;
    text-align: center;
    line-height: 1.5;
  }

  @media (max-width: 1024px) {
    .section-container {
      padding: var(--spacing-40);
      min-height: auto;
    }

    .cards-grid {
      grid-template-columns: repeat(1, minmax(0, 1fr));
      gap: var(--spacing-24);
      padding: var(--spacing-24);
    }

    .section-title {
      font-size: var(--text-3xl);
    }

    .section-subtitle {
      font-size: var(--text-xl);
    }
  }

  @media (max-width: 640px) {
    .section-container {
      padding: var(--spacing-24);
      gap: var(--spacing-24);
    }

    .section-title {
      font-size: var(--text-2xl);
    }

    .section-subtitle {
      font-size: var(--text-base);
      white-space: normal;
    }

    .cards-grid {
      padding: var(--spacing-16);
    }

    .default-card {
      padding: var(--spacing-24);
    }

    .card-icon {
      width: 120px;
      height: 120px;
    }

    .card-title {
      font-size: var(--text-lg);
    }

    .card-description {
      font-size: var(--text-sm);
    }
  }
</style>
