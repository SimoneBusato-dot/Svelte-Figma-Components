<script lang="ts">
  import HeroSection from '$lib/components/HeroSection.svelte';
  import Section from '$lib/components/Section.svelte';
  import ApproachSection from '$lib/components/ApproachSection.svelte';

  // Hero images and assets
  const heroImage = 'https://www.figma.com/api/mcp/asset/7da4ef95-e51f-46c5-a8d7-182652814d15';
  
  // Section 2 image
  const section2Image = 'https://www.figma.com/api/mcp/asset/36dc6ea8-8231-4beb-aff0-8dd1c35016c2';
  
  // Section 3 image
  const section3Image = 'https://www.figma.com/api/mcp/asset/10888489-f1ca-4869-a8db-5a319c6ba433';

  // Approach cards data
  const approachCards = [
    {
      id: 1,
      title: 'Precision Chisel',
      description: 'Refining every detail with surgical accuracy',
      icon: `<svg viewBox="0 0 66 66" fill="none" xmlns="http://www.w3.org/2000/svg">
        <circle cx="33" cy="33" r="30" fill="currentColor" opacity="0.2"/>
        <path d="M33 15C23 15 15 23 15 33C15 43 23 51 33 51C43 51 51 43 51 33C51 23 43 15 33 15ZM33 38C30 38 28 36 28 33C28 30 30 28 33 28C36 28 38 30 38 33C38 36 36 38 33 38Z" fill="currentColor"/>
      </svg>`
    },
    {
      id: 2,
      title: 'Etched in Memory',
      description: 'Creating lasting impressions through design',
      icon: `<svg viewBox="0 0 66 66" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M33 15C23 15 15 23 15 33C15 43 23 51 33 51C43 51 51 43 51 33C51 23 43 15 33 15ZM38 35H30C28 35 27 34 27 32V28C27 26 28 25 30 25H38C40 25 41 26 41 28V32C41 34 40 35 38 35Z" fill="currentColor"/>
      </svg>`
    },
    {
      id: 3,
      title: 'Structured Clarity',
      description: 'Organizing complexity into comprehensible patterns',
      icon: `<svg viewBox="0 0 66 66" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M18 22H48V26H18V22ZM18 32H48V36H18V32ZM18 42H48V46H18V42Z" fill="currentColor"/>
      </svg>`
    },
    {
      id: 4,
      title: 'Inflexible Integrity',
      description: 'Maintaining principles and quality standards',
      icon: `<svg viewBox="0 0 66 66" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M33 15C23 15 15 23 15 33C15 43 23 51 33 51C43 51 51 43 51 33C51 23 43 15 33 15ZM38 35L30 43L22 35L25 32L30 37L35 32L38 35Z" fill="currentColor"/>
      </svg>`
    }
  ];
</script>

<svelte:head>
  <title>Studio - Data Design</title>
  <meta name="description" content="Transform raw data into unforgettable masterpieces" />
</svelte:head>

<HeroSection
  title="Embedded Data"
  description="The true value does not lie in the shapeless mass of information, but in the figure we extract through a process of deliberate subtraction and refinement."
  ctaPrimary={{ label: 'Get Started', href: '#approach' }}
  ctaSecondary={{ label: 'About Us', href: '#about' }}
  heroImage={undefined}
/>

<Section
  title="Defined by Precision"
  description="A breakdown of the core attributes chiseled into every analysis to ensure clarity, impact, and depth."
  image={section2Image}
  imagePosition="right"
/>

<Section
  title="Pillars of the Indelible"
  description="The structural qualities we carve into our work to make every insight impossible to ignore and harder to forget."
  image={section3Image}
  imagePosition="left"
/>

<ApproachSection
  id="approach"
  title="Our Approach"
  subtitle="Examining the sculpted traits that transform raw data into an unforgettable masterpiece"
  cards={approachCards}
/>