<script>
  const advantages = [
    {
      num: '01',
      icon: '⚡',
      title: 'Arsitektur Teknologi Terdepan',
      desc: 'Menggunakan tech stack modern yang menjamin kecepatan pemuatan situs yang sangat tinggi serta penggunaan sumber daya server yang efisien.',
      tags: ['Modern Framework', 'Lightweight', 'High Speed']
    },
    {
      num: '02',
      icon: '🔒',
      title: 'Keamanan & Stabilitas Data',
      desc: 'Menerapkan standar enkripsi data dan praktik pemrograman terbaik (best coding practices) untuk melindungi aset digital dari ancaman siber.',
      tags: ['SSL 256-Bit', 'Data Encryption', 'Best Coding Practices']
    },
    {
      num: '03',
      icon: '📱',
      title: 'Desain Adaptive & Multi-Platform',
      desc: 'Semua produk dioptimalkan agar dapat diakses dengan mulus dari berbagai ukuran layar, mulai dari smartphone, tablet, hingga PC desktop.',
      tags: ['Responsive UI', 'Cross-Browser', 'Mobile First']
    },
    {
      num: '04',
      icon: '⚙️',
      title: 'Skalabilitas Tinggi',
      desc: 'Sistem dirancang secara modular, memungkinkan pengembangan fitur baru secara fleksibel seiring bertumbuhnya skala bisnis Anda.',
      tags: ['Modular System', 'Future-Proof', 'Easy Expansion']
    },
    {
      num: '05',
      icon: '🤝',
      title: 'Dukungan Purna Jual Berkelanjutan',
      desc: 'Kami menyediakan pendampingan teknis dan perawatan pasca-peluncuran (go-live) untuk memastikan kelancaran operasional tanpa downtime.',
      tags: ['Technical Support', 'Maintenance', 'Go-Live Guarantee']
    }
  ];
</script>

<section id="keunggulan" class="why-us-section">
  <div class="container">
    <div class="section-header">
      <div class="badge">Keunggulan Kami</div>
      <h2>Mengapa Bermitra dengan <span class="text-gradient">Alphatech?</span></h2>
      <p>
        Standar kualitas dan komitmen tinggi untuk memastikan produk digital Anda unggul dalam performa, keamanan, dan skalabilitas.
      </p>
    </div>

    <!-- Advantages Grid Layout -->
    <div class="advantages-grid">
      {#each advantages as adv}
        <div class="glass-card advantage-card">
          <div class="adv-top-row">
            <span class="adv-icon">{adv.icon}</span>
            <span class="adv-num">{adv.num}</span>
          </div>

          <h3 class="adv-title">{adv.title}</h3>
          <p class="adv-desc">{adv.desc}</p>

          <div class="adv-tags">
            {#each adv.tags as tag}
              <span class="adv-tag">{tag}</span>
            {/each}
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>

<style>
  .why-us-section {
    background: var(--bg-dark-surface);
  }

  .advantages-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2rem;
  }

  .advantage-card {
    padding: 2rem;
    display: flex;
    flex-direction: column;
  }

  .advantage-card:nth-child(4),
  .advantage-card:nth-child(5) {
    grid-column: span 1.5;
  }

  .adv-top-row {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 1.5rem;
  }

  .adv-icon {
    font-size: 2.25rem;
  }

  .adv-num {
    font-family: var(--font-heading);
    font-size: 2rem;
    font-weight: 800;
    color: rgba(255, 255, 255, 0.1);
  }

  .adv-title {
    font-size: 1.25rem;
    color: var(--text-main);
    margin-bottom: 0.75rem;
  }

  .adv-desc {
    font-size: 0.95rem;
    color: var(--text-muted);
    line-height: 1.65;
    margin-bottom: 1.5rem;
  }

  .adv-tags {
    margin-top: auto;
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
  }

  .adv-tag {
    font-size: 0.725rem;
    font-weight: 600;
    color: var(--accent-cyan);
    background: rgba(0, 242, 254, 0.05);
    padding: 0.25rem 0.65rem;
    border-radius: var(--radius-sm);
    border: 1px solid rgba(0, 242, 254, 0.15);
  }

  @media (max-width: 1024px) {
    .advantages-grid {
      grid-template-columns: repeat(2, 1fr);
    }
    .advantage-card:nth-child(4),
    .advantage-card:nth-child(5) {
      grid-column: span 1;
    }
  }

  @media (max-width: 640px) {
    .advantages-grid {
      grid-template-columns: 1fr;
    }
  }
</style>
