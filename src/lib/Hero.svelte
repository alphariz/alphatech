<script>
  import { onMount } from 'svelte';

  let performanceScore = 99;
  let activeUsers = 1420;
  let securityStatus = "SSL 256-Bit Active";

  // Simulate active dynamic telemetry pulse
  onMount(() => {
    const interval = setInterval(() => {
      activeUsers = 1400 + Math.floor(Math.random() * 50);
    }, 3000);
    return () => clearInterval(interval);
  });
</script>

<section id="hero" class="hero-section">
  <!-- Glowing Background Orbs -->
  <div class="glow-orb orb-1"></div>
  <div class="glow-orb orb-2"></div>
  <div class="cyber-grid"></div>

  <div class="container hero-container">
    <div class="hero-content">
      <!-- Badge -->
      <div class="badge hero-badge">
        <span class="badge-dot"></span>
        <span>Mitra Transformasi Digital Terpercaya</span>
      </div>

      <!-- Headline -->
      <h1 class="hero-title">
        Mitra Solusi Digitalisasi & <span class="text-gradient">Pengembangan Aplikasi Web Modern</span>
      </h1>

      <!-- Subheadline -->
      <p class="hero-description">
        Alphatech membantu memperkuat infrastruktur digital bisnis Anda melalui pembuatan website dan sistem aplikasi web yang tangguh, aman, berkecepatan tinggi, dan dapat disesuaikan dengan kebutuhan operasional.
      </p>

      <!-- CTA Buttons -->
      <div class="hero-cta-group">
        <a 
          href="https://wa.me/6287828690059?text=Halo%20Alphatech,%20saya%20tertarik%20untuk%20konsultasi%20proyek%20digitalisasi%20website%2Faplikasi%20web." 
          target="_blank" 
          rel="noopener noreferrer" 
          class="btn btn-whatsapp hero-btn-main"
        >
          <svg width="22" height="22" viewBox="0 0 24 24" fill="currentColor">
            <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.501-.669-.51l-.57-.01c-.198 0-.52.074-.792.372s-1.04 1.016-1.04 2.479 1.065 2.876 1.213 3.074c.149.198 2.095 3.2 5.076 4.487.709.306 1.263.489 1.694.626.712.226 1.36.194 1.872.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.473-8.413"/>
          </svg>
          <span>Konsultasi Proyek via WhatsApp</span>
        </a>

        <a href="#layanan" class="btn btn-secondary hero-btn-sec">
          <span>Pelajari Layanan Kami</span>
          <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <path d="M5 12h14M12 5l7 7-7 7"/>
          </svg>
        </a>
      </div>

      <!-- Quick Trust Indicators -->
      <div class="hero-trust-bar">
        <div class="trust-item">
          <span class="trust-icon">⚡</span>
          <span>Performa Berkecepatan Tinggi</span>
        </div>
        <div class="trust-divider"></div>
        <div class="trust-item">
          <span class="trust-icon">🛡️</span>
          <span>Keamanan Data Terenkripsi</span>
        </div>
        <div class="trust-divider"></div>
        <div class="trust-item">
          <span class="trust-icon">🛠️</span>
          <span>Dukungan Maintenance Total</span>
        </div>
      </div>
    </div>

    <!-- Hero Interactive Tech Card Showcase -->
    <div class="hero-visual">
      <div class="glass-card tech-showcase-card">
        <div class="card-window-bar">
          <div class="window-dots">
            <span class="dot dot-red"></span>
            <span class="dot dot-yellow"></span>
            <span class="dot dot-green"></span>
          </div>
          <span class="window-title">Alphatech Architecture Engine v2.6</span>
          <div class="live-status-pill">
            <span class="pulse-green"></span>
            <span>SYSTEM ACTIVE</span>
          </div>
        </div>

        <div class="card-content-grid">
          <!-- Metric 1 -->
          <div class="metric-box">
            <div class="metric-header">
              <span class="metric-label">Lighthouse Score</span>
              <span class="metric-icon">🚀</span>
            </div>
            <div class="metric-value">{performanceScore}/100</div>
            <div class="metric-bar-bg">
              <div class="metric-bar-fill" style="width: 99%;"></div>
            </div>
            <span class="metric-footer">Optimasi Kecepatan & SEO</span>
          </div>

          <!-- Metric 2 -->
          <div class="metric-box">
            <div class="metric-header">
              <span class="metric-label">System Security</span>
              <span class="metric-icon">🔒</span>
            </div>
            <div class="metric-value text-cyan">256-Bit</div>
            <div class="metric-sub-tag">{securityStatus}</div>
            <span class="metric-footer">Proteksi Siber Tingkat Tinggi</span>
          </div>

          <!-- Metric 3 -->
          <div class="metric-box full-width">
            <div class="metric-header">
              <span class="metric-label">Arsitektur Modular & Scalable</span>
              <span class="metric-icon">⚙️</span>
            </div>
            <div class="tech-stack-pills">
              <span class="stack-pill">Modern JS/Svelte</span>
              <span class="stack-pill">API Gateway</span>
              <span class="stack-pill">Cloud Server</span>
              <span class="stack-pill">Automated Backup</span>
            </div>
          </div>
        </div>

        <!-- Floating Accent Badges -->
        <div class="floating-badge badge-top-right">
          <span class="badge-icon">⚡</span>
          <div class="badge-text">
            <strong>0.6s Load Time</strong>
            <span>Instant Response</span>
          </div>
        </div>

        <div class="floating-badge badge-bottom-left">
          <span class="badge-icon">🤝</span>
          <div class="badge-text">
            <strong>100% Custom Built</strong>
            <span>Sesuai Kebutuhan Client</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<style>
  .hero-section {
    padding-top: 10rem;
    padding-bottom: 7rem;
    min-height: 90vh;
    display: flex;
    align-items: center;
    overflow: hidden;
  }

  .cyber-grid {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-image: 
      linear-gradient(to right, rgba(255, 255, 255, 0.03) 1px, transparent 1px),
      linear-gradient(to bottom, rgba(255, 255, 255, 0.03) 1px, transparent 1px);
    background-size: 60px 60px;
    mask-image: radial-gradient(circle at 50% 40%, black 30%, transparent 80%);
    -webkit-mask-image: radial-gradient(circle at 50% 40%, black 30%, transparent 80%);
    pointer-events: none;
  }

  .glow-orb {
    position: absolute;
    border-radius: 50%;
    filter: blur(120px);
    pointer-events: none;
    opacity: 0.45;
  }

  .orb-1 {
    top: 10%;
    left: 15%;
    width: 450px;
    height: 450px;
    background: radial-gradient(circle, #00F2FE 0%, rgba(0, 242, 254, 0) 70%);
  }

  .orb-2 {
    bottom: 10%;
    right: 15%;
    width: 500px;
    height: 500px;
    background: radial-gradient(circle, #7F56D9 0%, rgba(127, 86, 217, 0) 70%);
  }

  .hero-container {
    display: grid;
    grid-template-columns: 1.15fr 0.85fr;
    gap: 3.5rem;
    align-items: center;
    position: relative;
    z-index: 2;
  }

  .hero-badge {
    margin-bottom: 1.5rem;
  }

  .hero-title {
    font-size: clamp(2.4rem, 5vw, 3.8rem);
    line-height: 1.15;
    margin-bottom: 1.5rem;
    letter-spacing: -0.03em;
  }

  .hero-description {
    font-size: 1.15rem;
    color: var(--text-muted);
    line-height: 1.7;
    margin-bottom: 2.5rem;
    max-width: 620px;
  }

  .hero-cta-group {
    display: flex;
    align-items: center;
    gap: 1.25rem;
    flex-wrap: wrap;
    margin-bottom: 3rem;
  }

  .hero-btn-main {
    padding: 1rem 2.2rem;
    font-size: 1.05rem;
  }

  .hero-btn-sec {
    padding: 1rem 2.2rem;
    font-size: 1.05rem;
  }

  .hero-trust-bar {
    display: flex;
    align-items: center;
    gap: 1.25rem;
    padding-top: 1.5rem;
    border-top: 1px solid var(--border-subtle);
    flex-wrap: wrap;
  }

  .trust-item {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    font-size: 0.875rem;
    color: var(--text-muted);
    font-weight: 500;
  }

  .trust-divider {
    width: 4px;
    height: 4px;
    border-radius: 50%;
    background-color: var(--border-subtle);
  }

  /* Visual Showcase Card */
  .tech-showcase-card {
    padding: 1.5rem;
    background: rgba(14, 19, 31, 0.85);
    border: 1px solid rgba(0, 242, 254, 0.2);
    box-shadow: 0 20px 50px rgba(0, 0, 0, 0.5), 0 0 30px rgba(0, 242, 254, 0.15);
  }

  .card-window-bar {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding-bottom: 1rem;
    margin-bottom: 1.25rem;
    border-bottom: 1px solid var(--border-subtle);
  }

  .window-dots {
    display: flex;
    gap: 6px;
  }

  .dot {
    width: 10px;
    height: 10px;
    border-radius: 50%;
  }

  .dot-red { background: #FF5F56; }
  .dot-yellow { background: #FFBD2E; }
  .dot-green { background: #27C93F; }

  .window-title {
    font-size: 0.75rem;
    font-family: monospace;
    color: var(--text-subtle);
  }

  .live-status-pill {
    display: flex;
    align-items: center;
    gap: 6px;
    font-size: 0.7rem;
    font-weight: 700;
    color: var(--accent-emerald);
    background: rgba(16, 185, 129, 0.1);
    padding: 3px 8px;
    border-radius: var(--radius-full);
  }

  .pulse-green {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: var(--accent-emerald);
    box-shadow: 0 0 8px var(--accent-emerald);
    animation: pulse-dot 1.5s infinite;
  }

  .card-content-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1rem;
  }

  .metric-box {
    background: rgba(255, 255, 255, 0.03);
    border: 1px solid var(--border-subtle);
    border-radius: var(--radius-sm);
    padding: 1.15rem;
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
  }

  .metric-box.full-width {
    grid-column: span 2;
  }

  .metric-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .metric-label {
    font-size: 0.8rem;
    color: var(--text-muted);
    font-weight: 600;
  }

  .metric-value {
    font-size: 1.75rem;
    font-family: var(--font-heading);
    font-weight: 800;
    color: var(--text-main);
  }

  .text-cyan {
    color: var(--accent-cyan);
  }

  .metric-bar-bg {
    width: 100%;
    height: 6px;
    background: rgba(255, 255, 255, 0.1);
    border-radius: 3px;
    overflow: hidden;
  }

  .metric-bar-fill {
    height: 100%;
    background: var(--gradient-primary);
    border-radius: 3px;
  }

  .metric-sub-tag {
    font-size: 0.75rem;
    color: var(--accent-cyan);
    font-weight: 600;
  }

  .metric-footer {
    font-size: 0.725rem;
    color: var(--text-subtle);
  }

  .tech-stack-pills {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    margin-top: 0.25rem;
  }

  .stack-pill {
    font-size: 0.75rem;
    padding: 0.25rem 0.65rem;
    border-radius: var(--radius-sm);
    background: rgba(0, 242, 254, 0.08);
    border: 1px solid rgba(0, 242, 254, 0.2);
    color: var(--text-main);
    font-weight: 500;
  }

  .floating-badge {
    position: absolute;
    display: flex;
    align-items: center;
    gap: 0.75rem;
    padding: 0.75rem 1rem;
    background: var(--bg-dark-surface);
    border: 1px solid var(--border-highlight);
    border-radius: var(--radius-md);
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.4);
  }

  .badge-top-right {
    top: -15px;
    right: -20px;
  }

  .badge-bottom-left {
    bottom: -20px;
    left: -20px;
  }

  .badge-icon {
    font-size: 1.4rem;
  }

  .badge-text {
    display: flex;
    flex-direction: column;
  }

  .badge-text strong {
    font-size: 0.85rem;
    color: var(--text-main);
  }

  .badge-text span {
    font-size: 0.725rem;
    color: var(--text-muted);
  }

  @media (max-width: 1024px) {
    .hero-container {
      grid-template-columns: 1fr;
      text-align: center;
    }

    .hero-description {
      margin-left: auto;
      margin-right: auto;
    }

    .hero-cta-group {
      justify-content: center;
    }

    .hero-trust-bar {
      justify-content: center;
    }

    .hero-visual {
      max-width: 520px;
      margin: 0 auto;
    }

    .badge-top-right, .badge-bottom-left {
      display: none;
    }
  }
</style>
