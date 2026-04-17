<script lang="ts">
  interface NavLink {
    label: string;
    href: string;
    isActive?: boolean;
  }

  let { links = [
    { label: 'Home', href: '#' },
    { label: 'About Us', href: '#' },
    { label: 'Contacts', href: '#' }
  ] } = $props();
</script>

<nav class="navbar">
  <div class="navbar-container">
    <div class="navbar-content">
      <div class="logo">ED</div>
      
      <div class="navbar-links">
        {#each links as link (link.label)}
          <a href={link.href} class="nav-link" class:active={link.isActive}>
            {link.label}
          </a>
        {/each}
      </div>
    </div>
  </div>
</nav>

<style>
  .navbar {
    width: 100%;
    background-color: var(--color-bg-primary);
    padding: var(--spacing-8) var(--spacing-80);
    position: sticky;
    top: 5%;
    z-index: 50;
  }

  .navbar-container {
    display: flex;
    flex-direction: column;
    gap: var(--spacing-8);
    align-items: center;
  }

  .navbar-content {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 1352px;
    background-color: var(--color-bg-primary);
    padding: 10px var(--spacing-32);
    border-radius: var(--radius-full);
    box-shadow: -6px -5px 4px 0px rgba(255, 255, 255, 0.95), 3px 4px 4px 0px rgba(139, 139, 139, 0.5);
    overflow: hidden;
  }

  .logo {
    font-family: var(--font-inter);
    font-weight: var(--font-weight-bold);
    font-size: 24px;
    background: linear-gradient(
      -65.30348184230508deg,
      var(--color-gradient-primary-start) 6.86%,
      var(--color-gradient-primary-end) 93.14%
    );
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    white-space: nowrap;
  }

  .navbar-links {
    display: flex;
    gap: var(--spacing-24);
    align-items: center;
  }

  .nav-link {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: var(--spacing-12) var(--spacing-32);
    border-radius: var(--radius-full);
    background-color: var(--color-bg-primary);
    color: var(--color-content-secondary);
    font-family: var(--font-inter);
    font-weight: var(--font-weight-semibold);
    font-size: var(--spacing-24);
    text-decoration: none;
    cursor: pointer;
    position: relative;
    border: none;
    transition: all 0.15s ease;
    box-shadow: inset -4px -3px 4px 0px var(--color-bg-primary), inset 3px 3px 5px 0px var(--color-bg-primary) ;
    white-space: nowrap;
  }

  .nav-link:hover {
    box-shadow: inset -2px -2px 3px 0px var(--color-neomorph-light), inset 2px 2px 4px 0px var(--color-neomorph-shadow);
    color: var(--color-brand-color-800);
  }

  .nav-link:active {
    box-shadow: inset -1px -1px 2px 0px var(--color-neomorph-light), inset 1px 1px 2px 0px var(--color-neomorph-shadow);
  }

  .nav-link.active {
    background-color: var(--color-bg-primary);
    box-shadow: inset -4px -3px 4px 0px rgba(255, 255, 255, 0.98), inset 3px 3px 5px 0px rgba(139, 139, 139, 0.35);
    color: var(--color-brand-color-800);
  }

  @media (max-width: 1024px) {
    .navbar {
      padding: var(--spacing-24) var(--spacing-40);
    }

    .navbar-content {
      width: 100%;
      max-width: 900px;
    }

    .logo {
      font-size: 20px;
    }

    .nav-link {
      font-size: var(--spacing-20);
    }
  }

  @media (max-width: 640px) {
    .navbar {
      padding: var(--spacing-16) var(--spacing-24);
    }

    .navbar-content {
      flex-direction: column;
      width: 100%;
      gap: var(--spacing-16);
    }

    .navbar-links {
      width: 100%;
      justify-content: center;
      gap: var(--spacing-8);
    }

    .nav-link {
      flex: 1;
      font-size: var(--spacing-16);
    }
  }
</style>
