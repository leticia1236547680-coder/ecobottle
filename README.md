<!doctype html>
<html lang="pt-BR" class="h-full">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <script src="https://cdn.jsdelivr.net/npm/lucide@0.263.0/dist/umd/lucide.min.js"></script>
  <script src="/_sdk/element_sdk.js"></script>
  <script src="/_sdk/data_sdk.js"></script>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&amp;family=Inter:wght@300;400;500;600&amp;display=swap" rel="stylesheet">
  <style>
  * { box-sizing: border-box; margin: 0; padding: 0; }
  html, body { height: 100%; }
  body { font-family: 'Poppins', sans-serif; }
  :root { --primary: #e879a3; --secondary: #888888; --bg: #faf9f8; --surface: #ffffff; --text: #2d2d2d; --text-light: #707070; }
  .mobile-frame { width: 100%; max-width: 420px; height: 100%; margin: 0 auto; display: flex; flex-direction: column; background: var(--bg); }
  .screen { flex: 1; overflow-y-auto; display: flex; flex-direction: column; }
  .screen-hidden { display: none; }
  .btn-primary { background: linear-gradient(135deg, var(--primary), #d84e92); color: #fff; border: none; border-radius: 12px; padding: 12px 24px; font-size: 15px; font-weight: 600; cursor: pointer; transition: all 0.3s; }
  .btn-primary:hover { transform: translateY(-2px); box-shadow: 0 8px 24px rgba(232,121,163,0.3); }
  .btn-primary:active { transform: translateY(0); }
  .btn-secondary { background: var(--surface); color: var(--text); border: 2px solid var(--primary); border-radius: 12px; padding: 12px 24px; font-size: 15px; font-weight: 600; cursor: pointer; transition: all 0.3s; }
  .btn-secondary:hover { background: var(--primary); color: #fff; }
  .card { background: var(--surface); border-radius: 16px; padding: 20px; margin-bottom: 16px; box-shadow: 0 2px 8px rgba(0,0,0,0.08); transition: all 0.3s; }
  .card:hover { box-shadow: 0 4px 16px rgba(0,0,0,0.12); }
  .feature-item { display: flex; gap: 16px; margin-bottom: 16px; align-items: flex-start; }
  .feature-icon { width: 48px; height: 48px; background: linear-gradient(135deg, rgba(232,121,163,0.1), rgba(136,136,136,0.1)); border-radius: 12px; display: flex; align-items: center; justify-content: center; flex-shrink: 0; }
  .feature-icon i { color: var(--primary); }
  .question-group { margin-bottom: 24px; }
  .question-label { font-weight: 600; color: var(--text); margin-bottom: 12px; font-size: 15px; }
  .btn-option { background: var(--surface); border: 2px solid #e5e7eb; padding: 12px 16px; border-radius: 10px; cursor: pointer; transition: all 0.2s; font-weight: 500; font-size: 14px; color: var(--text); width: 100%; text-align: left; }
  .btn-option:hover { border-color: var(--primary); background: rgba(16,185,129,0.05); }
  .btn-option.selected { background: var(--primary); color: #fff; border-color: var(--primary); }
  .option-row { display: flex; gap: 12px; }
  .option-row .btn-option { flex: 1; text-align: center; }
  .textarea-input { width: 100%; padding: 12px 16px; border: 2px solid #e5e7eb; border-radius: 10px; font-family: 'Inter', sans-serif; font-size: 14px; resize: vertical; color: var(--text); transition: all 0.2s; }
  .textarea-input:focus { outline: none; border-color: var(--primary); box-shadow: 0 0 0 3px rgba(16,185,129,0.1); }
  .input-field { width: 100%; padding: 12px 16px; border: 2px solid #e5e7eb; border-radius: 10px; font-size: 14px; color: var(--text); font-family: 'Inter', sans-serif; transition: all 0.2s; }
  .input-field:focus { outline: none; border-color: var(--primary); box-shadow: 0 0 0 3px rgba(16,185,129,0.1); }
  .header { padding: 24px 20px 20px; text-align: center; background: linear-gradient(135deg, rgba(232,121,163,0.05), rgba(136,136,136,0.05)); }
  .header h1 { font-size: 28px; font-weight: 700; color: var(--text); margin-bottom: 4px; }
  .header p { font-size: 14px; color: var(--text-light); }
  .water-display { text-align: center; margin: 20px 0; }
  .water-icon { font-size: 48px; margin-bottom: 8px; }
  .water-text { font-size: 24px; font-weight: 700; color: var(--primary); }
  .success-message { text-align: center; padding: 40px 20px; }
  .success-icon { font-size: 64px; margin-bottom: 16px; }
  .success-title { font-size: 24px; font-weight: 700; color: var(--text); margin-bottom: 8px; }
  .success-text { font-size: 15px; color: var(--text-light); line-height: 1.6; }
  .bottle-svg { width: 120px; height: 180px; margin: 20px auto; }
  .header-btn { position: absolute; top: 20px; right: 20px; background: #fff; border: none; width: 40px; height: 40px; border-radius: 10px; display: flex; align-items: center; justify-content: center; cursor: pointer; box-shadow: 0 2px 8px rgba(0,0,0,0.1); transition: all 0.2s; }
  .header-btn:hover { box-shadow: 0 4px 12px rgba(0,0,0,0.15); }
  .scroll-content { flex: 1; overflow-y: auto; padding: 20px; }
  .scroll-content::-webkit-scrollbar { width: 6px; }
  .scroll-content::-webkit-scrollbar-track { background: transparent; }
  .scroll-content::-webkit-scrollbar-thumb { background: #d1d5db; border-radius: 3px; }
  @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
  .fade-in { animation: fadeIn 0.4s ease; }
  @keyframes pulse-tech { 0%, 100% { r: 20; opacity: 0.6; } 50% { r: 22; opacity: 0.8; } }
  .tech-pulse { animation: pulse-tech 2s ease-in-out infinite; }
  </style>
  <style>body { box-sizing: border-box; }</style>
 </head>
 <body style="background: #faf8f6; display: flex; align-items: center; justify-content: center; min-height: 100vh; padding: 10px;">
  <div class="mobile-frame">
   <!-- HOME SCREEN -->
   <div id="screen-home" class="screen fade-in">
    <div class="header">
     <div style="font-size: 32px; margin-bottom: 12px;">
      💧
     </div>
     <h1 id="app-name">EcoBottle Smart</h1>
     <p id="app-slogan">Sua hidratação inteligente e sustentável</p>
    </div>
    <div class="scroll-content">
     <!-- Bottle SVG -->
     <svg class="bottle-svg" viewbox="0 0 140 220" xmlns="http://www.w3.org/2000/svg">
      <defs>
       <lineargradient id="bottleGrad" x1="0%" y1="0%" x2="100%">
        <stop offset="0%" style="stop-color:#ffc9e3;stop-opacity:1" />
        <stop offset="100%" style="stop-color:#ffb3d9;stop-opacity:1" />
       </lineargradient>
       <lineargradient id="handleGrad" x1="0%" y1="0%" x2="100%">
        <stop offset="0%" style="stop-color:#e879a3;stop-opacity:1" />
        <stop offset="100%" style="stop-color:#d84e92;stop-opacity:1" />
       </lineargradient>
       <radialgradient id="techCircle" cx="50%" cy="50%">
        <stop offset="0%" style="stop-color:#e879a3;stop-opacity:0.4" />
        <stop offset="70%" style="stop-color:#e879a3;stop-opacity:0.2" />
        <stop offset="100%" style="stop-color:#e879a3;stop-opacity:0" />
       </radialgradient>
      </defs> <!-- Cup/Caneca body --> <rect x="28" y="50" width="84" height="130" rx="10" fill="url(#bottleGrad)" stroke="#e879a3" stroke-width="2.5" /> <!-- Top rim/borda --> <ellipse cx="70" cy="50" rx="42" ry="8" fill="#e879a3" stroke="#d84e92" stroke-width="1.5" /> <ellipse cx="70" cy="50" rx="40" ry="6" fill="#ffb3d9" opacity="0.8" /> <!-- Handle (alça) --> <path d="M 112 70 Q 135 85 135 125 Q 135 150 112 160" stroke="url(#handleGrad)" stroke-width="5" fill="none" stroke-linecap="round" stroke-linejoin="round" /> <path d="M 112 70 Q 133 84 133 125 Q 133 148 112 158" stroke="#ffffff" stroke-width="2" fill="none" stroke-linecap="round" opacity="0.5" /> <!-- Straw (canudo) --> <rect x="62" y="12" width="16" height="42" rx="4" fill="#d84e92" stroke="#c93d7d" stroke-width="1.5" /> <rect x="65" y="14" width="10" height="38" fill="#ffffff" opacity="0.6" rx="2" /> <ellipse cx="70" cy="12" rx="8" ry="4" fill="#c93d7d" /> <ellipse cx="70" cy="13" rx="6" ry="2" fill="#ffffff" opacity="0.7" /> <!-- Main tech circle (pulsing) --> <circle cx="70" cy="115" r="24" fill="url(#techCircle)" class="tech-pulse" /> <!-- Tech circle rings --> <circle cx="70" cy="115" r="22" fill="none" stroke="#e879a3" stroke-width="2" opacity="0.7" /> <circle cx="70" cy="115" r="18" fill="none" stroke="#e879a3" stroke-width="1.5" opacity="0.5" stroke-dasharray="5 3" /> <!-- Inner tech elements --> <circle cx="70" cy="115" r="14" fill="none" stroke="#e879a3" stroke-width="1" opacity="0.4" /> <circle cx="70" cy="115" r="8" fill="#e879a3" opacity="0.8" /> <circle cx="70" cy="115" r="5" fill="#ffffff" opacity="0.9" /> <!-- Tech dots around circle --> <circle cx="88" cy="115" r="2" fill="#e879a3" opacity="0.6" /> <circle cx="52" cy="115" r="2" fill="#e879a3" opacity="0.6" /> <circle cx="70" cy="97" r="2" fill="#e879a3" opacity="0.6" /> <circle cx="70" cy="133" r="2" fill="#e879a3" opacity="0.6" /> <!-- Water level indicator inside --> <path d="M 32 140 Q 36 143 70 146 Q 104 143 108 140 L 108 170 Q 70 185 32 170 Z" fill="#e879a3" opacity="0.35" /> <!-- Shine effect on water --> <path d="M 40 145 Q 70 148 100 145" stroke="#ffffff" stroke-width="1.5" fill="none" opacity="0.4" stroke-linecap="round" />
     </svg><!-- Water Consumed -->
     <div class="water-display">
      <div class="water-icon">
       💧
      </div>
      <p class="water-text" id="water-consumed">Você bebeu 1,5L hoje</p>
     </div><!-- Action Buttons -->
     <div style="display: flex; gap: 12px; flex-direction: column;">
      <button class="btn-primary" onclick="goToScreen('avaliar')"> ⭐ Avaliar Produto </button> <button class="btn-secondary" onclick="goToScreen('sobre')"> ℹ️ Sobre o Produto </button>
     </div>
    </div>
   </div><!-- ABOUT SCREEN -->
   <div id="screen-sobre" class="screen screen-hidden fade-in">
    <div style="position: relative;">
     <div class="header">
      <h1>Sobre o Produto</h1>
      <p>Conheça as funcionalidades da EcoBottle Smart</p>
     </div><button class="header-btn" onclick="goToScreen('home')">✕</button>
    </div>
    <div class="scroll-content">
     <div class="feature-item">
      <div class="feature-icon"><i data-lucide="activity" style="width: 24px; height: 24px;"></i>
      </div>
      <div>
       <h3 style="color: var(--text); font-weight: 600; margin-bottom: 4px;">Sensor que monitora o consumo</h3>
       <p style="color: var(--text-light); font-size: 14px;">Acompanha em tempo real quantos ml você já bebeu</p>
      </div>
     </div>
     <div class="feature-item">
      <div class="feature-icon"><i data-lucide="smartphone" style="width: 24px; height: 24px;"></i>
      </div>
      <div>
       <h3 style="color: var(--text); font-weight: 600; margin-bottom: 4px;">Conexão com aplicativo</h3>
       <p style="color: var(--text-light); font-size: 14px;">Sincronize com o app do seu celular facilmente</p>
      </div>
     </div>
     <div class="feature-item">
      <div class="feature-icon"><i data-lucide="leaf" style="width: 24px; height: 24px;"></i>
      </div>
      <div>
       <h3 style="color: var(--text); font-weight: 600; margin-bottom: 4px;">Material ecológico</h3>
       <p style="color: var(--text-light); font-size: 14px;">Feita de materiais sustentáveis e reutilizáveis</p>
      </div>
     </div>
     <div class="feature-item">
      <div class="feature-icon"><i data-lucide="zap" style="width: 24px; height: 24px;"></i>
      </div>
      <div>
       <h3 style="color: var(--text); font-weight: 600; margin-bottom: 4px;">Luz LED inteligente</h3>
       <p style="color: var(--text-light); font-size: 14px;">Avisa quando é hora de beber água</p>
      </div>
     </div>
     <div class="feature-item">
      <div class="feature-icon"><i data-lucide="package" style="width: 24px; height: 24px;"></i>
      </div>
      <div>
       <h3 style="color: var(--text); font-weight: 600; margin-bottom: 4px;">Design moderno</h3>
       <p style="color: var(--text-light); font-size: 14px;">Portátil e elegante para seu estilo de vida</p>
      </div>
     </div><button class="btn-primary" style="width: 100%; margin-top: 20px;" onclick="goToScreen('home')">← Voltar</button>
    </div>
   </div><!-- EVALUATION SCREEN -->
   <div id="screen-avaliar" class="screen screen-hidden fade-in">
    <div style="position: relative;">
     <div class="header">
      <h1>Avaliação do Produto</h1>
      <p>Sua opinião é muito importante</p>
     </div><button class="header-btn" onclick="goToScreen('home')">✕</button>
    </div>
    <div class="scroll-content">
     <form id="evaluation-form">
      <!-- Name and Email -->
      <div class="question-group">
       <label class="question-label">Seu Nome</label> <input type="text" class="input-field" id="eval-name" placeholder="Digite seu nome" required>
      </div>
      <div class="question-group">
       <label class="question-label">Seu E-mail</label> <input type="email" class="input-field" id="eval-email" placeholder="seu@email.com" required>
      </div><!-- Q1: Design -->
      <div class="question-group">
       <label class="question-label">1️⃣ O design da garrafa é atraente?</label>
       <div class="option-row">
        <button type="button" class="btn-option" onclick="selectOption(this, 'design_atrativo', 'Sim')">Sim</button> <button type="button" class="btn-option" onclick="selectOption(this, 'design_atrativo', 'Não')">Não</button>
       </div>
      </div><!-- Q2: Sensor -->
      <div class="question-group">
       <label class="question-label">2️⃣ O sensor de consumo funciona bem?</label>
       <div class="option-row">
        <button type="button" class="btn-option" onclick="selectOption(this, 'sensor_funciona', 'Sim')">Sim</button> <button type="button" class="btn-option" onclick="selectOption(this, 'sensor_funciona', 'Às vezes')">Às vezes</button> <button type="button" class="btn-option" onclick="selectOption(this, 'sensor_funciona', 'Não')">Não</button>
       </div>
      </div><!-- Q3: Connection -->
      <div class="question-group">
       <label class="question-label">3️⃣ A conexão com o app é fácil?</label>
       <div class="option-row">
        <button type="button" class="btn-option" onclick="selectOption(this, 'conexao_facil', 'Sim')">Sim</button> <button type="button" class="btn-option" onclick="selectOption(this, 'conexao_facil', 'Difícil')">Difícil</button>
       </div>
      </div><!-- Q4: LED -->
      <div class="question-group">
       <label class="question-label">4️⃣ A luz LED ajuda na hidratação?</label>
       <div class="option-row">
        <button type="button" class="btn-option" onclick="selectOption(this, 'led_ajuda', 'Muito')">Muito</button> <button type="button" class="btn-option" onclick="selectOption(this, 'led_ajuda', 'Pouco')">Pouco</button> <button type="button" class="btn-option" onclick="selectOption(this, 'led_ajuda', 'Não ajuda')">Não ajuda</button>
       </div>
      </div><!-- Q5: Material -->
      <div class="question-group">
       <label class="question-label">5️⃣ O material parece sustentável?</label>
       <div class="option-row">
        <button type="button" class="btn-option" onclick="selectOption(this, 'material_sustentavel', 'Sim')">Sim</button> <button type="button" class="btn-option" onclick="selectOption(this, 'material_sustentavel', 'Não')">Não</button>
       </div>
      </div><!-- Q6: Practical -->
      <div class="question-group">
       <label class="question-label">6️⃣ A garrafa é prática no dia a dia?</label>
       <div class="option-row">
        <button type="button" class="btn-option" onclick="selectOption(this, 'pratico_dia_a_dia', 'Sim')">Sim</button> <button type="button" class="btn-option" onclick="selectOption(this, 'pratico_dia_a_dia', 'Não')">Não</button>
       </div>
      </div><!-- Q7: Difficulties -->
      <div class="question-group">
       <label class="question-label">7️⃣ Você teve dificuldades ao usar?</label>
       <div class="option-row">
        <button type="button" class="btn-option" onclick="selectOption(this, 'dificuldades', 'Sim')">Sim</button> <button type="button" class="btn-option" onclick="selectOption(this, 'dificuldades', 'Não')">Não</button>
       </div>
      </div><!-- Q8: Expectations -->
      <div class="question-group">
       <label class="question-label">8️⃣ O produto atende suas expectativas?</label>
       <div class="option-row">
        <button type="button" class="btn-option" onclick="selectOption(this, 'atende_expectativas', 'Sim')">Sim</button> <button type="button" class="btn-option" onclick="selectOption(this, 'atende_expectativas', 'Parcialmente')">Parcialmente</button> <button type="button" class="btn-option" onclick="selectOption(this, 'atende_expectativas', 'Não')">Não</button>
       </div>
      </div><!-- Q9: What you liked most -->
      <div class="question-group">
       <label class="question-label">9️⃣ O que você mais gostou?</label>
       <div class="option-row">
        <button type="button" class="btn-option" onclick="selectOption(this, 'gostou_mais', 'Design')">Design</button> <button type="button" class="btn-option" onclick="selectOption(this, 'gostou_mais', 'Tecnologia')">Tecnologia</button> <button type="button" class="btn-option" onclick="selectOption(this, 'gostou_mais', 'Sustentabilidade')">Sustentabilidade</button>
       </div>
      </div><!-- Q10: Recommendation -->
      <div class="question-group">
       <label class="question-label">🔟 Você recomendaria o produto?</label>
       <div class="option-row">
        <button type="button" class="btn-option" onclick="selectOption(this, 'recomenda', 'Sim')">Sim</button> <button type="button" class="btn-option" onclick="selectOption(this, 'recomenda', 'Não')">Não</button>
       </div>
      </div><!-- Text fields -->
      <div class="question-group">
       <label class="question-label">💬 Reclamação (Opcional)</label> <textarea class="textarea-input" id="eval-reclamacao" placeholder="Compartilhe sua reclamação aqui..." rows="3"></textarea>
      </div>
      <div class="question-group">
       <label class="question-label">💡 Sugestão (Opcional)</label> <textarea class="textarea-input" id="eval-sugestao" placeholder="Compartilhe uma sugestão aqui..." rows="3"></textarea>
      </div>
      <div class="question-group">
       <label class="question-label">❤️ Elogio (Opcional)</label> <textarea class="textarea-input" id="eval-elogio" placeholder="Compartilhe o que você amou aqui..." rows="3"></textarea>
      </div><!-- Submit Button --> <button type="submit" class="btn-primary" style="width: 100%;"> ✓ Enviar Avaliação </button>
     </form>
    </div>
   </div><!-- SUCCESS SCREEN -->
   <div id="screen-sucesso" class="screen screen-hidden fade-in">
    <div style="display: flex; flex-direction: column; height: 100%; align-items: center; justify-content: center;">
     <div class="success-message">
      <div class="success-icon">
       💚
      </div>
      <h2 class="success-title">Obrigado!</h2>
      <p class="success-text">Sua avaliação foi enviada com sucesso. Você está ajudando a melhorar a EcoBottle Smart.</p><button class="btn-primary" style="margin-top: 30px; width: 100%;" onclick="goToScreen('home')">← Voltar ao Início</button>
     </div>
    </div>
   </div>
  </div>
  <script>
    let formData = {};
    let allEvaluations = [];

    function goToScreen(screenName) {
      document.querySelectorAll('.screen').forEach(s => s.classList.add('screen-hidden'));
      document.getElementById('screen-' + screenName).classList.remove('screen-hidden');
      window.scrollTo(0, 0);
    }

    function selectOption(btn, key, value) {
      const parent = btn.parentElement;
      parent.querySelectorAll('.btn-option').forEach(b => b.classList.remove('selected'));
      btn.classList.add('selected');
      formData[key] = value;
    }

    // Data SDK
    const dataHandler = {
      onDataChanged(data) {
        allEvaluations = data;
      }
    };

    (async () => {
      const r = await window.dataSdk.init(dataHandler);
      if (!r.isOk) console.error('Data SDK init failed');
    })();

    // Form submission
    document.getElementById('evaluation-form').addEventListener('submit', async (e) => {
      e.preventDefault();
      
      if (allEvaluations.length >= 999) {
        alert('Limite de avaliações atingido!');
        return;
      }

      const result = await window.dataSdk.create({
        name: document.getElementById('eval-name').value.trim(),
        email: document.getElementById('eval-email').value.trim(),
        design_atrativo: formData.design_atrativo || '',
        sensor_funciona: formData.sensor_funciona || '',
        conexao_facil: formData.conexao_facil || '',
        led_ajuda: formData.led_ajuda || '',
        material_sustentavel: formData.material_sustentavel || '',
        pratico_dia_a_dia: formData.pratico_dia_a_dia || '',
        dificuldades: formData.dificuldades || '',
        atende_expectativas: formData.atende_expectativas || '',
        gostou_mais: formData.gostou_mais || '',
        recomenda: formData.recomenda || '',
        reclamacao: document.getElementById('eval-reclamacao').value.trim(),
        sugestao: document.getElementById('eval-sugestao').value.trim(),
        elogio: document.getElementById('eval-elogio').value.trim(),
        created_at: new Date().toISOString()
      });

      if (result.isOk) {
        goToScreen('sucesso');
        formData = {};
        document.getElementById('evaluation-form').reset();
      } else {
        alert('Erro ao enviar avaliação. Tente novamente.');
      }
    });

    // Element SDK
    const defaultConfig = {
      app_name: 'EcoBottle Smart',
      app_slogan: 'Hidratação inteligente para uma vida saudável',
      water_consumed: '1,5L',
      primary_color: '#e879a3',
      secondary_color: '#888888',
      bg_color: '#faf9f8',
      surface_color: '#ffffff',
      text_color: '#2d2d2d',
      font_family: 'Poppins'
    };

    function applyConfig(config) {
      const c = { ...defaultConfig, ...config };
      document.getElementById('app-name').textContent = c.app_name;
      document.getElementById('app-slogan').textContent = c.app_slogan;
      document.getElementById('water-consumed').textContent = `Você bebeu ${c.water_consumed} hoje`;
    }

    if (window.elementSdk) {
      window.elementSdk.init({
        defaultConfig,
        onConfigChange: async (config) => applyConfig(config),
        mapToCapabilities: () => ({
          recolorables: [],
          borderables: [],
          fontEditable: undefined,
          fontSizeable: undefined
        }),
        mapToEditPanelValues: (config) => {
          const c = { ...defaultConfig, ...config };
          return new Map([
            ['app_name', c.app_name],
            ['app_slogan', c.app_slogan],
            ['water_consumed', c.water_consumed]
          ]);
        }
      });
    }

    lucide.createIcons();
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9f06cdb10437ca9f',t:'MTc3Njg4MzcxNC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
