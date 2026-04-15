<script>
  let { title = '', description = '', image, imagePosition = 'right', minHeight = '800px' } = $props();

</script>

<section class="section" style="min-height: {minHeight}">
  <div class="section-container" data-position={imagePosition}>
    {#if imagePosition === 'left' && image}
      <div class="section-image">
        <img src={image} alt={title} />
      </div>
    {/if}

    <div class="section-content">
      <div class="content-wrapper">
        <h2 class="section-title">{title}</h2>
        <p class="section-description">{description}</p>
      </div>
    </div>

    {#if imagePosition === 'right' && image}
      <div class="section-image">
        <img src={image} alt={title} />
      </div>
    {/if}
  </div>
</section>

<style>
  .section {
    width: 100%;
    background-color: var(--color-bg-primary);
    overflow: hidden;
  }

  .section-container {
    display: flex;
    align-items: center;
    gap: var(--spacing-40);
    padding: var(--spacing-80);
    justify-content: space-between;
    height: 100%;
  }

  .section-container[data-position='left'] {
    flex-direction: row;
  }

  .section-container[data-position='right'] {
    flex-direction: row-reverse;
  }

  .section-image {
    flex: 0 0 auto;
    width: 887px;
    height: 692px;
    overflow: hidden;
    border-radius: var(--radius-md);
    position: relative;
  }

  .section-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .section-content {
    flex: 0 0 525px;
    display: flex;
    flex-direction: column;
    gap: var(--spacing-40);
    align-items: flex-start;
  }

  .content-wrapper {
    display: flex;
    flex-direction: column;
    gap: 2px;
    align-items: flex-start;
    justify-content: flex-end;
    background-color: var(--color-bg-primary);
    border-radius: var(--radius-xl);
    width: 100%;
  }

  .section-title {
    font-size: var(--text-4xl);
    font-weight: var(--font-weight-bold);
    font-family: var(--font-inter);
    color: var(--color-text-primary);
    margin: 0;
    width: 100%;
    line-height: 1.2;
  }

  .section-description {
    font-size: var(--text-xl);
    font-weight: var(--font-weight-medium);
    font-family: var(--font-inter);
    color: var(--color-text-secondary);
    margin: 0;
    width: 100%;
    line-height: 1.5;
  }

  @media (max-width: 1024px) {
    .section-container {
      flex-direction: column;
      padding: var(--spacing-40);
      gap: var(--spacing-24);
    }

    .section-image {
      width: 100%;
      height: 400px;
    }

    .section-content {
      flex: 0 0 auto;
      width: 100%;
    }

    .section-title {
      font-size: var(--text-3xl);
    }

    .section-description {
      font-size: var(--text-lg);
    }
  }

  @media (max-width: 640px) {
    .section-container {
      padding: var(--spacing-24);
    }

    .section-image {
      height: 250px;
    }

    .section-title {
      font-size: var(--text-2xl);
    }
  }
</style>
