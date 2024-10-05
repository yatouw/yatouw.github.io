<script>
    import "../app.css";
    
    let navItems = [
      { name: "Home", href: "/" },
      { name: "About Me", href: "/about-me" },
      { name: "Contact", href: "/contact" },
    ];
  </script>
  
  <nav class="bg-gray-900 text-white py-4 fixed w-full top-0 z-10 shadow-lg">
    <div class="container mx-auto flex justify-between items-center">
      <a href="/" class="text-2xl font-bold">MyPortfolio</a>
      <div class="space-x-6 hidden md:flex">
        {#each navItems as item}
          <a href={item.href} class="hover:text-blue-400 transition">
            {item.name}
          </a>
        {/each}
      </div>
      <!-- Hamburger Menu for mobile -->
      <div class="md:hidden">
        <button class="text-white focus:outline-none" id="menu-toggle">
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7"/>
          </svg>
        </button>
      </div>
    </div>
  </nav>
  
  <!-- Main Content -->
  <slot />
  
  