<script>
  let showTooltip = false;
</script>

<div class="floating-wa-container">
  {#if showTooltip}
    <div class="wa-tooltip">
      <div class="tooltip-header">
        <span class="online-indicator"></span>
        <strong>Tim Teknis Alphatech</strong>
      </div>
      <p>Halo! Ada yang bisa kami bantu mengenai pembuatan website & aplikasi web?</p>
    </div>
  {/if}

  <a 
    href="https://wa.me/6287828690059?text=Halo%20Alphatech,%20saya%20tertarik%20untuk%20konsultasi%20pembuatan%20website%2Faplikasi%20web." 
    target="_blank" 
    rel="noopener noreferrer" 
    class="floating-wa-btn"
    aria-label="Direct WhatsApp Chat"
    on:mouseenter={() => showTooltip = true}
    on:mouseleave={() => showTooltip = false}
  >
    <svg width="28" height="28" viewBox="0 0 24 24" fill="currentColor">
      <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.501-.669-.51l-.57-.01c-.198 0-.52.074-.792.372s-1.04 1.016-1.04 2.479 1.065 2.876 1.213 3.074c.149.198 2.095 3.2 5.076 4.487.709.306 1.263.489 1.694.626.712.226 1.36.194 1.872.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.473-8.413"/>
    </svg>
    <span class="online-dot"></span>
  </a>
</div>

<style>
  .floating-wa-container {
    position: fixed;
    bottom: 2rem;
    right: 2rem;
    z-index: 999;
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    gap: 0.75rem;
  }

  .floating-wa-btn {
    width: 60px;
    height: 60px;
    border-radius: 50%;
    background: linear-gradient(135deg, #25D366 0%, #128C7E 100%);
    color: #FFFFFF;
    display: flex;
    align-items: center;
    justify-content: center;
    box-shadow: 0 8px 30px rgba(37, 211, 102, 0.4);
    text-decoration: none;
    position: relative;
    transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  }

  .floating-wa-btn:hover {
    transform: scale(1.1);
    box-shadow: 0 12px 35px rgba(37, 211, 102, 0.6);
  }

  .online-dot {
    position: absolute;
    top: 2px;
    right: 2px;
    width: 14px;
    height: 14px;
    border-radius: 50%;
    background: #10B981;
    border: 2px solid var(--bg-dark);
    box-shadow: 0 0 10px #10B981;
  }

  .wa-tooltip {
    background: var(--bg-dark-surface);
    border: 1px solid var(--border-highlight);
    border-radius: var(--radius-md);
    padding: 1rem;
    width: 260px;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
    animation: fadeIn 0.2s ease-in-out;
  }

  @keyframes fadeIn {
    from { opacity: 0; transform: translateY(5px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .tooltip-header {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    margin-bottom: 0.4rem;
    font-size: 0.85rem;
  }

  .online-indicator {
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background: #10B981;
  }

  .wa-tooltip p {
    font-size: 0.825rem;
    color: var(--text-muted);
    margin: 0;
  }
</style>
