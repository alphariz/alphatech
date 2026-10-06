<script>
  import { fly } from 'svelte/transition';

  let activeStep = $state(0);
  const totalSteps = 7;

  const steps = [
    {
      stepNum: 1,
      title: 'Analisis Kebutuhan & Perencanaan Proyek',
      short: 'Analisis',
      icon: '📋',
      color: '#00F2FE',
      duration: '1–3 Hari Kerja',
      status: 'Discovery Phase',
      desc: 'Sesi diskusi mendalam bersama klien untuk memahami latar belakang bisnis, alur operasional, target pengguna (user persona), serta spesifikasi teknis dan fungsional sistem yang dibutuhkan secara komprehensif.',
      activities: [
        'Wawancara kebutuhan bisnis & teknis (briefing awal)',
        'Identifikasi target pengguna dan use case utama',
        'Benchmarking kompetitor & referensi desain',
        'Penyusunan ruang lingkup proyek (project scope)',
        'Estimasi biaya, sumber daya, dan jadwal pengerjaan'
      ],
      deliverables: [
        'Dokumen System Requirement Specification (SRS)',
        'Pemetaan Flowchart Bisnis & User Journey',
        'Penetapan Tech Stack & Arsitektur Sistem',
        'Project Timeline & Milestone Agreement'
      ]
    },
    {
      stepNum: 2,
      title: 'Perancangan Antarmuka (UI/UX Design)',
      short: 'UI/UX',
      icon: '🎨',
      color: '#818CF8',
      duration: '2–5 Hari Kerja',
      status: 'Design Phase',
      desc: 'Penyusunan tata letak (layout), skema warna, sistem tipografi, dan alur interaksi pengguna yang intuitif, estetis, dan responsif. Seluruh desain dipresentasikan dalam bentuk prototype high-fidelity sebelum pengodean dimulai.',
      activities: [
        'Pembuatan wireframe & sitemap halaman',
        'Perancangan mockup visual antarmuka (UI) high-fidelity',
        'Prototype interaktif & simulasi alur navigasi',
        'Penyusunan design system (warna, tipografi, komponen)',
        'Revisi desain berdasarkan feedback klien'
      ],
      deliverables: [
        'Wireframe & Sitemap Halaman Lengkap',
        'Mockup Desain Visual High-Fidelity',
        'Interactive Prototype (Figma/Adobe XD)',
        'Design System & Brand Color Palette'
      ]
    },
    {
      stepNum: 3,
      title: 'Pengembangan & Pengodean (Development)',
      short: 'Development',
      icon: '💻',
      color: '#4FACFE',
      duration: '5–20 Hari Kerja',
      status: 'Build Phase',
      desc: 'Fase inti pengodean frontend dan backend menggunakan standar arsitektur perangkat lunak modern. Pengembangan dilakukan secara iteratif dengan laporan progres berkala kepada klien agar output sesuai ekspektasi.',
      activities: [
        'Setup environment, repo, dan arsitektur proyek',
        'Pengembangan antarmuka frontend (HTML, CSS, JS/Framework)',
        'Pengembangan logic backend & struktur database',
        'Implementasi enkripsi keamanan & access control',
        'Integrasi API third-party (payment, maps, notification, dll)',
        'Laporan progres mingguan kepada klien'
      ],
      deliverables: [
        'Codebase Frontend Responsive & Cross-Browser',
        'Backend API & Struktur Database Teroptimasi',
        'Sistem Autentikasi & Manajemen Hak Akses',
        'Integrasi Third-Party API & Service'
      ]
    },
    {
      stepNum: 4,
      title: 'Pengujian Kualitas (QA & Testing)',
      short: 'QA Testing',
      icon: '🔍',
      color: '#F59E0B',
      duration: '2–5 Hari Kerja',
      status: 'Testing Phase',
      desc: 'Pengujian menyeluruh terhadap seluruh fitur, performa kecepatan, responsivitas di berbagai perangkat dan browser, serta ketahanan sistem terhadap potensi celah keamanan siber sebelum diluncurkan ke publik.',
      activities: [
        'Functional testing seluruh fitur & modul sistem',
        'Cross-browser & responsive device testing',
        'Performance & speed audit (Lighthouse, GTmetrix)',
        'Stress testing & load capacity analysis',
        'Security vulnerability scanning & penetration test dasar',
        'User acceptance testing (UAT) bersama klien'
      ],
      deliverables: [
        'Laporan Hasil QA Testing Lengkap',
        'Performance Audit Report (Lighthouse Score)',
        'Bug Fix & Security Patch Documentation',
        'Checklist UAT (User Acceptance Testing) Tersertifikasi'
      ]
    },
    {
      stepNum: 5,
      title: 'Serah Terima & Peluncuran (Go-Live)',
      short: 'Go-Live',
      icon: '🚀',
      color: '#10B981',
      duration: '1–3 Hari Kerja',
      status: 'Deployment Phase',
      desc: 'Proses migrasi sistem dari lingkungan pengembangan (staging) ke server/domain produksi utama. Dilengkapi dengan setup keamanan server, aktivasi SSL, dan serah terima resmi kepada klien.',
      activities: [
        'Konfigurasi domain, DNS, dan server produksi',
        'Deployment sistem ke server & aktivasi SSL Certificate',
        'Setup CDN, caching, dan optimasi server performa',
        'Aktivasi sistem monitoring uptime & error logging',
        'Final review & konfirmasi sistem berjalan optimal',
        'Serah terima resmi sistem kepada klien'
      ],
      deliverables: [
        'Sistem Live di Domain Produksi',
        'SSL Certificate Aktif & Domain Terverifikasi',
        'Konfigurasi Server & CDN Dokumentasi',
        'Akses Panel Admin & Credential Diserahkan ke Klien'
      ]
    },
    {
      stepNum: 6,
      title: 'Pelatihan & Onboarding Tim Klien',
      short: 'Training',
      icon: '🎓',
      color: '#A855F7',
      duration: '1–2 Hari Kerja',
      status: 'Handover Phase',
      desc: 'Sesi pelatihan terstruktur kepada tim internal klien untuk memastikan seluruh pengguna sistem (admin, operator, manajemen) dapat mengoperasikan platform secara mandiri, efisien, dan aman.',
      activities: [
        'Pelatihan penggunaan panel admin & manajemen konten',
        'Workshop fitur-fitur inti & alur kerja sistem',
        'Simulasi skenario operasional sehari-hari',
        'Tanya jawab teknis & troubleshooting dasar',
        'Penyerahan dokumentasi & panduan pengguna resmi'
      ],
      deliverables: [
        'User Manual & Panduan Penggunaan Sistem (PDF)',
        'Video Tutorial Penggunaan Fitur Utama',
        'Technical Documentation & API Reference',
        'Sertifikat Serah Terima Proyek Resmi'
      ]
    },
    {
      stepNum: 7,
      title: 'Pemeliharaan & Dukungan Berkelanjutan (Maintenance)',
      short: 'Maintenance',
      icon: '🛡️',
      color: '#F43F5E',
      duration: 'Layanan Berkelanjutan',
      status: 'Post-Launch Phase',
      desc: 'Layanan purna jual pasca peluncuran yang memastikan sistem terus berjalan optimal, aman, dan terkini. Mencakup pembaruan berkala, penanganan bug, monitoring sistem 24/7, serta dukungan teknis responsif.',
      activities: [
        'Monitoring uptime & kesehatan server 24/7',
        'Pembaruan sistem, patch keamanan, & dependency update',
        'Pencadangan (backup) data terjadwal & otomatis',
        'Penanganan bug, error, dan gangguan teknis',
        'Optimasi performa berkala & cache management',
        'Laporan kesehatan sistem & analitik bulanan'
      ],
      deliverables: [
        'Laporan Monitoring & Uptime Bulanan',
        'Backup Data Otomatis & Terjadwal',
        'Patch Log & Security Update Record',
        'Helpdesk Support 24/7 via WhatsApp/Email'
      ]
    }
  ];

  let isLastStep = $derived(activeStep === totalSteps - 1);
  let current = $derived(steps[activeStep]);

  function goNext() {
    if (activeStep < totalSteps - 1) activeStep += 1;
  }

  function goPrev() {
    if (activeStep > 0) activeStep -= 1;
  }

  function goTo(idx) {
    activeStep = idx;
  }
</script>

<section id="alur-kerja" class="process-section">
  <div class="container">
    <div class="section-header">
      <div class="badge">Alur Kerja</div>
      <h2>Tahapan Pengembangan <span class="text-gradient">Proyek — End to End</span></h2>
      <p>
        Tujuh fase pengerjaan yang terstruktur, transparan, dan sistematis — dari konsultasi awal hingga dukungan purna jual berkelanjutan.
      </p>
    </div>

    <!-- Stepper Navigation Tabs -->
    <div class="stepper-nav-scroll-wrapper">
      <div class="stepper-nav">
        {#each steps as step, idx}
          <button
            type="button"
            class="step-nav-btn {activeStep === idx ? 'active' : ''} {idx < activeStep ? 'completed' : ''}"
            onclick={() => goTo(idx)}
            style={activeStep === idx ? `--step-color: ${step.color}` : ''}
          >
            <div
              class="step-circle"
              style={
                activeStep === idx
                  ? `background: ${step.color}; border-color: ${step.color}; box-shadow: 0 0 18px ${step.color}60; color: #000`
                  : idx < activeStep
                  ? `border-color: ${step.color}60; color: ${step.color}`
                  : ''
              }
            >
              {#if idx < activeStep}
                <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3">
                  <polyline points="20 6 9 17 4 12"/>
                </svg>
              {:else}
                {step.stepNum}
              {/if}
            </div>
            <span
              class="step-nav-title"
              style={activeStep === idx ? `color: ${step.color}` : idx < activeStep ? 'color: var(--text-muted)' : ''}
            >{step.short}</span>
          </button>
        {/each}
      </div>
    </div>

    <!-- Main Step Detail Card -->
    <div class="glass-card process-detail-card" style="--step-accent: {current.color}">
      {#key activeStep}
        <div
          class="process-card-grid"
          in:fly={{ x: 30, duration: 280, opacity: 0 }}
        >
          <!-- LEFT: Step Information -->
          <div class="process-left">
            <div class="step-header-row">
              <div
                class="step-tag-pill"
                style="background: {current.color}15; border-color: {current.color}40; color: {current.color}"
              >
                <span class="step-icon">{current.icon}</span>
                <span>Tahap {current.stepNum} dari {totalSteps} — {current.status}</span>
              </div>
              <div class="step-duration-badge">
                <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/>
                </svg>
                <span>{current.duration}</span>
              </div>
            </div>

            <h3 class="step-main-title">{current.title}</h3>
            <p class="step-main-desc">{current.desc}</p>

            <!-- Activities -->
            <div class="step-activities">
              <h4>
                <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <path d="M9 11l3 3L22 4"/>
                  <path d="M21 12v7a2 2 0 01-2 2H5a2 2 0 01-2-2V5a2 2 0 012-2h11"/>
                </svg>
                Aktivitas dalam Fase Ini:
              </h4>
              <ul>
                {#each current.activities as activity, i}
                  <li style="animation-delay: {i * 0.06}s">
                    <span
                      class="activity-num"
                      style="background: {current.color}15; color: {current.color}; border-color: {current.color}30"
                    >{i + 1}</span>
                    <span>{activity}</span>
                  </li>
                {/each}
              </ul>
            </div>
          </div>

          <!-- RIGHT: Deliverables + Visual -->
          <div class="process-right">
            <!-- Visual Status Box -->
            <div
              class="workflow-visual-box"
              style="border-color: {current.color}30; background: {current.color}06"
            >
              <div class="workflow-status-bar" style="background: {current.color}18; color: {current.color}">
                <span class="pulse-dot" style="background: {current.color}; box-shadow: 0 0 8px {current.color}"></span>
                <span>{current.status.toUpperCase()}</span>
              </div>
              <div class="big-step-icon">{current.icon}</div>
              <div
                class="big-step-num"
                style="background: linear-gradient(135deg, {current.color}, {steps[Math.max(0, activeStep - 1)].color}); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text"
              >
                {String(current.stepNum).padStart(2, '0')}
              </div>
              <div class="step-name-badge">{current.short} Phase</div>
            </div>

            <!-- Deliverables List -->
            <div class="step-deliverables-box">
              <h4>
                <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <path d="M21 15v4a2 2 0 01-2 2H5a2 2 0 01-2-2v-4"/>
                  <polyline points="7 10 12 15 17 10"/>
                  <line x1="12" y1="15" x2="12" y2="3"/>
                </svg>
                Deliverables & Hasil Akhir:
              </h4>
              <ul class="deliverables-list">
                {#each current.deliverables as deliv}
                  <li>
                    <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="{current.color}" stroke-width="2.5">
                      <polyline points="20 6 9 17 4 12"/>
                    </svg>
                    <span>{deliv}</span>
                  </li>
                {/each}
              </ul>
            </div>
          </div>
        </div>
      {/key}

      <!-- Navigation Controls -->
      <div class="step-nav-controls">
        <button
          type="button"
          class="nav-ctrl-btn prev-btn"
          onclick={goPrev}
          disabled={activeStep === 0}
        >
          <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <path d="M19 12H5M12 19l-7-7 7-7"/>
          </svg>
          <span>Tahap Sebelumnya</span>
        </button>

        <div class="step-pagination-dots">
          {#each steps as step, idx}
            <button
              type="button"
              class="pagination-dot {idx === activeStep ? 'active' : ''} {idx < activeStep ? 'done' : ''}"
              style={idx === activeStep ? `background: ${step.color}` : idx < activeStep ? `background: ${step.color}60` : ''}
              onclick={() => goTo(idx)}
              aria-label="Tahap {step.stepNum}: {step.short}"
            ></button>
          {/each}
        </div>

        {#if isLastStep}
          <a
            href="https://wa.me/6287828690059?text=Halo%20Alphatech,%20saya%20ingin%20memulai%20konsultasi%20proyek%20pengembangan%20website%2Faplikasi%20web."
            target="_blank"
            rel="noopener noreferrer"
            class="nav-ctrl-btn cta-btn"
          >
            <span>Mulai Proyek Sekarang</span>
            <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor">
              <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.501-.669-.51l-.57-.01c-.198 0-.52.074-.792.372s-1.04 1.016-1.04 2.479 1.065 2.876 1.213 3.074c.149.198 2.095 3.2 5.076 4.487.709.306 1.263.489 1.694.626.712.226 1.36.194 1.872.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.473-8.413"/>
            </svg>
          </a>
        {:else}
          <button
            type="button"
            class="nav-ctrl-btn next-btn"
            onclick={goNext}
            style="background: {current.color}20; border-color: {current.color}50; color: {current.color}"
          >
            <span>Tahap Berikutnya</span>
            <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
              <path d="M5 12h14M12 5l7 7-7 7"/>
            </svg>
          </button>
        {/if}
      </div>
    </div>
  </div>
</section>

<style>
  .process-section {
    background: var(--bg-dark);
  }

  .stepper-nav-scroll-wrapper {
    overflow-x: auto;
    margin-bottom: 2rem;
    padding-bottom: 0.5rem;
  }

  .stepper-nav {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    gap: 0.5rem;
    min-width: 700px;
    position: relative;
    padding: 0.5rem 1rem 0.5rem;
  }

  .stepper-nav::before {
    content: '';
    position: absolute;
    top: 32px;
    left: 60px;
    right: 60px;
    height: 2px;
    background: var(--border-subtle);
    z-index: 1;
  }

  .step-nav-btn {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0.6rem;
    background: none;
    border: none;
    cursor: pointer;
    position: relative;
    z-index: 2;
    flex: 1;
    padding: 0;
    min-width: 80px;
    transition: transform var(--transition-fast);
  }

  .step-nav-btn:hover {
    transform: translateY(-2px);
  }

  .step-circle {
    width: 48px;
    height: 48px;
    border-radius: 50%;
    background: var(--bg-dark-surface);
    border: 2px solid var(--border-subtle);
    color: var(--text-muted);
    font-family: var(--font-heading);
    font-size: 1.05rem;
    font-weight: 700;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all var(--transition-smooth);
  }

  .step-nav-btn.active .step-circle {
    transform: scale(1.12);
  }

  .step-nav-title {
    font-size: 0.78rem;
    font-weight: 600;
    color: var(--text-subtle);
    transition: color var(--transition-fast);
    text-align: center;
    white-space: nowrap;
  }

  .process-detail-card {
    padding: 2.5rem;
    border-color: color-mix(in srgb, var(--step-accent, var(--accent-cyan)) 25%, var(--border-subtle));
    transition: border-color var(--transition-smooth);
  }

  .process-card-grid {
    display: grid;
    grid-template-columns: 1.25fr 0.75fr;
    gap: 3rem;
    align-items: start;
    margin-bottom: 2.5rem;
  }

  .step-header-row {
    display: flex;
    align-items: center;
    gap: 0.75rem;
    flex-wrap: wrap;
    margin-bottom: 1.25rem;
  }

  .step-tag-pill {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    padding: 0.35rem 0.85rem;
    border-radius: var(--radius-full);
    font-size: 0.8rem;
    font-weight: 600;
    border: 1px solid;
    transition: all var(--transition-fast);
  }

  .step-icon { font-size: 1rem; }

  .step-duration-badge {
    display: inline-flex;
    align-items: center;
    gap: 0.4rem;
    font-size: 0.8rem;
    color: var(--text-muted);
    padding: 0.3rem 0.75rem;
    background: rgba(255,255,255,0.04);
    border: 1px solid var(--border-subtle);
    border-radius: var(--radius-full);
  }

  .step-main-title {
    font-size: 1.7rem;
    color: var(--text-main);
    margin-bottom: 0.85rem;
    line-height: 1.25;
  }

  .step-main-desc {
    font-size: 1rem;
    color: var(--text-muted);
    line-height: 1.72;
    margin-bottom: 2rem;
  }

  .step-activities h4 {
    font-size: 0.925rem;
    color: var(--text-main);
    margin-bottom: 0.9rem;
    display: flex;
    align-items: center;
    gap: 0.5rem;
    text-transform: uppercase;
    letter-spacing: 0.04em;
    font-weight: 700;
  }

  .step-activities ul {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 0.6rem;
  }

  .step-activities li {
    display: flex;
    align-items: flex-start;
    gap: 0.75rem;
    font-size: 0.925rem;
    color: var(--text-muted);
    line-height: 1.5;
    animation: fadeSlideIn 0.3s ease-out both;
  }

  @keyframes fadeSlideIn {
    from { opacity: 0; transform: translateX(-10px); }
    to { opacity: 1; transform: translateX(0); }
  }

  .activity-num {
    min-width: 22px;
    height: 22px;
    border-radius: 50%;
    border: 1px solid;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.7rem;
    font-weight: 700;
    flex-shrink: 0;
    margin-top: 2px;
  }

  .process-right {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
  }

  .workflow-visual-box {
    border: 1px solid;
    border-radius: var(--radius-md);
    padding: 2rem 1.5rem;
    text-align: center;
    transition: all var(--transition-smooth);
  }

  .workflow-status-bar {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    font-size: 0.72rem;
    font-weight: 700;
    letter-spacing: 0.05em;
    padding: 0.3rem 0.8rem;
    border-radius: var(--radius-full);
    margin-bottom: 1.25rem;
  }

  .pulse-dot {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    animation: pulse-dot 1.5s infinite;
  }

  @keyframes pulse-dot {
    0%, 100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.4; transform: scale(1.4); }
  }

  .big-step-icon {
    font-size: 3.5rem;
    margin-bottom: 0.5rem;
  }

  .big-step-num {
    font-family: var(--font-heading);
    font-size: 5.5rem;
    font-weight: 900;
    line-height: 1;
    transition: all var(--transition-smooth);
  }

  .step-name-badge {
    margin-top: 0.75rem;
    font-size: 0.9rem;
    font-weight: 700;
    color: var(--text-main);
  }

  .step-deliverables-box {
    padding: 1.5rem;
    background: rgba(255,255,255,0.02);
    border: 1px solid var(--border-subtle);
    border-radius: var(--radius-md);
  }

  .step-deliverables-box h4 {
    font-size: 0.875rem;
    color: var(--text-main);
    margin-bottom: 0.85rem;
    display: flex;
    align-items: center;
    gap: 0.5rem;
    text-transform: uppercase;
    letter-spacing: 0.04em;
    font-weight: 700;
  }

  .deliverables-list {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 0.55rem;
  }

  .deliverables-list li {
    display: flex;
    align-items: flex-start;
    gap: 0.5rem;
    font-size: 0.875rem;
    color: var(--text-muted);
    line-height: 1.45;
  }

  .deliverables-list svg {
    flex-shrink: 0;
    margin-top: 2px;
  }

  .step-nav-controls {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 1rem;
    padding-top: 2rem;
    border-top: 1px solid var(--border-subtle);
    flex-wrap: wrap;
  }

  .nav-ctrl-btn {
    display: inline-flex;
    align-items: center;
    gap: 0.6rem;
    padding: 0.75rem 1.5rem;
    border-radius: var(--radius-full);
    font-size: 0.9rem;
    font-weight: 600;
    cursor: pointer;
    transition: all var(--transition-fast);
    border: 1px solid var(--border-subtle);
    background: rgba(255,255,255,0.04);
    color: var(--text-main);
    text-decoration: none;
  }

  .nav-ctrl-btn:disabled {
    opacity: 0.35;
    cursor: not-allowed;
    transform: none !important;
  }

  .nav-ctrl-btn:not(:disabled):hover {
    transform: translateY(-2px);
    background: rgba(255,255,255,0.08);
  }

  .prev-btn { color: var(--text-muted); }

  .next-btn:hover {
    filter: brightness(1.15);
    box-shadow: 0 4px 15px rgba(0,0,0,0.2);
  }

  .cta-btn {
    background: linear-gradient(135deg, #25D366, #128C7E);
    color: #fff;
    border-color: transparent;
    box-shadow: 0 4px 20px rgba(37,211,102,0.35);
  }

  .cta-btn:hover {
    box-shadow: 0 6px 25px rgba(37,211,102,0.5) !important;
    transform: translateY(-2px) !important;
  }

  .step-pagination-dots {
    display: flex;
    align-items: center;
    gap: 0.5rem;
  }

  .pagination-dot {
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background: var(--border-subtle);
    border: none;
    cursor: pointer;
    transition: all var(--transition-fast);
  }

  .pagination-dot.active {
    width: 20px;
    border-radius: 4px;
  }

  .pagination-dot.done { opacity: 0.6; }
  .pagination-dot:hover { transform: scale(1.3); }

  @media (max-width: 1024px) {
    .process-card-grid { grid-template-columns: 1fr; }
    .process-right { flex-direction: row; flex-wrap: wrap; }
    .workflow-visual-box, .step-deliverables-box { flex: 1; min-width: 260px; }
  }

  @media (max-width: 640px) {
    .process-detail-card { padding: 1.5rem; }
    .step-main-title { font-size: 1.35rem; }
    .step-nav-controls { justify-content: center; }
    .process-right { flex-direction: column; }
  }
</style>
