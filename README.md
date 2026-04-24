

<style>
  * { box-sizing: border-box; margin: 0; padding: 0; }
  body { font-family: 'Georgia', serif; }

  .site-wrapper {
    background: #1a1a1a;
    min-height: 100vh;
    color: #f5f0eb;
  }

  .header {
    text-align: center;
    padding: 2.5rem 1rem 1.5rem;
    border-bottom: 1px solid #333;
  }
  .header-name {
    font-family: 'Georgia', serif;
    font-size: 2rem;
    font-weight: 300;
    letter-spacing: 0.12em;
    color: #c4967a;
    font-style: italic;
  }
  .header-sub {
    font-family: Arial, sans-serif;
    font-size: 0.65rem;
    letter-spacing: 0.35em;
    color: #a08070;
    margin-top: 4px;
    text-transform: uppercase;
  }

  .main {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 0;
    max-width: 900px;
    margin: 0 auto;
  }

  @media (max-width: 620px) {
    .main { grid-template-columns: 1fr; }
  }

  .nail-preview-panel {
    padding: 2rem 1.5rem 2rem 2rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    border-right: 1px solid #2a2a2a;
  }

  .panel-label {
    font-family: Arial, sans-serif;
    font-size: 0.6rem;
    letter-spacing: 0.3em;
    text-transform: uppercase;
    color: #a08070;
    margin-bottom: 1.2rem;
  }

  .nail-container {
    width: 100%;
    max-width: 320px;
    position: relative;
    border-radius: 14px;
    overflow: hidden;
    background: #111;
  }

  .nail-container img {
    width: 100%;
    display: block;
    opacity: 0.92;
  }

  .nail-overlay {
    position: absolute;
    top: 0; left: 0; right: 0; bottom: 0;
    mix-blend-mode: multiply;
    border-radius: 14px;
    opacity: 0;
    transition: opacity 0.4s ease, background-color 0.3s ease;
    pointer-events: none;
  }

  .selected-color-info {
    margin-top: 1.2rem;
    text-align: center;
  }
  .color-dot {
    width: 28px;
    height: 28px;
    border-radius: 50%;
    margin: 0 auto 6px;
    border: 2px solid #444;
    transition: background-color 0.3s ease;
  }
  .color-name {
    font-family: Arial, sans-serif;
    font-size: 0.75rem;
    color: #d4b8a8;
    letter-spacing: 0.1em;
  }
  .color-type {
    font-family: Arial, sans-serif;
    font-size: 0.6rem;
    color: #7a6a60;
    margin-top: 2px;
    text-transform: uppercase;
    letter-spacing: 0.15em;
  }

  .upload-btn {
    margin-top: 1.5rem;
    background: transparent;
    border: 1px solid #c4967a;
    color: #c4967a;
    font-family: Arial, sans-serif;
    font-size: 0.65rem;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    padding: 10px 20px;
    border-radius: 40px;
    cursor: pointer;
    transition: background 0.2s;
    width: 100%;
    max-width: 220px;
  }
  .upload-btn:hover { background: rgba(196,150,122,0.12); }
  #photoInput { display: none; }

  .uploaded-preview {
    margin-top: 1rem;
    width: 100%;
    max-width: 320px;
    border-radius: 14px;
    overflow: hidden;
    display: none;
  }
  .uploaded-preview img {
    width: 100%;
    display: block;
    border-radius: 14px;
  }
  .uploaded-label {
    font-family: Arial, sans-serif;
    font-size: 0.6rem;
    color: #7a6a60;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    margin-top: 0.5rem;
    text-align: center;
  }

  .colors-panel {
    padding: 2rem 2rem 2rem 1.5rem;
    overflow-y: auto;
    max-height: 680px;
  }

  .filter-tabs {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    margin-bottom: 1.2rem;
  }
  .filter-tab {
    background: transparent;
    border: 1px solid #3a3a3a;
    color: #9a8878;
    font-family: Arial, sans-serif;
    font-size: 0.6rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    padding: 5px 12px;
    border-radius: 20px;
    cursor: pointer;
    transition: all 0.2s;
  }
  .filter-tab:hover, .filter-tab.active {
    border-color: #c4967a;
    color: #c4967a;
    background: rgba(196,150,122,0.08);
  }

  .colors-grid {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 8px;
  }

  .color-swatch {
    aspect-ratio: 1;
    border-radius: 50%;
    cursor: pointer;
    border: 2px solid transparent;
    transition: transform 0.2s, border-color 0.2s;
    position: relative;
  }
  .color-swatch:hover { transform: scale(1.15); }
  .color-swatch.selected {
    border-color: #f0e0d0;
    transform: scale(1.12);
    box-shadow: 0 0 0 1px #c4967a;
  }

  .cta-panel {
    grid-column: 1 / -1;
    text-align: center;
    padding: 1.5rem;
    border-top: 1px solid #2a2a2a;
  }
  .cta-btn {
    background: #c4967a;
    color: #1a1a1a;
    border: none;
    font-family: Arial, sans-serif;
    font-size: 0.7rem;
    font-weight: bold;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    padding: 14px 40px;
    border-radius: 40px;
    cursor: pointer;
    transition: background 0.2s, transform 0.1s;
  }
  .cta-btn:hover { background: #d4a68a; transform: scale(1.02); }
  .cta-sub {
    font-family: Arial, sans-serif;
    font-size: 0.6rem;
    color: #6a5a50;
    margin-top: 8px;
    letter-spacing: 0.1em;
  }
</style>

<div class="site-wrapper">
  <div class="header">
    <div class="header-name">Thamires Lisboa</div>
    <div class="header-sub">Nail Designer</div>
  </div>

  <div class="main">
    <div class="nail-preview-panel">
      <div class="panel-label">Visualize nas suas unhas</div>

      <div class="nail-container" id="nailContainer">
        <img src="https://i.imgur.com/placeholder.png" id="nailImg" alt="Unhas" onerror="this.style.display='none'" />
        <div class="nail-overlay" id="nailOverlay"></div>
      </div>

      <div class="selected-color-info">
        <div class="color-dot" id="colorDot" style="background:#b09080;"></div>
        <div class="color-name" id="colorName">Escolha uma cor</div>
        <div class="color-type" id="colorType">passe o mouse para visualizar</div>
      </div>

      <label class="upload-btn" for="photoInput">📷 Enviar foto da minha mão</label>
      <input type="file" id="photoInput" accept="image/*" />

      <div class="uploaded-preview" id="uploadedPreview">
        <img id="uploadedImg" alt="Sua mão" />
        <div class="uploaded-label">sua foto · toque uma cor para visualizar</div>
      </div>
    </div>

    <div class="colors-panel">
      <div class="panel-label">Escolha sua cor</div>

      <div class="filter-tabs" id="filterTabs">
        <button class="filter-tab active" data-cat="todos">Todas</button>
        <button class="filter-tab" data-cat="nudes">Nudes</button>
        <button class="filter-tab" data-cat="rosas">Rosas</button>
        <button class="filter-tab" data-cat="vermelhos">Vermelhos</button>
        <button class="filter-tab" data-cat="escuros">Escuros</button>
        <button class="filter-tab" data-cat="coloridos">Coloridos</button>
      </div>

      <div class="colors-grid" id="colorsGrid"></div>
    </div>

    <div class="cta-panel">
      <button class="cta-btn" onclick="sendPrompt('Adorei a cor ' + document.getElementById(\'colorName\').textContent + '! Quero agendar meu horário com a Thamires')">
        Agendar meu horário →
      </button>
      <div class="cta-sub">link da bio para marcar · @thamireslisboa</div>
    </div>
  </div>
</div>

<script>
const colors = [
  { name: "Areia Fina", hex: "#D4B896", cat: "nudes", type: "Cremoso" },
  { name: "Nude Rosado", hex: "#C9A18A", cat: "nudes", type: "Cremoso" },
  { name: "Pele Perfeita", hex: "#BF9880", cat: "nudes", type: "Perolado" },
  { name: "Caramelo Suave", hex: "#B8855A", cat: "nudes", type: "Cremoso" },
  { name: "Latte", hex: "#A67B5B", cat: "nudes", type: "Cremoso" },
  { name: "Bege Claro", hex: "#E8D5BE", cat: "nudes", type: "Cremoso" },
  { name: "Rosê Antigo", hex: "#C8857A", cat: "rosas", type: "Cremoso" },
  { name: "Quartzo Rosa", hex: "#E8A0A0", cat: "rosas", type: "Perolado" },
  { name: "Rosa Ballet", hex: "#F0B8C8", cat: "rosas", type: "Cremoso" },
  { name: "Rosa Seco", hex: "#D4889A", cat: "rosas", type: "Cremoso" },
  { name: "Chá de Rosa", hex: "#E8C0C0", cat: "rosas", type: "Perolado" },
  { name: "Rosa Mocha", hex: "#B8706A", cat: "rosas", type: "Cremoso" },
  { name: "Vermelho Clássico", hex: "#C0302A", cat: "vermelhos", type: "Cremoso" },
  { name: "Cereja", hex: "#A02020", cat: "vermelhos", type: "Cremoso" },
  { name: "Vermelho Coral", hex: "#D04840", cat: "vermelhos", type: "Cremoso" },
  { name: "Borgonha", hex: "#780018", cat: "vermelhos", type: "Cremoso" },
  { name: "Tomate", hex: "#D03820", cat: "vermelhos", type: "Cremoso" },
  { name: "Preto Carvão", hex: "#1A1A1A", cat: "escuros", type: "Cremoso" },
  { name: "Vinho Escuro", hex: "#4A0820", cat: "escuros", type: "Cremoso" },
  { name: "Marsala", hex: "#703040", cat: "escuros", type: "Cremoso" },
  { name: "Café Intenso", hex: "#3A2010", cat: "escuros", type: "Cremoso" },
  { name: "Azul Meia-Noite", hex: "#182040", cat: "escuros", type: "Perolado" },
  { name: "Roxo Escuro", hex: "#3A1850", cat: "escuros", type: "Metálico" },
  { name: "Verde Musgo", hex: "#304028", cat: "coloridos", type: "Cremoso" },
  { name: "Azul Bebê", hex: "#A0C0D8", cat: "coloridos", type: "Cremoso" },
  { name: "Lavanda", hex: "#B8A0D0", cat: "coloridos", type: "Cremoso" },
  { name: "Coral Vivo", hex: "#E07850", cat: "coloridos", type: "Cremoso" },
  { name: "Lilás", hex: "#C8A8E0", cat: "coloridos", type: "Perolado" },
  { name: "Verde Menta", hex: "#A0D0B8", cat: "coloridos", type: "Cremoso" },
  { name: "Amarelo Sol", hex: "#E8C840", cat: "coloridos", type: "Cremoso" },
];

let selectedColor = null;
let currentCat = "todos";

const nailImg = document.getElementById("nailImg");
const overlay = document.getElementById("nailOverlay");
const colorDot = document.getElementById("colorDot");
const colorName = document.getElementById("colorName");
const colorType = document.getElementById("colorType");
const grid = document.getElementById("colorsGrid");
const photoInput = document.getElementById("photoInput");
const uploadedPreview = document.getElementById("uploadedPreview");
const uploadedImg = document.getElementById("uploadedImg");

nailImg.src = "data:image/svg+xml;base64," + btoa(`<svg xmlns='http://www.w3.org/2000/svg' width='320' height='200'><rect width='320' height='200' fill='%231a1a1a'/><text x='50%' y='50%' dominant-baseline='middle' text-anchor='middle' fill='%23554444' font-size='13' font-family='Arial'>Carregando imagem...</text></svg>`);

const realNailImg = new Image();
realNailImg.crossOrigin = "anonymous";
realNailImg.onload = () => { nailImg.src = realNailImg.src; };
realNailImg.src = "https://images.unsplash.com/photo-1604654894610-df63bc536371?w=640&q=80";

function renderGrid() {
  grid.innerHTML = "";
  const filtered = currentCat === "todos" ? colors : colors.filter(c => c.cat === currentCat);
  filtered.forEach(c => {
    const sw = document.createElement("div");
    sw.className = "color-swatch" + (selectedColor && selectedColor.name === c.name ? " selected" : "");
    sw.style.background = c.hex;
    sw.title = c.name;
    sw.addEventListener("click", () => selectColor(c, sw));
    grid.appendChild(sw);
  });
}

function selectColor(c, el) {
  document.querySelectorAll(".color-swatch").forEach(s => s.classList.remove("selected"));
  el.classList.add("selected");
  selectedColor = c;
  colorDot.style.background = c.hex;
  colorName.textContent = c.name;
  colorType.textContent = c.type;

  overlay.style.backgroundColor = c.hex;
  overlay.style.opacity = "0.55";
  overlay.style.mixBlendMode = "multiply";
}

document.getElementById("filterTabs").addEventListener("click", e => {
  const tab = e.target.closest(".filter-tab");
  if (!tab) return;
  document.querySelectorAll(".filter-tab").forEach(t => t.classList.remove("active"));
  tab.classList.add("active");
  currentCat = tab.dataset.cat;
  renderGrid();
});

photoInput.addEventListener("change", e => {
  const file = e.target.files[0];
  if (!file) return;
  const reader = new FileReader();
  reader.onload = ev => {
    uploadedImg.src = ev.target.result;
    uploadedPreview.style.display = "block";
  };
  reader.readAsDataURL(file);
});

renderGrid();
</script>
