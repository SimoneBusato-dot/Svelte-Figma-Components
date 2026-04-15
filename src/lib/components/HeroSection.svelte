<script lang="ts">
  import Button from './Button.svelte';

  let { title = '', description = '', ctaPrimary = { label: 'Get Started', href: '#' }, ctaSecondary = { label: 'About Us', href: '#' }, heroImage = undefined } = $props();

  // Decoration circle data
  const decorations = [
    { id: 1, icon: 'icon-bars', top: '119px', left: '0px' },
    { id: 2, icon: 'icon-line', top: '263px', left: '246px' },
    { id: 3, icon: 'icon-radio', top: '464px', left: '474px' },
  ];
</script>

<section class="hero-section">
  <div class="hero-container">
    <!-- Text Content -->
    <div class="hero-content">
      <div class="title-container">
        <h1 class="hero-title">{title}</h1>
        <p class="hero-description">{description}</p>
      </div>

      <div class="buttons-group">
        <Button variant="primary" href={ctaPrimary.href}>
          {ctaPrimary.label}
           <svg
            class="trailing-icon"
            width="24"
            height="24"
            viewBox="0 0 24 24"
            fill="none"
            style="margin-left: 8px;"
          >
            <path
              d="M5 12H19M19 12L12 5M19 12L12 19"
              stroke="currentColor"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
          </svg>
        </Button>
        <Button variant="secondary" href={ctaSecondary.href}>
          {ctaSecondary.label}
        </Button>
      </div>
    </div>

    <!-- Decorative Image Area -->
    {#if heroImage}
      <div class="hero-image">
        <img src={heroImage} alt="Hero decoration" />
      </div>
    {/if}
  </div>
</section>

<style>
  .hero-section {
    width: 100%;
    background-color: var(--color-bg-primary);
    overflow: hidden;
  }

  .hero-container {
    display: flex;
    gap: var(--spacing-40);
    align-items: flex-end;
    justify-content: space-between;
    padding: var(--spacing-40);
    padding-left: var(--spacing-80);
    padding-right: var(--spacing-80);
    min-height: 749px;
    max-width: 100%;
  }

  .hero-content {
    display: flex;
    flex-direction: column;
    gap: var(--spacing-40);
    align-items: flex-start;
    flex: 0 0 auto;
  }

  .title-container {
    display: flex;
    flex-direction: column;
    gap: 2px;
    align-items: flex-start;
    justify-content: flex-end;
    background-color: var(--color-bg-primary);
    border-radius: var(--radius-xl);
  }

  .hero-title {
    font-size: var(--text-4xl);
    font-weight: var(--font-weight-bold);
    font-family: var(--font-inter);
    background: linear-gradient(
      -60.39554116875058deg,
      var(--color-gradient-primary-start) 18.326%,
      var(--color-gradient-primary-end) 69.64%
    );
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin: 0;
    white-space: nowrap;
    text-align: center;
  }

  .hero-description {
    font-size: var(--text-xl);
    font-weight: var(--font-weight-medium);
    font-family: var(--font-inter);
    color: var(--color-text-secondary);
    margin: 0;
    max-width: 719px;
    line-height: 1.5;
  }

  .buttons-group {
    display: flex;
    gap: var(--spacing-16);
    align-items: center;
  }

  .trailing-icon {
    display: inline;
    color: inherit;
  }

  .hero-image {
    flex: 0 0 666px;
    height: 596px;
    overflow: hidden;
    position: relative;
  }

  .hero-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  @media (max-width: 1024px) {
    .hero-container {
      flex-direction: column;
      min-height: auto;
      padding: var(--spacing-40);
    }

    .hero-title {
      white-space: normal;
    }

    .hero-image {
      flex: 0 0 auto;
      width: 100%;
      max-width: 500px;
      height: 400px;
    }
  }

  @media (max-width: 640px) {
    .hero-container {
      gap: var(--spacing-24);
      padding: var(--spacing-24);
    }

    .hero-title {
      font-size: var(--text-3xl);
    }

    .hero-description {
      font-size: var(--text-lg);
    }

    .buttons-group {
      width: 100%;
      flex-direction: column;
    }

    .hero-image {
      max-width: 100%;
      height: 300px;
    }
  }
</style>
