<script>
  let { icon, title = '', description = '', children } = $props();


</script>

<div class="card">
  {#if icon}
    <div class="card-icon">
      {@html icon}
    </div>
  {/if}
  <h3 class="card-title">{title}</h3>
  {#if description}
    <p class="card-description">{description}</p>
  {/if}
  {@render children?.()}
</div>

<style>
  .card {
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

  .card::before {
    content: '';
    position: absolute;
    inset: 0;
    pointer-events: none;
    border-radius: inherit;
    background-color: var(--color-bg-secondary);
  }

  .card::after {
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

  @media (hover: hover) {
    .card:hover {
      transform: translateY(-4px);
    }
  }

  @media (max-width: 768px) {
    .card {
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
