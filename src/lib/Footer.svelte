<script>
  const currentYear = new Date().getFullYear();
</script>

<footer class="footer-wrapper">
  <div class="container">
    <div class="footer-grid">
      <!-- Brand & Profile Column -->
      <div class="footer-brand-col">
        <a href="#hero" class="footer-logo">
          <svg width="26" height="26" viewBox="0 0 32 32" fill="none">
            <path d="M16 2L3 9.5V22.5L16 30L29 22.5V9.5L16 2Z" stroke="#00F2FE" stroke-width="2.5" stroke-linejoin="round"/>
            <circle cx="16" cy="16" r="3" fill="#00F2FE"/>
          </svg>
          <span class="logo-text">ALPHATECH</span>
        </a>
        <p class="footer-desc">
          Alphatech — Penyedia Layanan Pengembangan Website dan Aplikasi Web Profesional. Menjadi mitra teknologi tepercaya untuk efisiensi & transformasi digital bisnis Anda.
        </p>
        <div class="footer-wa-badge">
          <span class="pulse-green"></span>
          <span>WhatsApp Official: <a href="https://wa.me/6287828690059" target="_blank" rel="noopener noreferrer">+62 878-2869-0059</a></span>
        </div>
      </div>

      <!-- Navigation Links -->
      <div class="footer-links-col">
        <h4>Navigasi Cepat</h4>
        <ul>
          <li><a href="#hero">Beranda</a></li>
          <li><a href="#tentang">Tentang Kami</a></li>
          <li><a href="#layanan">Layanan Kami</a></li>
          <li><a href="#keunggulan">Keunggulan</a></li>
          <li><a href="#alur-kerja">Alur Kerja</a></li>
          <li><a href="#estimasi">Kalkulator Proyek</a></li>
        </ul>
      </div>

      <!-- Services Quick List -->
      <div class="footer-services-col">
        <h4>Layanan Utama</h4>
        <ul>
          <li><span>Website Profil Perusahaan</span></li>
          <li><span>Custom Web Application</span></li>
          <li><span>Landing Page Interaktif</span></li>
          <li><span>Pemeliharaan System (Maintenance)</span></li>
        </ul>
      </div>
    </div>

    <div class="footer-bottom">
      <p>© {currentYear} Alphatech. Seluruh Hak Cipta Dilindungi Undang-Undang.</p>
      <div class="footer-tagline">Engineered with Precision & High Performance</div>
    </div>
  </div>
</footer>

<style>
  .footer-wrapper {
    background: var(--bg-dark);
    border-top: 1px solid var(--border-subtle);
    padding-top: 4.5rem;
    padding-bottom: 2.5rem;
  }

  .footer-grid {
    display: grid;
    grid-template-columns: 2fr 1fr 1fr;
    gap: 3.5rem;
    margin-bottom: 3.5rem;
  }

  .footer-logo {
    display: flex;
    align-items: center;
    gap: 0.6rem;
    text-decoration: none;
    margin-bottom: 1rem;
  }

  .logo-text {
    font-family: var(--font-heading);
    font-size: 1.4rem;
    font-weight: 800;
    letter-spacing: 0.06em;
    color: var(--text-main);
  }

  .footer-desc {
    font-size: 0.925rem;
    color: var(--text-muted);
    line-height: 1.65;
    margin-bottom: 1.25rem;
    max-width: 440px;
  }

  .footer-wa-badge {
    display: inline-flex;
    align-items: center;
    gap: 0.6rem;
    font-size: 0.85rem;
    color: var(--text-main);
    background: rgba(255, 255, 255, 0.04);
    padding: 0.4rem 0.9rem;
    border-radius: var(--radius-full);
    border: 1px solid var(--border-subtle);
  }

  .footer-wa-badge a {
    color: var(--accent-cyan);
    font-weight: 700;
    text-decoration: none;
  }

  .footer-wa-badge a:hover {
    text-decoration: underline;
  }

  .pulse-green {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: var(--accent-emerald);
    box-shadow: 0 0 8px var(--accent-emerald);
  }

  .footer-links-col h4, .footer-services-col h4 {
    font-size: 1rem;
    color: var(--text-main);
    margin-bottom: 1.25rem;
  }

  .footer-links-col ul, .footer-services-col ul {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
  }

  .footer-links-col a {
    color: var(--text-muted);
    text-decoration: none;
    font-size: 0.9rem;
    transition: color var(--transition-fast);
  }

  .footer-links-col a:hover {
    color: var(--accent-cyan);
  }

  .footer-services-col span {
    color: var(--text-muted);
    font-size: 0.9rem;
  }

  .footer-bottom {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding-top: 2rem;
    border-top: 1px solid var(--border-subtle);
    font-size: 0.85rem;
    color: var(--text-subtle);
  }

  @media (max-width: 900px) {
    .footer-grid {
      grid-template-columns: 1fr;
      gap: 2rem;
    }
    .footer-bottom {
      flex-direction: column;
      gap: 0.5rem;
      text-align: center;
    }
  }
</style>
