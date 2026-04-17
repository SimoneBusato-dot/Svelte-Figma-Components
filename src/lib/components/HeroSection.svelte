<script lang="ts">
  import Button from './Button.svelte';

  let { title = '', description = '', ctaPrimary = { label: 'Get Started', href: '#' }, ctaSecondary = { label: 'About Us', href: '#' }, heroImage = undefined } = $props();

  // Image assets from Figma frame "image"
  const imgDecorationBackground = "https://www.figma.com/api/mcp/asset/b9acc4af-5064-44aa-876d-4178d2cd8411";
  const imgEllipse1 = "https://www.figma.com/api/mcp/asset/659157c2-2718-4c53-8f20-e37842fbc38d";
  const imgEllipse3 = "https://www.figma.com/api/mcp/asset/729073fd-e354-4a2d-befc-e3ae195eaa34";
  const imgDecorationBackground1 = "https://www.figma.com/api/mcp/asset/11559bc4-a8cd-41cd-bc5e-01e76a538a01";
  const imgEllipse2 = "https://www.figma.com/api/mcp/asset/f199fc6a-2fac-4863-8cfd-9ead519a6cca";
  const imgEllipse4 = "https://www.figma.com/api/mcp/asset/67572564-aa3a-4610-87fb-ceeee1887078";
  const imgDecorationBackground2 = "https://www.figma.com/api/mcp/asset/6fe2d0e2-2858-4728-9132-40f29bcf0189";
  const imgEllipse5 = "https://www.figma.com/api/mcp/asset/d80278ae-9f7b-4c08-87fb-9aec2280154a";
  const imgEllipse6 = "https://www.figma.com/api/mcp/asset/75f302c6-6d99-410c-9aa4-94d2cb1dd714";
  const imgVector = "https://www.figma.com/api/mcp/asset/7d045476-2960-415d-9770-28dc83672344";
  const imgVector1 = "https://www.figma.com/api/mcp/asset/29f64254-849b-47bd-ab18-9b0f4e156753";
  const imgVector2 = "https://www.figma.com/api/mcp/asset/2357d917-a374-438a-98c3-8688ca40322b";
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
              d="M5 19L19 5M19 5H7M19 5V17"
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
    {:else}
      <div class="hero-image-figma">
        <div class="decoration-bg" style="left: 45px; top: 71px; width: 533px; height: 516px;">
          <img src={imgDecorationBackground} alt="" class="bg-img" />
        </div>
        <div class="decoration-bg" style="left: 465px; top: 0; width: 201px; height: 194px;">
          <img src={imgDecorationBackground1} alt="" class="bg-img" />
        </div>
        <div class="decoration-bg" style="left: 26px; top: 496px; width: 79px; height: 76px;">
          <img src={imgDecorationBackground2} alt="" class="bg-img" />
        </div>
        
        <!-- Decorated circles -->
        <div class="decorated-circle" style="left: 0; top: 119px;">
          <img src={imgVector1} alt="Chart" class="circle-icon" />
        </div>
        <div class="decorated-circle" style="left: 246px; top: 263px;">
          <img src={imgVector} alt="Line chart" class="circle-icon" />
        </div>
        <div class="decorated-circle" style="left: 474px; top: 464px;">
          <img src={imgVector2} alt="Radio" class="circle-icon" />
        </div>
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
    font-weight: var(--font-weight-regular);
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

  .hero-image-figma {
    flex: 0 0 666px;
    height: 596px;
    position: relative;
    overflow: hidden;
  }

  .decoration-bg {
    position: absolute;
  }

  .bg-img {
    width: 100%;
    height: 100%;
    display: block;
  }

  .decorated-circle {
    position: absolute;
    width: 132px;
    height: 132px;
    background-color: var(--color-bg-primary);
    border-radius: var(--radius-full);
    border: 1px solid rgba(255, 255, 255, 0.5);
    display: flex;
    align-items: center;
    justify-content: center;
    box-shadow: -2px -2px 4px 0px rgba(255, 255, 255, 0.8), 4px 4px 8px 0px rgba(0, 0, 0, 0.15);
    z-index: 10;
  }

  .circle-icon {
    width: 66px;
    height: 66px;
    display: block;
    flex-shrink: 0;
  }

  @media (max-width: 1024px) {
    .hero-image-figma {
      flex: 0 0 auto;
      width: 100%;
      max-width: 500px;
      height: 400px;
    }
  }

  @media (max-width: 640px) {
    .hero-image-figma {
      max-width: 100%;
      height: 300px;
    }
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
