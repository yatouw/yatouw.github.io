<script lang="ts">
  import dp from '$lib/assets/dp.jpg';
  import ecommerce1 from '$lib/assets/ecommerce1.png';
  import ecommerce2 from '$lib/assets/ecommerce2.png';
  import cepa1 from '$lib/assets/cepa1.png';
  import cepa2 from '$lib/assets/cepa2.png';

  interface Project {
    title: string;
    description: string;
    image: string[];
    currentImageIndex: number;
  }


  let projects: Project[] = [
    {
      title: "E-Commerce Website",
      description: "A fully functional e-commerce site built with Angular and PHP.",
      image: [ecommerce1, ecommerce2],
      currentImageIndex: 0
    },
    {
      title: "CEPA Project",
      description: "Community Extension Participation Attendance: A platform designed to streamline community event participation.",
      image: [cepa1, cepa2],
      currentImageIndex: 0
    }
  ];


  function toggleImage(index: number) {
    projects[index].currentImageIndex = (projects[index].currentImageIndex + 1) % projects[index].image.length;
  }


</script>

<section class="min-h-screen hero-section">
  <div class="text-right text-white max-w-lg">
    <h1 class="hero-title">
      Hi, I'm <span class="highlighted-text">Jayvee</span>
    </h1>
    <p class="hero-description">
      A BSIT student, focused on building functional websites.
    </p>
  </div>
  <div class="hero-image-container">
    <img src={dp} alt="Jayvee" class="hero-image">
  </div>
</section>

<section class="projects-section">
  <h2 class="section-title">My Projects</h2>
  <div class="projects-grid">
    {#each projects as project, i}
      <div class="project-card">
        <img src={project.image[project.currentImageIndex]} alt={project.title} class="project-image">
        <h3 class="project-title">{project.title}</h3>
        <p class="project-description">{project.description}</p>
        {#if project.image.length > 1}
          <button on:click={() => toggleImage(i)} class="toggle-button">
            Next Image
          </button>
        {/if}
      </div>
    {/each}
  </div>
</section>

<section class="skills-section">
  <h2 class="section-title">Skills</h2>
  <div class="skills-grid">
    <div class="skill">HTML</div>
    <div class="skill">CSS</div>
    <div class="skill">Svelte</div>
    <div class="skill">Angular</div>
    <div class="skill">PHP</div>
  </div>
</section>