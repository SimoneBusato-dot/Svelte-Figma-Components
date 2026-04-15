<script lang="ts">
  let { variant = 'primary', href, type = 'button', children } = $props();

  type ButtonVariant = 'primary' | 'secondary';

  const getButtonType = (t: string) => {
    return (t as 'button' | 'submit' | 'reset') || 'button';
  };
</script>

{#if href}
  <a {href} class={`btn btn-${variant}`}>
    {@render children?.()}
   
  </a>
{:else}
  <button type={getButtonType(type)} class={`btn btn-${variant}`}>
    {@render children?.()}
  </button>
{/if}

<style>
  .btn {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 57px;
    border-radius: var(--radius-full);
    font-family: var(--font-inter);
    font-weight: var(--font-weight-semibold);
    font-size: 24px;
    cursor: pointer;
    border: none;
    transition: all 0.2s ease;
    text-decoration: none;
  }

  .btn-primary {
    background-color: var(--color-btn-primary-bg);
    color: var(--color-btn-primary-text);
    padding: var(--radius-s) var(--spacing-24);
    box-shadow: -3px -4px 4px 0px var(--color-neomorph-light),
      3px 2px 4px 0px var(--color-neomorph-shadow);
      position: relative;
     
  }


  

  .btn-secondary {
    background-color: var(--color-bg-primary);
    color: var(--color-btn-secondary-text);
    padding: var(--radius-s) var(--spacing-32);
    box-shadow: inset -3px -4px 4px 0px var(--color-neomorph-light),
      inset 3px 2px 4px 0px var(--color-neomorph-shadow);
      transition: all 0.2s ease;
  }

  .btn-secondary:hover {
    background-color: var(--color-btn-hover-bg);
    box-shadow: inset -3px -4px 4px 0px var(--color-btn-hover-bg),
      inset 3px 2px 4px 0px var(--color-btn-hover-bg);
  }



  /* Dark mode */
  :global(.dark) .btn-primary {
    box-shadow: -3px -4px 4px 0px var(--color-neomorph-light),
      3px 2px 4px 0px var(--color-neomorph-shadow);
  }

  :global(.dark) .btn-secondary {
    box-shadow: inset -3px -4px 4px 0px var(--color-neomorph-light),
      inset 3px 2px 4px 0px var(--color-neomorph-shadow);
    
  }
</style>
