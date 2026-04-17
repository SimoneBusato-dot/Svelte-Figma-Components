<script lang="ts">
  import NavBar from '$lib/components/NavBar.svelte';
  import HeroSection from '$lib/components/HeroSection.svelte';
  import Section from '$lib/components/Section.svelte';
  import ApproachSection from '$lib/components/ApproachSection.svelte';

  // Hero images and assets
  const heroImage = 'https://www.figma.com/api/mcp/asset/7da4ef95-e51f-46c5-a8d7-182652814d15';
  
  // Section 2 image
  const section2Image = 'https://www.figma.com/api/mcp/asset/36dc6ea8-8231-4beb-aff0-8dd1c35016c2';
  
  // Section 3 image
  const section3Image = 'https://www.figma.com/api/mcp/asset/10888489-f1ca-4869-a8db-5a319c6ba433';

  // Approach section icons
  const iconPrecisionChisel = 'https://www.figma.com/api/mcp/asset/a06758b1-17c8-48ff-88d7-41f56c83b86b';
  const iconEtchedMemory = 'https://www.figma.com/api/mcp/asset/c3aec1b3-1e2f-49f5-a161-b8241a813ba3';
  const iconStructuredClarity = 'https://www.figma.com/api/mcp/asset/00cd79f9-347a-4927-ad8f-32a13a7644d8';
  const iconInflexibleIntegrity = 'https://www.figma.com/api/mcp/asset/aa8aaa1b-51fa-4ec1-9561-d02da30137fd';

  // Approach cards data
  const approachCards = [
    {
      id: 1,
      title: 'Precision Chisel',
      description: 'Refining every detail with surgical accuracy',
      icon: `<img src="${iconPrecisionChisel}" alt="Precision Chisel" style="width: 100%; height: 100%; object-fit: contain;" />`
    },
    {
      id: 2,
      title: 'Etched in Memory',
      description: 'Creating lasting impressions through design',
      icon: `<img src="${iconEtchedMemory}" alt="Etched in Memory" style="width: 100%; height: 100%; object-fit: contain;" />`
    },
    {
      id: 3,
      title: 'Structured Clarity',
      description: 'Organizing complexity into comprehensible patterns',
      icon: `<img src="${iconStructuredClarity}" alt="Structured Clarity" style="width: 100%; height: 100%; object-fit: contain;" />`
    },
    {
      id: 4,
      title: 'Inflexible Integrity',
      description: 'Maintaining principles and quality standards',
      icon: `<img src="${iconInflexibleIntegrity}" alt="Inflexible Integrity" style="width: 100%; height: 100%; object-fit: contain;" />`
    }
  ];
</script>

<svelte:head>
  <title>Studio - Data Design</title>
  <meta name="description" content="Transform raw data into unforgettable masterpieces" />
</svelte:head>

<NavBar />

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