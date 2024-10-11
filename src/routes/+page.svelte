<script>
  import dp from '$lib/assets/dp.jpg';
  import ecommerce1 from '$lib/assets/ecommerce1.png';
  import ecommerce2 from '$lib/assets/ecommerce2.png';

  // Add project images
  let projects = [
    {
      title: "E-Commerce Website",
      description: "A fully functional e-commerce site built with Angular and PHP.",
      image: [ecommerce1, ecommerce2]
    },
    {
      title: "CEPA Project",
      description: "Community Extension Participation Attendance: A platform designed to streamline community event participation and enhance engagement through attendance tracking and event analytics.",
      image: ""
    }
  ];

  let currentImageIndex = 0;

  function toggleImage() {
    currentImageIndex = (currentImageIndex + 1) % projects[0].image.length;
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
    {#each projects as project}
      <div class="project-card">
        <img src={project.image[currentImageIndex]} alt={project.title} class="project-image">
        <h3 class="project-title">{project.title}</h3>
        <p class="project-description">{project.description}</p>
        {#if project.image.length > 1}
          <button on:click={toggleImage} class="toggle-button">
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
    <div class="skill">Python</div>
  </div>
</section>