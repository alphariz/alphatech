<script>
  let selectedService = null;

  const services = [
    {
      id: 'company-profile',
      letter: 'A',
      icon: '🌐',
      title: 'Website Profil Perusahaan (Company Profile)',
      shortDesc: 'Website profesional untuk mempresentasikan profil, visi, legalitas, dan portofolio produk/jasa perusahaan Anda.',
      desc: 'Pembuatan website profesional yang dirancang khusus untuk mempresentasikan profil, visi, legalitas, serta portofolio produk/jasa perusahaan Anda guna meningkatkan kredibilitas di mata klien, investor, dan lembaga keuangan.',
      badge: 'Populer untuk Bisnis & Koorporasi',
      features: [
        'Tampilan Adaptive & Responsive (Mobile, Tablet, Desktop)',
        'Optimasi SEO Dasar (Search Engine Optimization)',
        'Kecepatan Muat Situs Sangat Tinggi (< 1 Detik)',
        'Formulir Kontak Interaktif & Direct WhatsApp',
        'Galeri Portofolio & Katalog Produk',
        'Integrasi Peta Lokasi & Media Sosial'
      ]
    },
    {
      id: 'custom-web-app',
      letter: 'B',
      icon: '💻',
      title: 'Pengembangan Aplikasi Web (Custom Web Application)',
      shortDesc: 'Sistem informasi & aplikasi berbasis web kustom untuk manajemen internal dan layanan publik.',
      desc: 'Pengembangan sistem informasi dan aplikasi berbasis web yang disesuaikan (custom-built) untuk kebutuhan manajemen internal maupun layanan publik dengan keamanan dan skalabilitas tinggi.',
      badge: 'Solusi Kustom & Enterprise',
      features: [
        'Sistem Informasi Manajemen (SIM)',
        'Dashboard Analytical Real-Time & Reporting',
        'Portal CRM (Customer Relationship Management)',
        'Manajemen Inventaris & Stok Barang',
        'Integrasi API Payment Gateway & Third-Party System',
        'Manajemen Akses & Hak User Multi-Level'
      ]
    },
    {
      id: 'landing-page',
      letter: 'C',
      icon: '🎯',
      title: 'Landing Page Interaktif & Pemasaran Digital',
      shortDesc: 'Halaman penawaran khusus yang dioptimalkan untuk mengonversi pengunjung menjadi pelanggan potensial.',
      desc: 'Perancangan halaman penawaran khusus yang dioptimalkan secara psikologis dan visual untuk mengonversi pengunjung situs menjadi calon pelanggan potensial (lead generation & sales).',
      badge: 'High Conversion Rate',
      features: [
        'Desain Berfokus pada Konversi (Conversion-Focused)',
        'Kecepatan Muat Optimal & Lightweight',
        'Integrasi Direct WhatsApp Chat & Call-to-Action',
        'Pelacakan Analytics (Google Analytics & Meta Pixel)',
        'Copywriting Penawaran Persuasif',
        'A/B Testing Ready Architecture'
      ]
    },
    {
      id: 'web-maintenance',
      letter: 'D',
      icon: '🛡️',
      title: 'Pemeliharaan & Optimasi Sistem (Web Maintenance)',
      shortDesc: 'Layanan perawatan berkala untuk memastikan infrastruktur sistem berjalan tanpa gangguan (zero downtime).',
      desc: 'Layanan perawatan berkala untuk memastikan infrastruktur website dan aplikasi berjalan tanpa gangguan teknis (zero downtime), aman dari serangan siber, dan selalu berkinerja maksimal.',
      badge: 'Zero Downtime Guarantee',
      features: [
        'Pembaruan Sistem & Patch Keamanan Berkala',
        'Penyimpanan Backup Data Otomatis & Terjadwal',
        'Optimasi Performa Server & Cache Management',
        'Penanganan Bug & Dukungan Teknis (Helpdesk 24/7)',
        'Monitoring Uptime & Health Check',
        'Laporan Kinerja & Analytics Bulanan'
      ]
    }
  ];

  function openServiceModal(service) {
    selectedService = service;
  }

  function closeModal() {
    selectedService = null;
  }
</script>

<section id="layanan" class="services-section">
  <div class="container">
    <div class="section-header">
      <div class="badge">Layanan Kami</div>
      <h2>Solusi Digital <span class="text-gradient">Terintegrasi & Komprehensif</span></h2>
      <p>
        Dirancang khusus untuk mendukung pertumbuhan bisnis Anda melalui teknologi web berkualitas tinggi, aman, dan berkinerja maksimal.
      </p>
    </div>

    <!-- Services Grid -->
    <div class="services-grid">
      {#each services as service}
        <div class="glass-card service-card">
          <div class="card-top-bar">
            <span class="service-icon">{service.icon}</span>
            <span class="service-badge">{service.badge}</span>
          </div>

          <h3 class="service-title">{service.title}</h3>
          <p class="service-desc">{service.shortDesc}</p>

          <div class="features-preview">
            <div class="preview-header">Fitur & Keunggulan Utama:</div>
            <ul class="features-list">
              {#each service.features.slice(0, 4) as feat}
                <li>
                  <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="var(--accent-cyan)" stroke-width="2.5">
                    <polyline points="20 6 9 17 4 12"/>
                  </svg>
                  <span>{feat}</span>
                </li>
              {/each}
            </ul>
          </div>

          <div class="service-card-actions">
            <button class="btn btn-secondary btn-full" on:click={() => openServiceModal(service)}>
              <span>Detail Selengkapnya</span>
              <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M5 12h14M12 5l7 7-7 7"/>
              </svg>
            </button>
            <a 
              href="https://wa.me/6287828690059?text=Halo%20Alphatech,%20saya%20tertarik%20dengan%20layanan%20{encodeURIComponent(service.title)}."
              target="_blank"
              rel="noopener noreferrer"
              class="btn btn-whatsapp btn-icon-only"
              title="Konsultasikan Layanan ini via WhatsApp"
            >
              <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor">
                <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.501-.669-.51l-.57-.01c-.198 0-.52.074-.792.372s-1.04 1.016-1.04 2.479 1.065 2.876 1.213 3.074c.149.198 2.095 3.2 5.076 4.487.709.306 1.263.489 1.694.626.712.226 1.36.194 1.872.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.473-8.413"/>
              </svg>
            </a>
          </div>
        </div>
      {/each}
    </div>
  </div>

  <!-- Detail Modal -->
  {#if selectedService}
    <!-- svelte-ignore a11y-click-events-have-key-events a11y-no-static-element-interactions -->
    <div class="modal-backdrop" role="button" tabindex="-1" on:click={closeModal} on:keydown={(e) => e.key === 'Escape' && closeModal()}>
      <!-- svelte-ignore a11y-click-events-have-key-events a11y-no-static-element-interactions -->
      <div class="glass-card modal-card" role="dialog" aria-modal="true" on:click|stopPropagation>
        <button class="modal-close-btn" on:click={closeModal}>✕</button>
        
        <div class="modal-header">
          <span class="modal-icon">{selectedService.icon}</span>
          <div>
            <span class="modal-tag">{selectedService.badge}</span>
            <h3>{selectedService.title}</h3>
          </div>
        </div>

        <p class="modal-desc">{selectedService.desc}</p>

        <div class="modal-features-box">
          <h4>Cakupan & Fitur Lengkap:</h4>
          <ul>
            {#each selectedService.features as feat}
              <li>
                <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="var(--accent-cyan)" stroke-width="2.5">
                  <polyline points="20 6 9 17 4 12"/>
                </svg>
                <span>{feat}</span>
              </li>
            {/each}
          </ul>
        </div>

        <div class="modal-footer">
          <a 
            href="https://wa.me/6287828690059?text=Halo%20Alphatech,%20saya%20ingin%20berkonsultasi%20mengenai%20{encodeURIComponent(selectedService.title)}."
            target="_blank"
            rel="noopener noreferrer"
            class="btn btn-whatsapp btn-full"
          >
            <span>Konsultasikan Layanan Ini via WA</span>
          </a>
        </div>
      </div>
    </div>
  {/if}
</section>

<style>
  .services-section {
    position: relative;
  }

  .services-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 2rem;
  }

  .service-card {
    padding: 2rem;
    display: flex;
    flex-direction: column;
    height: 100%;
  }

  .card-top-bar {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 1.25rem;
  }

  .service-icon {
    font-size: 2.25rem;
  }

  .service-badge {
    font-size: 0.75rem;
    font-weight: 600;
    color: var(--accent-cyan);
    background: rgba(0, 242, 254, 0.08);
    padding: 0.3rem 0.75rem;
    border-radius: var(--radius-full);
    border: 1px solid rgba(0, 242, 254, 0.2);
  }

  .service-title {
    font-size: 1.35rem;
    color: var(--text-main);
    margin-bottom: 0.75rem;
  }

  .service-desc {
    font-size: 0.95rem;
    color: var(--text-muted);
    margin-bottom: 1.5rem;
    line-height: 1.6;
  }

  .features-preview {
    margin-top: auto;
    padding-top: 1.25rem;
    border-top: 1px solid var(--border-subtle);
    margin-bottom: 1.5rem;
  }

  .preview-header {
    font-size: 0.8rem;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.04em;
    color: var(--text-subtle);
    margin-bottom: 0.75rem;
  }

  .features-list {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
  }

  .features-list li {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    font-size: 0.875rem;
    color: var(--text-muted);
  }

  .service-card-actions {
    display: flex;
    align-items: center;
    gap: 0.75rem;
  }

  .btn-full {
    flex: 1;
  }

  .btn-icon-only {
    padding: 0.85rem;
    border-radius: var(--radius-full);
  }

  /* Modal Styling */
  .modal-backdrop {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(0, 0, 0, 0.75);
    backdrop-filter: blur(8px);
    z-index: 200;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 1.5rem;
  }

  .modal-card {
    max-width: 600px;
    width: 100%;
    padding: 2.5rem;
    position: relative;
    background: var(--bg-dark-surface);
  }

  .modal-close-btn {
    position: absolute;
    top: 1.25rem;
    right: 1.25rem;
    background: rgba(255, 255, 255, 0.08);
    border: none;
    color: var(--text-main);
    width: 32px;
    height: 32px;
    border-radius: 50%;
    cursor: pointer;
    font-size: 1.1rem;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .modal-header {
    display: flex;
    align-items: center;
    gap: 1rem;
    margin-bottom: 1.25rem;
  }

  .modal-icon {
    font-size: 2.5rem;
  }

  .modal-tag {
    font-size: 0.75rem;
    color: var(--accent-cyan);
    font-weight: 700;
    text-transform: uppercase;
  }

  .modal-header h3 {
    font-size: 1.35rem;
    color: var(--text-main);
  }

  .modal-desc {
    color: var(--text-muted);
    font-size: 0.975rem;
    line-height: 1.65;
    margin-bottom: 1.5rem;
  }

  .modal-features-box h4 {
    font-size: 0.95rem;
    color: var(--text-main);
    margin-bottom: 0.75rem;
  }

  .modal-features-box ul {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 0.6rem;
    margin-bottom: 2rem;
  }

  .modal-features-box li {
    display: flex;
    align-items: center;
    gap: 0.6rem;
    font-size: 0.925rem;
    color: var(--text-muted);
  }

  @media (max-width: 900px) {
    .services-grid {
      grid-template-columns: 1fr;
    }
  }
</style>
