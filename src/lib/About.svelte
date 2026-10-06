<script>
  const sectors = [
    {
      icon: '🏪',
      title: 'Usaha Kecil & Menengah (UMKM)',
      desc: 'Meningkatkan kredibilitas & visibilitas merk melalui website profesional yang ramah anggaran.'
    },
    {
      icon: '🏢',
      title: 'Instansi Swasta & Korporasi',
      desc: 'Membangun infrastruktur sistem web kustom untuk otomatisasi dan efisiensi operasional bisnis.'
    },
    {
      icon: '💼',
      title: 'Institusi Bisnis & Startup',
      desc: 'Pengembangan web application yang scalable, aman, dan siap menghadapi ekspansi pasar.'
    }
  ];

  const coreValues = [
    { title: 'Arsitektur Modern', value: '100% Scalable' },
    { title: 'Optimasi Performa', value: '< 1s Load Speed' },
    { title: 'Standar Keamanan', value: 'SSL 256-Bit' },
    { title: 'Layanan Purna Jual', value: '24/7 Support' }
  ];
</script>

<section id="tentang" class="about-section">
  <div class="container">
    <div class="section-header">
      <div class="badge">Tentang Alphatech</div>
      <h2>Membantu Bisnis Bertumbuh Melalui <span class="text-gradient">Teknologi Digital</span></h2>
      <p>
        Mitra strategis Anda dalam mengadopsi teknologi web terkini untuk efisiensi operasional dan pertumbuhan jangka panjang.
      </p>
    </div>

    <!-- Main Content Grid -->
    <div class="about-grid">
      <!-- Left Column: Story & Vision -->
      <div class="glass-card about-card-main">
        <div class="about-text-content">
          <h3 class="about-subtitle">Transformasi Digital yang Berkelanjutan & Terpercaya</h3>
          
          <p class="about-paragraph">
            <strong>Alphatech</strong> adalah entitas bisnis yang bergerak di bidang penyediaan jasa pengembangan website dan aplikasi berbasis web (<em>web applications</em>). Kami mendampingi berbagai sektor usaha—mulai dari usaha kecil dan menengah (UMKM), instansi swasta, hingga institusi bisnis—dalam mengadopsi teknologi digital untuk meningkatkan efisiensi operasional, visibilitas merk, serta jangkauan pasar.
          </p>

          <p class="about-paragraph">
            Dengan berfokus pada arsitektur sistem modern, performa tinggi, serta proteksi keamanan yang kokoh, Alphatech memastikan setiap produk digital yang kami bangun tidak hanya menarik secara visual, tetapi juga memberikan nilai tambah finansial dan manajerial bagi bisnis klien.
          </p>

          <div class="vision-mission-box">
            <div class="vm-item">
              <div class="vm-header">
                <span class="vm-icon">🎯</span>
                <h4>Visi Kami</h4>
              </div>
              <p>Menjadi mitra teknologi tepercaya bagi pelaku usaha dan organisasi dalam merealisasikan transformasi digital yang andal, efisien, dan berkelanjutan.</p>
            </div>

            <div class="vm-item">
              <div class="vm-header">
                <span class="vm-icon">🚀</span>
                <h4>Misi Utama</h4>
              </div>
              <ul>
                <li>Menghadirkan produk perangkat lunak berkualitas tinggi dengan arsitektur teknologi modern.</li>
                <li>Memberikan solusi teknologi yang disesuaikan dengan kebutuhan & alur kerja spesifik klien.</li>
                <li>Memastikan standar keamanan data, performa sistem optimal, dan layanan purna jual berkelanjutan.</li>
              </ul>
            </div>
          </div>
        </div>
      </div>

      <!-- Right Column: Target Sectors & Value Counters -->
      <div class="about-right-col">
        <h3 class="sectors-title">Sektor Usaha yang Kami Dampingi</h3>
        
        <div class="sectors-list">
          {#each sectors as sector}
            <div class="glass-card sector-card">
              <span class="sector-icon">{sector.icon}</span>
              <div class="sector-text">
                <h4>{sector.title}</h4>
                <p>{sector.desc}</p>
              </div>
            </div>
          {/each}
        </div>

        <!-- Metric Stat Cards -->
        <div class="values-grid">
          {#each coreValues as item}
            <div class="value-box">
              <div class="value-num text-gradient">{item.value}</div>
              <div class="value-title">{item.title}</div>
            </div>
          {/each}
        </div>
      </div>
    </div>
  </div>
</section>

<style>
  .about-section {
    background: linear-gradient(180deg, var(--bg-dark) 0%, var(--bg-dark-surface) 100%);
  }

  .about-grid {
    display: grid;
    grid-template-columns: 1.2fr 0.8fr;
    gap: 2.5rem;
    align-items: start;
  }

  .about-card-main {
    padding: 2.5rem;
  }

  .about-subtitle {
    font-size: 1.5rem;
    color: var(--text-main);
    margin-bottom: 1.25rem;
  }

  .about-paragraph {
    color: var(--text-muted);
    font-size: 1.025rem;
    line-height: 1.75;
    margin-bottom: 1.25rem;
  }

  .vision-mission-box {
    margin-top: 2rem;
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
    padding-top: 1.5rem;
    border-top: 1px solid var(--border-subtle);
  }

  .vm-header {
    display: flex;
    align-items: center;
    gap: 0.6rem;
    margin-bottom: 0.5rem;
  }

  .vm-icon {
    font-size: 1.25rem;
  }

  .vm-header h4 {
    font-size: 1.15rem;
    color: var(--accent-cyan);
  }

  .vm-item p {
    color: var(--text-muted);
    font-size: 0.95rem;
  }

  .vm-item ul {
    list-style: none;
    padding-left: 0;
    display: flex;
    flex-direction: column;
    gap: 0.4rem;
  }

  .vm-item ul li {
    position: relative;
    padding-left: 1.25rem;
    color: var(--text-muted);
    font-size: 0.925rem;
  }

  .vm-item ul li::before {
    content: '✓';
    position: absolute;
    left: 0;
    color: var(--accent-cyan);
    font-weight: bold;
  }

  .about-right-col {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
  }

  .sectors-title {
    font-size: 1.25rem;
    color: var(--text-main);
  }

  .sectors-list {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .sector-card {
    padding: 1.25rem;
    display: flex;
    align-items: flex-start;
    gap: 1.25rem;
  }

  .sector-icon {
    font-size: 2rem;
    padding: 0.5rem;
    background: rgba(0, 242, 254, 0.06);
    border-radius: var(--radius-sm);
  }

  .sector-text h4 {
    font-size: 1.05rem;
    color: var(--text-main);
    margin-bottom: 0.25rem;
  }

  .sector-text p {
    font-size: 0.875rem;
    color: var(--text-muted);
    line-height: 1.5;
  }

  .values-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1rem;
    margin-top: 0.5rem;
  }

  .value-box {
    background: rgba(255, 255, 255, 0.02);
    border: 1px solid var(--border-subtle);
    border-radius: var(--radius-md);
    padding: 1.25rem;
    text-align: center;
  }

  .value-num {
    font-family: var(--font-heading);
    font-size: 1.5rem;
    font-weight: 800;
    margin-bottom: 0.25rem;
  }

  .value-title {
    font-size: 0.8rem;
    color: var(--text-muted);
    font-weight: 600;
  }

  @media (max-width: 1024px) {
    .about-grid {
      grid-template-columns: 1fr;
    }
  }
</style>
