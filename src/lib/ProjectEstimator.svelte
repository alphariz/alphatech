<script>
  let selectedService = 'company-profile';
  let selectedFeatures = ['seo-basic', 'responsive-ui'];
  let clientName = '';
  let companyName = '';
  let projectNotes = '';

  const serviceOptions = [
    { id: 'company-profile', title: 'Website Profil Perusahaan', estTime: '5-10 Hari Kerja' },
    { id: 'custom-web-app', title: 'Custom Web Application', estTime: '14-30 Hari Kerja' },
    { id: 'landing-page', title: 'Landing Page High Conversion', estTime: '3-7 Hari Kerja' },
    { id: 'maintenance', title: 'Web Maintenance & Support', estTime: 'Layanan Berkala' }
  ];

  const featureOptions = [
    { id: 'responsive-ui', title: 'Desain Adaptive & Mobile First' },
    { id: 'seo-basic', title: 'Optimasi SEO & Index Google' },
    { id: 'admin-dashboard', title: 'Panel Admin / CMS Kustom' },
    { id: 'payment-gateway', title: 'Integrasi Payment Gateway' },
    { id: 'multi-lang', title: 'Dukungan Multi-Bahasa' },
    { id: 'fast-track', title: 'Peluncuran Prioritas (Fast-Track)' }
  ];

  function toggleFeature(id) {
    if (selectedFeatures.includes(id)) {
      selectedFeatures = selectedFeatures.filter(f => f !== id);
    } else {
      selectedFeatures = [...selectedFeatures, id];
    }
  }

  $: waLink = generateWaLink(selectedService, selectedFeatures, clientName, companyName, projectNotes);

  function generateWaLink(serviceId, featIds, name, company, notes) {
    const serviceObj = serviceOptions.find(s => s.id === serviceId);
    const serviceTitle = serviceObj ? serviceObj.title : 'Pengembangan Web';

    const selectedFeatTitles = featureOptions
      .filter(f => featIds.includes(f.id))
      .map(f => `• ${f.title}`);

    let text = `Halo Alphatech, saya ingin berkonsultasi mengenai rencana proyek digital berikut:\n\n`;
    if (name) text += `👤 *Nama:* ${name}\n`;
    if (company) text += `🏢 *Perusahaan/Usaha:* ${company}\n`;
    text += `📌 *Jenis Layanan:* ${serviceTitle}\n`;
    
    if (selectedFeatTitles.length > 0) {
      text += `⚡ *Fitur/Kebutuhan Khusus:*\n${selectedFeatTitles.join('\n')}\n`;
    }

    if (notes) text += `📝 *Catatan Tambahan:* ${notes}\n`;

    text += `\nMohon informasi estimasi waktu dan langkah konsultasi selanjutnya. Terima kasih!`;

    return `https://wa.me/6287828690059?text=${encodeURIComponent(text)}`;
  }
</script>

<section id="estimasi" class="estimator-section">
  <div class="container">
    <div class="section-header">
      <div class="badge">Simulasi & Kalkulator Proyek</div>
      <h2>Rencanakan Spesifikasi <span class="text-gradient">Proyek Web Anda</span></h2>
      <p>
        Pilih jenis layanan dan fitur yang Anda butuhkan untuk langsung terhubung dengan tim teknis Alphatech via WhatsApp.
      </p>
    </div>

    <div class="glass-card estimator-card">
      <div class="estimator-grid">
        <!-- Input Form Options -->
        <div class="estimator-left">
          <!-- Step 1: Select Service -->
          <div class="form-group-step">
            <p class="step-label">1. Pilih Jenis Layanan Utama</p>
            <div class="service-selector-grid">
              {#each serviceOptions as s}
                <button 
                  type="button"
                  class="service-select-btn {selectedService === s.id ? 'active' : ''}"
                  on:click={() => selectedService = s.id}
                >
                  <span class="btn-check">{selectedService === s.id ? '✓' : ''}</span>
                  <div class="btn-text-content">
                    <strong>{s.title}</strong>
                    <small>Estimasi: {s.estTime}</small>
                  </div>
                </button>
              {/each}
            </div>
          </div>

          <!-- Step 2: Select Features -->
          <div class="form-group-step">
            <p class="step-label">2. Pilih Fitur &amp; Spesifikasi Tambahan</p>
            <div class="features-checkbox-grid">
              {#each featureOptions as f}
                <button
                  type="button"
                  class="feature-check-btn {selectedFeatures.includes(f.id) ? 'active' : ''}"
                  on:click={() => toggleFeature(f.id)}
                >
                  <span class="check-box">{selectedFeatures.includes(f.id) ? '✓' : ''}</span>
                  <span>{f.title}</span>
                </button>
              {/each}
            </div>
          </div>

          <!-- Step 3: Identity & Notes -->
          <div class="form-group-step">
            <p class="step-label">3. Data Kontak &amp; Catatan Singkat (Opsional)</p>
            <div class="input-row">
              <input 
                type="text" 
                placeholder="Nama Anda" 
                bind:value={clientName} 
                class="form-input"
              />
              <input 
                type="text" 
                placeholder="Nama Perusahaan / Bisnis" 
                bind:value={companyName} 
                class="form-input"
              />
            </div>
            <textarea 
              placeholder="Catatan khusus atau gambaran singkat proyek Anda..." 
              bind:value={projectNotes}
              rows="3"
              class="form-textarea"
            ></textarea>
          </div>
        </div>

        <!-- Summary & Instant Dispatch Card -->
        <div class="estimator-right">
          <div class="glass-card summary-card">
            <div class="summary-header">
              <span class="summary-icon">📲</span>
              <h3>Ringkasan Konsultasi</h3>
            </div>

            <div class="summary-content">
              <div class="summary-row">
                <span class="row-label">Layanan:</span>
                <span class="row-value highlight">
                  {serviceOptions.find(s => s.id === selectedService)?.title}
                </span>
              </div>

              <div class="summary-row">
                <span class="row-label">Jumlah Fitur:</span>
                <span class="row-value">{selectedFeatures.length} Spesifikasi Dipilih</span>
              </div>

              <div class="summary-row">
                <span class="row-label">Kontak Resmi:</span>
                <span class="row-value">+62 878-2869-0059</span>
              </div>

              <div class="summary-divider"></div>

              <p class="summary-note">
                Sistem kami akan membuat draf pesan WhatsApp berisi semua pilihan spesifikasi Anda untuk langsung didiskusikan dengan tim Alphatech.
              </p>

              <a 
                href={waLink} 
                target="_blank" 
                rel="noopener noreferrer" 
                class="btn btn-whatsapp btn-full btn-lg"
              >
                <svg width="22" height="22" viewBox="0 0 24 24" fill="currentColor">
                  <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.501-.669-.51l-.57-.01c-.198 0-.52.074-.792.372s-1.04 1.016-1.04 2.479 1.065 2.876 1.213 3.074c.149.198 2.095 3.2 5.076 4.487.709.306 1.263.489 1.694.626.712.226 1.36.194 1.872.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.473-8.413"/>
                </svg>
                <span>Kirim Konsultasi ke WA</span>
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<style>
  .estimator-section {
    background: var(--bg-dark-surface);
  }

  .estimator-card {
    padding: 3rem;
  }

  .estimator-grid {
    display: grid;
    grid-template-columns: 1.3fr 0.7fr;
    gap: 3rem;
    align-items: stretch;
  }

  .form-group-step {
    margin-bottom: 2rem;
  }

  .step-label {
    display: block;
    font-size: 1rem;
    font-weight: 700;
    color: var(--text-main);
    margin-bottom: 1rem;
  }

  .service-selector-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1rem;
  }

  .service-select-btn {
    display: flex;
    align-items: flex-start;
    gap: 0.75rem;
    padding: 1rem;
    background: var(--bg-dark-surface);
    border: 1px solid var(--border-subtle);
    border-radius: var(--radius-sm);
    cursor: pointer;
    text-align: left;
    transition: all var(--transition-fast);
    color: var(--text-main);
  }

  .service-select-btn:hover {
    border-color: rgba(0, 242, 254, 0.3);
  }

  .service-select-btn.active {
    background: rgba(0, 242, 254, 0.08);
    border-color: var(--accent-cyan);
    box-shadow: 0 0 15px rgba(0, 242, 254, 0.15);
  }

  .btn-check {
    width: 20px;
    height: 20px;
    border-radius: 50%;
    border: 1px solid var(--border-subtle);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.75rem;
    color: var(--accent-cyan);
    font-weight: bold;
    flex-shrink: 0;
  }

  .service-select-btn.active .btn-check {
    background: var(--accent-cyan);
    color: #000;
    border-color: var(--accent-cyan);
  }

  .btn-text-content strong {
    display: block;
    font-size: 0.9rem;
    line-height: 1.3;
  }

  .btn-text-content small {
    font-size: 0.75rem;
    color: var(--text-muted);
  }

  .features-checkbox-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 0.75rem;
  }

  .feature-check-btn {
    display: flex;
    align-items: center;
    gap: 0.6rem;
    padding: 0.75rem 1rem;
    background: var(--bg-dark-surface);
    border: 1px solid var(--border-subtle);
    border-radius: var(--radius-sm);
    color: var(--text-muted);
    font-size: 0.85rem;
    cursor: pointer;
    text-align: left;
    transition: all var(--transition-fast);
  }

  .feature-check-btn.active {
    background: rgba(0, 242, 254, 0.08);
    border-color: var(--accent-cyan);
    color: var(--text-main);
    font-weight: 600;
  }

  .check-box {
    width: 16px;
    height: 16px;
    border-radius: 4px;
    border: 1px solid var(--border-subtle);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.7rem;
    color: var(--accent-cyan);
    flex-shrink: 0;
  }

  .feature-check-btn.active .check-box {
    background: var(--accent-cyan);
    color: #000;
  }

  .input-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1rem;
    margin-bottom: 1rem;
  }

  .form-input, .form-textarea {
    width: 100%;
    padding: 0.85rem 1.1rem;
    background: var(--bg-dark-surface);
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

  .form-input:focus, .form-textarea:focus {
    border-color: var(--accent-cyan);
  }

  /* Summary Card Right */
  .summary-card {
    padding: 2rem;
    background: var(--bg-card);
    border: 1px solid var(--border-highlight);
    box-shadow: var(--shadow-glow);
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    height: 100%;
  }

  .summary-header {
    display: flex;
    align-items: center;
    gap: 0.75rem;
    margin-bottom: 1.5rem;
    padding-bottom: 1rem;
    border-bottom: 1px solid var(--border-subtle);
  }

  .summary-header h3 {
    font-size: 1.2rem;
    color: var(--text-main);
  }

  .summary-row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 1rem;
    font-size: 0.9rem;
  }

  .row-label {
    color: var(--text-muted);
  }

  .row-value {
    font-weight: 600;
    color: var(--text-main);
  }

  .row-value.highlight {
    color: var(--accent-cyan);
  }

  .summary-divider {
    height: 1px;
    background: var(--border-subtle);
    margin: 1.5rem 0;
  }

  .summary-note {
    font-size: 0.825rem;
    color: var(--text-muted);
    line-height: 1.5;
    margin-bottom: 1.5rem;
  }

  .btn-lg {
    padding: 1rem;
    font-size: 1rem;
  }

  @media (max-width: 1024px) {
    .estimator-grid {
      grid-template-columns: 1fr;
    }

    .service-selector-grid, .features-checkbox-grid, .input-row {
      grid-template-columns: 1fr;
    }
  }
</style>
