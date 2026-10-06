<script>
  import { onMount } from 'svelte';

  let isScrolled = false;
  let mobileMenuOpen = false;
  let isDarkMode = true;

  const navLinks = [
    { label: 'Beranda', href: '#hero' },
    { label: 'Tentang Kami', href: '#tentang' },
    { label: 'Layanan', href: '#layanan' },
    { label: 'Keunggulan', href: '#keunggulan' },
    { label: 'Alur Kerja', href: '#alur-kerja' },
    { label: 'Kalkulator Proyek', href: '#estimasi' },
    { label: 'Hubungi Kami', href: '#kontak' }
  ];

  onMount(() => {
    const handleScroll = () => {
      isScrolled = window.scrollY > 30;
    };
    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  });

  function toggleTheme() {
    isDarkMode = !isDarkMode;
    if (isDarkMode) {
      document.documentElement.setAttribute('data-theme', 'dark');
      document.documentElement.classList.add('dark');
    } else {
      document.documentElement.setAttribute('data-theme', 'light');
      document.documentElement.classList.remove('dark');
    }
  }

  function closeMobileMenu() {
    mobileMenuOpen = false;
  }
</script>

<header class="navbar-wrapper {isScrolled ? 'scrolled' : ''}">
  <div class="container navbar-container">
    <!-- Brand Logo -->
    <a href="#hero" class="brand-logo" on:click={closeMobileMenu}>
      <div class="logo-icon">
        <svg width="28" height="28" viewBox="0 0 32 32" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M16 2L3 9.5V22.5L16 30L29 22.5V9.5L16 2Z" stroke="url(#logo-grad)" stroke-width="2.5" stroke-linejoin="round"/>
          <path d="M16 8L8 12.5V20L16 24.5L24 20V12.5L16 8Z" fill="url(#logo-grad-inner)" opacity="0.8"/>
          <circle cx="16" cy="16" r="3" fill="#00F2FE"/>
          <defs>
            <linearGradient id="logo-grad" x1="3" y1="2" x2="29" y2="30" gradientUnits="userSpaceOnUse">
              <stop stop-color="#00F2FE"/>
              <stop offset="0.5" stop-color="#4FACFE"/>
              <stop offset="1" stop-color="#8A2BE2"/>
            </linearGradient>
            <linearGradient id="logo-grad-inner" x1="8" y1="8" x2="24" y2="24.5" gradientUnits="userSpaceOnUse">
              <stop stop-color="#00F2FE"/>
              <stop offset="1" stop-color="#8A2BE2"/>
            </linearGradient>
          </defs>
        </svg>
      </div>
      <div class="logo-text-group">
        <span class="logo-title">ALPHATECH</span>
        <span class="logo-subtitle">Digitalization & Web Development</span>
      </div>
    </a>

    <!-- Desktop Navigation Links -->
    <nav class="desktop-nav">
      {#each navLinks as link}
        <a href={link.href} class="nav-link">{link.label}</a>
      {/each}
    </nav>

    <!-- Action Group (Theme Switcher + WhatsApp CTA) -->
    <div class="navbar-actions">
      <button 
        class="theme-toggle-btn" 
        on:click={toggleTheme}
        aria-label="Toggle Dark/Light Mode"
        title="Ubah Tema"
      >
        {#if isDarkMode}
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <circle cx="12" cy="12" r="5"/>
            <path d="M12 1v2M12 21v2M4.22 4.22l1.42 1.42M18.36 18.36l1.42 1.42M1 12h2M21 12h2M4.22 19.78l1.42-1.42M18.36 5.64l1.42-1.42"/>
          </svg>
        {:else}
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"/>
          </svg>
        {/if}
      </button>

      <a 
        href="https://wa.me/6287828690059?text=Halo%20Alphatech,%20saya%20tertarik%20untuk%20konsultasi%20proyek%20website%2Faplikasi%20web." 
        target="_blank" 
        rel="noopener noreferrer" 
        class="btn btn-whatsapp header-cta"
      >
        <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor">
          <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.501-.669-.51l-.57-.01c-.198 0-.52.074-.792.372s-1.04 1.016-1.04 2.479 1.065 2.876 1.213 3.074c.149.198 2.095 3.2 5.076 4.487.709.306 1.263.489 1.694.626.712.226 1.36.194 1.872.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.473-8.413"/>
        </svg>
        <span>Konsultasi WA</span>
      </a>

      <!-- Mobile Hamburger Toggle -->
      <button 
        class="mobile-toggle" 
        on:click={() => mobileMenuOpen = !mobileMenuOpen}
        aria-label="Toggle Mobile Menu"
      >
        <span class="hamburger-line {mobileMenuOpen ? 'open' : ''}"></span>
        <span class="hamburger-line {mobileMenuOpen ? 'open' : ''}"></span>
        <span class="hamburger-line {mobileMenuOpen ? 'open' : ''}"></span>
      </button>
    </div>
  </div>

  <!-- Mobile Drawer Menu -->
  {#if mobileMenuOpen}
    <div class="mobile-drawer">
      <nav class="mobile-nav">
        {#each navLinks as link}
          <a href={link.href} class="mobile-nav-link" on:click={closeMobileMenu}>
            {link.label}
          </a>
        {/each}
        <a 
          href="https://wa.me/6287828690059?text=Halo%20Alphatech,%20saya%20tertarik%20untuk%20konsultasi%20proyek%20website%2Faplikasi%20web." 
          target="_blank" 
          rel="noopener noreferrer" 
          class="btn btn-whatsapp mobile-cta"
          on:click={closeMobileMenu}
        >
          Konsultasi via WhatsApp (0878-2869-0059)
        </a>
      </nav>
    </div>
  {/if}
</header>

<style>
  .navbar-wrapper {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 100;
    padding: 1.25rem 0;
    transition: all var(--transition-smooth);
    background: transparent;
  }

  .navbar-wrapper.scrolled {
    padding: 0.75rem 0;
    background: var(--bg-card);
    backdrop-filter: blur(20px);
    -webkit-backdrop-filter: blur(20px);
    border-bottom: 1px solid var(--border-subtle);
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
  }

  .navbar-container {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .brand-logo {
    display: flex;
    align-items: center;
    gap: 0.75rem;
    text-decoration: none;
  }

  .logo-icon {
    display: flex;
    align-items: center;
    justify-content: center;
    filter: drop-shadow(0 0 10px rgba(0, 242, 254, 0.4));
  }

  .logo-text-group {
    display: flex;
    flex-direction: column;
  }

  .logo-title {
    font-family: var(--font-heading);
    font-weight: 800;
    font-size: 1.35rem;
    letter-spacing: 0.08em;
    color: var(--text-main);
    line-height: 1;
  }

  .logo-subtitle {
    font-size: 0.68rem;
    font-weight: 600;
    letter-spacing: 0.04em;
    color: var(--accent-cyan);
    text-transform: uppercase;
    margin-top: 2px;
  }

  .desktop-nav {
    display: flex;
    align-items: center;
    gap: 1.75rem;
  }

  .nav-link {
    color: var(--text-muted);
    text-decoration: none;
    font-size: 0.925rem;
    font-weight: 500;
    transition: color var(--transition-fast);
    position: relative;
  }

  .nav-link:hover {
    color: var(--accent-cyan);
  }

  .nav-link::after {
    content: '';
    position: absolute;
    bottom: -4px;
    left: 0;
    width: 0;
    height: 2px;
    background: var(--gradient-primary);
    transition: width var(--transition-fast);
    border-radius: 2px;
  }

  .nav-link:hover::after {
    width: 100%;
  }

  .navbar-actions {
    display: flex;
    align-items: center;
    gap: 1rem;
  }

  .theme-toggle-btn {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    border: 1px solid var(--border-subtle);
    background: rgba(255, 255, 255, 0.05);
    color: var(--text-main);
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: all var(--transition-fast);
  }

  .theme-toggle-btn:hover {
    background: rgba(255, 255, 255, 0.12);
    border-color: var(--accent-cyan);
    color: var(--accent-cyan);
    transform: rotate(15deg);
  }

  .header-cta {
    padding: 0.6rem 1.25rem;
    font-size: 0.875rem;
  }

  .mobile-toggle {
    display: none;
    flex-direction: column;
    justify-content: space-between;
    width: 38px;
    height: 38px;
    padding: 9px;
    background: rgba(255, 255, 255, 0.05);
    border: 1px solid var(--border-subtle);
    border-radius: var(--radius-sm);
    cursor: pointer;
  }

  .hamburger-line {
    width: 100%;
    height: 2px;
    background-color: var(--text-main);
    transition: all 0.3s ease;
  }

  .mobile-drawer {
    display: none;
    position: absolute;
    top: 100%;
    left: 0;
    right: 0;
    background: var(--bg-dark-surface);
    border-bottom: 1px solid var(--border-subtle);
    padding: 1.5rem;
    box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4);
  }

  .mobile-nav {
    display: flex;
    flex-direction: column;
    gap: 1.25rem;
  }

  .mobile-nav-link {
    color: var(--text-main);
    text-decoration: none;
    font-size: 1.05rem;
    font-weight: 600;
  }

  .mobile-cta {
    margin-top: 0.5rem;
    width: 100%;
    justify-content: center;
  }

  @media (max-width: 1024px) {
    .desktop-nav {
      display: none;
    }

    .header-cta {
      display: none;
    }

    .mobile-toggle {
      display: flex;
    }

    .mobile-drawer {
      display: block;
    }
  }
</style>
