<script>
  let name = '';
  let email = '';
  let serviceType = 'Website Profil Perusahaan';
  let message = '';

  function handleSubmit() {
    const waText = `Halo Alphatech, saya ingin berkonsultasi mengenai proyek digital.\n\n👤 *Nama:* ${name || '-'}\n📧 *Email:* ${email || '-'}\n📌 *Layanan:* ${serviceType}\n💬 *Pesan/Kebutuhan:* ${message || '-'}`;
    window.open(`https://wa.me/6287828690059?text=${encodeURIComponent(waText)}`, '_blank');
  }
</script>

<section id="kontak" class="contact-section">
  <!-- Glow Elements -->
  <div class="cta-glow"></div>

  <div class="container">
    <div class="glass-card contact-main-card">
      <div class="contact-grid">
        <!-- Left Side: Call to Action Details -->
        <div class="contact-info">
          <div class="badge contact-badge">
            <span class="badge-dot"></span>
            <span>Status: Siap Menerima Proyek Baru</span>
          </div>

          <h2 class="contact-title">
            Siap Bertransformasi ke Era Digital <span class="text-gradient">Bersama Alphatech?</span>
          </h2>

          <p class="contact-desc">
            Konsultasikan kebutuhan website dan aplikasi bisnis Anda sekarang bersama tim teknis kami secara langsung. Diskusi bebas biaya dan tanpa komitmen awal.
          </p>

          <div class="official-wa-box">
            <div class="wa-icon-wrapper">
              <svg width="32" height="32" viewBox="0 0 24 24" fill="currentColor">
                <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.501-.669-.51l-.57-.01c-.198 0-.52.074-.792.372s-1.04 1.016-1.04 2.479 1.065 2.876 1.213 3.074c.149.198 2.095 3.2 5.076 4.487.709.306 1.263.489 1.694.626.712.226 1.36.194 1.872.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.473-8.413"/>
              </svg>
            </div>
            <div class="wa-text-group">
              <span class="wa-label">WhatsApp Official Alphatech</span>
              <a href="https://wa.me/6287828690059" target="_blank" rel="noopener noreferrer" class="wa-number">
                +62 878-2869-0059
              </a>
            </div>
          </div>
        </div>

        <!-- Right Side: Fast Quick Form -->
        <div class="contact-form-box">
          <h3 class="form-title">Formulir Diskusi Cepat</h3>
          <form on:submit|preventDefault={handleSubmit} class="quick-form">
            <div class="form-group">
              <label for="name">Nama Lengkap</label>
              <input type="text" id="name" placeholder="Masukkan nama Anda" bind:value={name} required class="form-input" />
            </div>

            <div class="form-group">
              <label for="email">Alamat Email / Kontak</label>
              <input type="text" id="email" placeholder="email@perusahaan.com" bind:value={email} required class="form-input" />
            </div>

            <div class="form-group">
              <label for="service">Layanan yang Diminati</label>
              <select id="service" bind:value={serviceType} class="form-select">
                <option value="Website Profil Perusahaan">Website Profil Perusahaan (Company Profile)</option>
                <option value="Pengembangan Aplikasi Web">Pengembangan Aplikasi Web (Custom Web App)</option>
                <option value="Landing Page Interaktif">Landing Page Interaktif & Pemasaran Digital</option>
                <option value="Pemeliharaan System">Pemeliharaan & Optimasi System (Web Maintenance)</option>
              </select>
            </div>

            <div class="form-group">
              <label for="msg">Pesan / Gambaran Singkat</label>
              <textarea id="msg" placeholder="Tuliskan kebutuhan atau pertanyaan Anda..." bind:value={message} rows="3" class="form-textarea"></textarea>
            </div>

            <button type="submit" class="btn btn-whatsapp btn-full">
              <span>Hubungi via WhatsApp Cepat</span>
              <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M5 12h14M12 5l7 7-7 7"/>
              </svg>
            </button>
          </form>
        </div>
      </div>
    </div>
  </div>
</section>

<style>
  .contact-section {
    position: relative;
    padding: 6rem 0;
  }

  .cta-glow {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 600px;
    height: 350px;
    background: radial-gradient(circle, rgba(0, 242, 254, 0.15) 0%, rgba(138, 43, 226, 0.1) 60%, transparent 80%);
    filter: blur(80px);
    pointer-events: none;
  }

  .contact-main-card {
    padding: 3.5rem;
    background: var(--bg-card);
    border: 1px solid var(--border-highlight);
    box-shadow: var(--shadow-glow);
  }

  .contact-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 3.5rem;
    align-items: center;
  }

  .contact-badge {
    margin-bottom: 1.5rem;
  }

  .contact-title {
    font-size: 2.25rem;
    margin-bottom: 1.25rem;
    line-height: 1.2;
  }

  .contact-desc {
    color: var(--text-muted);
    font-size: 1.05rem;
    line-height: 1.7;
    margin-bottom: 2.5rem;
  }

  .official-wa-box {
    display: flex;
    align-items: center;
    gap: 1.25rem;
    padding: 1.25rem 1.5rem;
    background: rgba(37, 211, 102, 0.08);
    border: 1px solid rgba(37, 211, 102, 0.3);
    border-radius: var(--radius-md);
  }

  .wa-icon-wrapper {
    color: #25D366;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .wa-text-group {
    display: flex;
    flex-direction: column;
  }

  .wa-label {
    font-size: 0.8rem;
    color: var(--text-muted);
    font-weight: 600;
  }

  .wa-number {
    font-family: var(--font-heading);
    font-size: 1.35rem;
    font-weight: 800;
    color: #25D366;
    text-decoration: none;
  }

  .wa-number:hover {
    text-decoration: underline;
  }

  .contact-form-box {
    background: var(--bg-dark-surface);
    border: 1px solid var(--border-subtle);
    border-radius: var(--radius-md);
    padding: 2rem;
  }

  .form-title {
    font-size: 1.25rem;
    color: var(--text-main);
    margin-bottom: 1.5rem;
  }

  .quick-form {
    display: flex;
    flex-direction: column;
    gap: 1.25rem;
  }

  .form-group {
    display: flex;
    flex-direction: column;
    gap: 0.4rem;
  }

  .form-group label {
    font-size: 0.85rem;
    font-weight: 600;
    color: var(--text-muted);
  }

  .form-select, .form-input, .form-textarea {
    width: 100%;
    padding: 0.85rem 1.1rem;
    background: var(--bg-card);
    border: 1px solid var(--border-subtle);
    border-radius: var(--radius-sm);
    color: var(--text-main);
    font-family: var(--font-primary);
    font-size: 0.9rem;
    outline: none;
    transition: border-color var(--transition-fast);
  }

  .form-textarea {
    resize: none;
  }

  .form-input:focus, .form-textarea:focus, .form-select:focus {
    border-color: var(--accent-cyan);
  }

  @media (max-width: 900px) {
    .contact-grid {
      grid-template-columns: 1fr;
    }

    .contact-main-card {
      padding: 2rem;
    }
  }
</style>
