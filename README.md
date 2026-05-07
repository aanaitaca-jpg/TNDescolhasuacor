
<html lang="pt-BR">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Thamires Lisboa · Nail Designer</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;1,400&family=Jost:wght@300;400;500&display=swap" rel="stylesheet"/>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{--bg:#1c1714;--panel:#231e1a;--border:rgba(196,150,122,.18);--accent:#c4967a;--muted:#7a6458;--text:#f0e8e0;--soft:#c8b8ac;}
body{background:var(--bg);color:var(--text);font-family:'Jost',sans-serif;font-weight:300;min-height:100vh;overflow-x:hidden}
header{text-align:center;padding:2.5rem 1rem 1.5rem;border-bottom:1px solid var(--border)}
.logo-name{font-family:'Playfair Display',serif;font-style:italic;font-size:clamp(1.8rem,5vw,2.8rem);color:var(--accent);letter-spacing:.04em}
.logo-sub{font-size:.6rem;letter-spacing:.42em;color:var(--muted);margin-top:5px;text-transform:uppercase}
.layout{display:grid;grid-template-columns:1fr 1.4fr;max-width:1120px;margin:0 auto}
@media(max-width:740px){.layout{grid-template-columns:1fr}}
.panel-left{padding:2rem 1.8rem;border-right:1px solid var(--border);display:flex;flex-direction:column;align-items:center;gap:1.2rem;position:sticky;top:0;height:fit-content}
@media(max-width:740px){.panel-left{position:static;border-right:none;border-bottom:1px solid var(--border)}}
.plabel{font-size:.54rem;letter-spacing:.38em;text-transform:uppercase;color:var(--muted)}
.nail-wrap{width:100%;max-width:320px;border-radius:16px;overflow:hidden;box-shadow:0 16px 48px rgba(0,0,0,.7)}
#nailCanvas{display:block;width:100%;height:auto}
.cinfo{text-align:center;min-height:56px}
.cinfo-row{display:flex;align-items:center;justify-content:center;gap:10px;margin-bottom:4px}
.cdot{width:20px;height:20px;border-radius:50%;border:2px solid rgba(255,255,255,.14);background:var(--muted);transition:background .3s;flex-shrink:0}
.cname{font-family:'Playfair Display',serif;font-style:italic;font-size:.95rem;color:var(--soft)}
.cmarca{font-size:.54rem;letter-spacing:.25em;text-transform:uppercase;color:var(--muted)}
.cfinish{font-size:.48rem;letter-spacing:.18em;text-transform:uppercase;color:#5a4a42;margin-top:1px}
.btn-cta{background:var(--accent);color:var(--bg);border:none;font-family:'Jost',sans-serif;font-weight:500;font-size:.64rem;letter-spacing:.28em;text-transform:uppercase;padding:12px 24px;border-radius:40px;cursor:pointer;text-decoration:none;display:block;transition:background .2s,transform .15s;width:100%;max-width:220px;text-align:center}
.btn-cta:hover{background:#d4a68a;transform:translateY(-1px)}
.cta-sub{font-size:.52rem;color:var(--muted);letter-spacing:.1em;text-align:center;margin-top:3px}
.panel-right{padding:2rem 1.8rem}
.filter-section{margin-bottom:1.2rem}
.filter-label{font-size:.5rem;letter-spacing:.3em;text-transform:uppercase;color:var(--muted);margin-bottom:.45rem}
.filter-row{display:flex;flex-wrap:wrap;gap:5px}
.ftab{background:transparent;border:1px solid #3a332e;color:#8a7a70;font-family:'Jost',sans-serif;font-size:.52rem;letter-spacing:.2em;text-transform:uppercase;padding:4px 11px;border-radius:30px;cursor:pointer;transition:all .2s}
.ftab:hover,.ftab.active{border-color:var(--accent);color:var(--accent);background:rgba(196,150,122,.08)}
.search-wrap{position:relative;margin-bottom:1.1rem}
.search-input{width:100%;background:#2a2320;border:1px solid var(--border);color:var(--text);font-family:'Jost',sans-serif;font-size:.72rem;padding:8px 14px 8px 34px;border-radius:30px;outline:none;transition:border-color .2s}
.search-input:focus{border-color:var(--accent)}
.search-icon{position:absolute;left:11px;top:50%;transform:translateY(-50%);color:var(--muted);font-size:.8rem;pointer-events:none}
.search-input::placeholder{color:var(--muted)}
.cgrid{display:grid;grid-template-columns:repeat(auto-fill,minmax(88px,1fr));gap:8px}
.ccard{background:var(--panel);border:1px solid var(--border);border-radius:12px;padding:10px 6px 8px;cursor:pointer;text-align:center;transition:border-color .2s,transform .2s,background .2s;display:flex;flex-direction:column;align-items:center;gap:5px}
.ccard:hover{border-color:var(--accent);transform:translateY(-2px);background:#2e2622}
.ccard.sel{border-color:var(--accent);background:#2e2622;box-shadow:0 0 0 1px var(--accent)}
.cswatch{width:34px;height:34px;border-radius:50%;border:2px solid rgba(255,255,255,.1);transition:transform .2s;flex-shrink:0}
.ccard:hover .cswatch,.ccard.sel .cswatch{transform:scale(1.12)}
.ccard-name{font-size:.54rem;color:var(--soft);line-height:1.25}
.ccard-marca{font-size:.42rem;letter-spacing:.14em;text-transform:uppercase;color:#5a4a42}
.empty-msg{text-align:center;color:var(--muted);font-size:.7rem;padding:2rem;grid-column:1/-1}
footer{text-align:center;padding:1.8rem 1rem;border-top:1px solid var(--border)}
.f-name{font-family:'Playfair Display',serif;font-style:italic;color:var(--accent);font-size:1rem}
.f-sub{font-size:.54rem;letter-spacing:.3em;color:var(--muted);text-transform:uppercase;margin-top:3px}
.f-line{width:36px;height:1px;background:var(--border);margin:.9rem auto}
.f-note{font-size:.54rem;color:var(--muted)}
@keyframes fadeUp{from{opacity:0;transform:translateY(12px)}to{opacity:1;transform:translateY(0)}}
.ccard{animation:fadeUp .26s ease both}
</style>
</head>
<body>
<header>
  <div class="logo-name">Thamires Lisboa</div>
  <div class="logo-sub">Nail Designer</div>
</header>
<div class="layout">
  <div class="panel-left">
    <div class="plabel">Visualize nas suas unhas</div>
    <div class="nail-wrap"><canvas id="nailCanvas" width="500" height="500"></canvas></div>
    <div class="cinfo">
      <div class="cinfo-row">
        <div class="cdot" id="cdot"></div>
        <div class="cname" id="cname">Escolha uma cor</div>
      </div>
      <div class="cmarca" id="cmarca">toque em qualquer esmalte →</div>
      <div class="cfinish" id="cfinish"></div>
    </div>
    <div style="width:100%;max-width:220px">
      <a id="ctaLink" href="https://wa.me/message/2N4ZU6WSF2DED1" target="_blank" class="btn-cta">Agendar agora →</a>
      <div class="cta-sub" id="ctaSub">link da bio para marcar</div>
    </div>
  </div>
  <div class="panel-right">
    <div class="filter-section">
      <div class="filter-label">Categoria</div>
      <div class="filter-row" id="catRow">
        <button class="ftab active" data-cat="todos">Todas</button>
        <button class="ftab" data-cat="nudes">Nudes</button>
        <button class="ftab" data-cat="rosas">Rosas</button>
        <button class="ftab" data-cat="vermelhos">Vermelhos</button>
        <button class="ftab" data-cat="escuros">Escuros</button>
        <button class="ftab" data-cat="coloridos">Coloridos</button>
      </div>
    </div>
    <div class="filter-section">
      <div class="filter-label">Marca</div>
      <div class="filter-row" id="marcaRow">
        <button class="ftab active" data-marca="todas">Todas</button>
      <button class="ftab" data-marca="Anita">Anita</button>
      <button class="ftab" data-marca="Dailus">Dailus</button>
      <button class="ftab" data-marca="Impala">Impala</button>
      <button class="ftab" data-marca="Risqué">Risqué</button>
      </div>
    </div>
    <div class="search-wrap">
      <span class="search-icon">🔍</span>
      <input class="search-input" id="searchInput" type="text" placeholder="Buscar por nome..."/>
    </div>
    <div class="cgrid" id="cgrid"></div>
  </div>
</div>
<footer>
  <div class="f-name">Thamires Lisboa</div>
  <div class="f-sub">Nail Designer</div>
  <div class="f-line"></div>
  <div class="f-note">© 2025 · Todos os direitos reservados</div>
</footer>
<script>
const NAIL_B64='/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDAAMCAgICAgMCAgIDAwMDBAYEBAQEBAgGBgUGCQgKCgkICQkKDA8MCgsOCwkJDRENDg8QEBEQCgwSExIQEw8QEBD/2wBDAQMDAwQDBAgEBAgQCwkLEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBD/wAARCAH0AfQDASIAAhEBAxEB/8QAHwAAAQUBAQEBAQEAAAAAAAAAAAECAwQFBgcICQoL/8QAtRAAAgEDAwIEAwUFBAQAAAF9AQIDAAQRBRIhMUEGE1FhByJxFDKBkaEII0KxwRVS0fAkM2JyggkKFhcYGRolJicoKSo0NTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uHi4+Tl5ufo6erx8vP09fb3+Pn6/8QAHwEAAwEBAQEBAQEBAQAAAAAAAAECAwQFBgcICQoL/8QAtREAAgECBAQDBAcFBAQAAQJ3AAECAxEEBSExBhJBUQdhcRMiMoEIFEKRobHBCSMzUvAVYnLRChYkNOEl8RcYGRomJygpKjU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6goOEhYaHiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU1dbX2Nna4uPk5ebn6Onq8vP09fb3+Pn6/9oADAMBAAIRAxEAPwD8qqKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKMH0owfSgAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAoooAyQMdaAH5HcmjB7V7B4W/ZV+MHiqxi1KDSdN0qGYbo/7W1SC0Zl/3JG3L/wACArkfiB8JvHPwyukg8V6SsccrbYrm2njuLeU9cLJGzLn2reeFrU1zSg18jKOIpVHyxkjiqKKKwNQooooA0NK0rUda1G10nSbSW7vryVYLeGJdzyyMdqqB719T+Hf2K9D0eFF+L3jq7sNVbb9o0fR7RZJLRdu7Ek8ny+Z/sKuP9r+Guy/4JlfCPTdU8R+IPjZ4itFlg8Mx/Y9L81flW6dd0kv1WP5f+2hr27xDpdnr2u3viK+aV5b6driRd3y7mavp+E8swub4qrHF35IJbd2eHxTjcTlGEpTw1uebe/Zf8OfKHjT9j7QZ4JJfhT44uru8iiaRdP1u2jga4K/wRTI23zP7qsq7v7275a+Ybm1uLK4ktbmJ4poXZJEcYKsOoNfpbqnh21k+azbyP7yt8y18N/tIaTBo3xc1e2t2TZNFbXPy/wB6SBGb823H8a7uKMiwWWQhVwkpa6Wf+ZwcOZ1i8yc6WLgtOq/yPLKKKK+KPqwooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAcpHBr6a/YX+DFt8S/H+r+LNatBNpfgfTZtVVJE3RyXioxgVv72GXdt/2a+ZAOK/T7/gnd4N/sn9mHxV4mWHF14kuryONtv344YfLj/8AIjSVVOpGnVpuX8y/M2p4eWIhUUek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CiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKAFHav2N/4J7Rrbfsx+GQvSSS6kb/v81fjkO1fsl+wKv8AxjL4SX+8s3/o5q8nN/4MfU9rI/8AeH6H03D80v8AwGrBZWX5f++qp2zNu2qv/fVXm25+Xb/u14cT6OXxFbyV+Zd38Py1FKrR/dZf92pX+Vmbd/tUjR3DL8rLJ/dWkKUiJNu1fl/4DUw/i2/LUW3a21t27+Kkb+9u+T+7WnwiJYbps/Lt/utUF/fKsbM3zVXmk8t/vf7u2s7UZmaM7W3M1KdX3S6cIykc9rGoeZJt3N9771eDftbeJD4X/Z18d6huw95YLpqf7X2mRYm/8dkavZtXuP3yx7l3V8k/8FEdeNj8EdN0VHwdW12Hd/tRwxyM3/jzR1ngF7SvFeZtmT9lhZuPY/NuiiivtD87CiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACgdaKB1oAXtX7M/sEqv/AAzL4P3L/wAspm/8jNX4zdq/ZL9hOSSP9mrwbt/54Tf+jGrys3/hR9T28j/jy9D6bt13fd+9/eq1tVd25V21Vs/4WZtv+zV11+Vdzf8AfVeLFe6e9OXvFdlb/gP+1UbfKP8AWfM38S1O6/71Mfd8vzfLVE8xE+7buZmqrN8z/KrVadl2/wCd1UZpm+ZWZf8AvqspmsCG82qm7bWDf3DbSv3a1biTcPlZv+BVgX7L5q7mrCcjeHumFeRtMWZf/Ha+Hv8AgpfdtFo3gTS933ri+uGX/gMS/wDxVfeCrw8jf73zV+ff/BTib/iovA1ru4FjdP8A+RFrrymP+1I586qf7Ez4fooor64+ECiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACgdaKKAF6Gv2c/YktTZ/s2eBVfdvksWk/4C0jV+Mn+NfuN+znobaH8E/A2m+Wy+XoNm23/aaNZG/wDQq8fOX+6jHzPdyKP76T8j1+2ZvvN/6FV0XCqyx/3l3VlJcKsS7vvf3f71aMXl7POZdu5fvV4sJHvzh7xI237q/LTG2/N8u6nKq5+bcytTW/2VZf8A2WtTLlGS9Fbbu3fe3Vj3TbX2tt2tWpMzNDubd8tYN22590i1y1pHVQiI7bhtWs67h3fw4ar5k/u1TkkZv4f4qyZXKYt80lvGy/3vvV+cv/BS26aT4heEbftHo0jf99TNX6QauqtCzN97bX5z/wDBS6zEPi7wRdDkyaVcKT/uzV6GTy/2o4c6/wBy+Z8XUUUV9YfFBRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRQOtAFiyjaa7hhVctJIq4/Gv368G6TDpPhjS9LVdq2dnDbqv8A1zjVf/Za/BTwnGsnirRo2+61/bqf+/i1+/1g3+jqqx/dX5a8LOnrD5n0ORR+OXoSxxyeb8yr/s7q1EZdjL8y/wDoNVoY1ZW8xV+X/wAdqVPmK/K23+7t+avIge9P3ifzFVdq7tv97b8tM8xs/wB3/eoZfm2tuZv4dtNddq7vL2/w1oR7oy4+ZGZWZlrCv/7rfIv92tuT/V/LuZv96sa+WPazK3zbqwqm9EobuF2rTJW3D5Vp6zbhtVf96oJWVV3N92sJSNuX3jP1La0PzNtr8+v+CnMZ/tbwFMf+fO8X/wAiLX6A6hIux23fLXwb/wAFN7f/AED4e3n977dH/wCiq78ml/tR5+dr/ZD4Nooor68+GCiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigDR0GX7Prmn3H/PK6hk/JxX9AWiTLNbxMq7tyrX8+docXcB/wBtf51+/fgmb7V4e0uZm/1lpDJu/wCA14Od7w+f6H0WQ/DU+X6nUIq/6v7y/wAPzU5flO75ttNiX7392nPHz/6Cu771eSj2mOHzfNuZlX+LdTdyyfMvl7f7zNTYfJ37drb1/wBnbRcbtvmRybdv8NMZDKsiq0m7atY1+u1W3LuZv4q1ZtzIu6T+L+7WbcbWlZVXb/easKpvScolDb/F5ny1DcqrIysy1NN5bFV3N8tRTfKjf3f7tYmyl7xzV+y58lf92vjD/gpxb7vB3w+utv3by+X/AL6ji/8Aia+ydYjk87crfKtfIX/BTBd3w18ESN95dVuF/wDIK135N/vJw55/ujPztPWig9aK+xPgwooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAmtv9bH/vr/ADr97/hu27wZoe5m+bTbdv8AyGtfgjaruuYR/ekX+dfvj4Dh+x+G9JtW/wCWNjbx/d/uxqteBnm8PmfR5BG6qfI7FI2Xb/D8v96ptqttZvLaoht/hZV/4D81Ofzsqu1fvf8AjteZE9lkrx87dq1BJ91m3fK38NT+Z83+r/ef7tRXC+d95mVVqpExKs21U+Vl+Wsm4kVd38VaNz5bfLuXbWbdNuP7vd8v+zXNVkdNJGdI25t21l21A8nyszK26rMnVtyrVCT5lbduWudnRGMTE1Rmkm8uPb/vV8kf8FKoFPwm8KSL/wAsdbZf++oW/wDia+sryTbPt/i3fxV8sf8ABSWHHwX8Ptt+7r8K/wDkvNXdlH+8ROHOl/srPzZooor7M+CCiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigC/osJuNXsbZes1zEn5sK/frRFWG2ijb+GNVr8H/hhZHVfiZ4T0zbn7Zrdhb4/wB6dF/rX72aVHutk/8AHq+ezz44L1PqOHtIVZehpQ/Mdy/LVh/3m3d/48tV0XyVbzPm/wB2pUZWjb5tzV5kJe6etOJKWk+9tbbt27agl8tU+Xb/ALK7qnRV2tu3qrf3qrvIq7lZlZv92qkSjOuPLkXd81ULllXduq7My/Msa/N/FWfKq7FaT5W/hWuWUjqijLv7xo3Tar/M38K1QuZG85l/2fmrSu5FZ93937tZFzcRrvZl2tXHze8dUTJu23XCs3ytXzH/AMFJRn4H6Ky/9DFb/wDpPPX0q7fvtzSbq+a/+CjMO74DaXN/1MNq3/kvPXp5P/HieZnf+7yPzSooor7U+CCiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigD039mjTxqf7QXw8tSuQPEdjMR7RzK/wD7LX7k6SrKjbm+X+Gvxc/Ynsft/wC0/wCBYyBiK6uLg/SO2lb/ANlr9p7Bd0ayK27/AIFXzOdy/wBohHyPrchj/s85eZpRNuHzf/Y1On3G2/PUSruRV2sabLNti3K27a38NcKPRlHmHiRvu7vn/wDHqim/eDcqttb+H+7RD5jfe2/Mv8VJL5kP3V3qv8Kt92qlImMeWRQmjaH7zf8AfVZc0nmOyt8u1a1LmbduZm+Vf4WrEuZNzO0f/fP8LVxzkdUP7xSu1b+6rViXka5Zvmb5a1L+T5GXdt+WsG4k8yb5pl2VyM6KXMUpVXzfutXzj/wUUj2/s/2X+zr9n/6Jnr6RZtz/AN35q+cP+Ch6t/wz7Bnouv2f/ouevVyj+PE83Of93kfmXRRRX2h8GFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFAH0r/wT4tYZ/wBpnQ2lXJisb2RPZvII/kxr9gbF2UcH+Giivls5/wB6j6H2GRf7o/U0rWeZhsaQkGrLLgEBjzRRXHE7p/EIucEZPFQTuyx4Boopz2FH4jKvEUYwPvt81Z9xDHt+7RRXJM6F8JkaiQI8bR+Vc/dwx7ZH287qKK5ZfEddL4TPdjivnr/godz+z1EfTXrH/wBFzUUV6mU/x4nk5t/u8z8x6KKK+1PhQooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooA//2Q==';
const MASK_B64='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';
const COLORS=[
  {name:'Carmim',hex:'#8B0000',cat:'vermelhos',finish:'Cremoso',marca:'Risqué'},
  {name:'Beijo',hex:'#C0392B',cat:'vermelhos',finish:'Cremoso',marca:'Risqué'},
  {name:'Léo Mandou Flores',hex:'#8B2252',cat:'rosas',finish:'Cremoso',marca:'Risqué'},
  {name:'Palco Cherry',hex:'#7B1565',cat:'escuros',finish:'Cremoso',marca:'Risqué'},
  {name:'Faço o Pink em Casa',hex:'#C2406A',cat:'rosas',finish:'Cremoso',marca:'Risqué'},
  {name:'Gabriela',hex:'#A52828',cat:'vermelhos',finish:'Cremoso',marca:'Risqué'},
  {name:'Tâmara',hex:'#7A2060',cat:'escuros',finish:'Cremoso',marca:'Risqué'},
  {name:'Preto Sépia',hex:'#1A1A1A',cat:'escuros',finish:'Cremoso',marca:'Risqué'},
  {name:'Turmalina',hex:'#6B2D8B',cat:'escuros',finish:'Cremoso',marca:'Risqué'},
  {name:'Rebu',hex:'#0D0D0D',cat:'escuros',finish:'Cremoso',marca:'Risqué'},
  {name:'Verdelino',hex:'#3DAD9B',cat:'coloridos',finish:'Brilhante',marca:'Risqué'},
  {name:'Lavanda Alma',hex:'#9B8DC8',cat:'nudes',finish:'Cremoso',marca:'Risqué'},
  {name:'Chik Pop',hex:'#CFA898',cat:'nudes',finish:'Cremoso',marca:'Risqué'},
  {name:'Condessa',hex:'#E8D5C8',cat:'nudes',finish:'Natural',marca:'Risqué'},
  {name:'Ninfa',hex:'#C8D0D8',cat:'nudes',finish:'Cremoso',marca:'Risqué'},
  {name:'Nude',hex:'#D4B89A',cat:'nudes',finish:'Cremoso',marca:'Risqué'},
  {name:'Nudeu Tempo',hex:'#C8B0B8',cat:'nudes',finish:'Cremoso',marca:'Risqué'},
  {name:'Bali',hex:'#9E8080',cat:'nudes',finish:'Cremoso',marca:'Risqué'},
  {name:'Antes Sol que Mal Iluminada',hex:'#E8622A',cat:'coloridos',finish:'Cremoso',marca:'Risqué'},
  {name:'Guerreira do Arco-Íris',hex:'#7A9040',cat:'coloridos',finish:'Cremoso',marca:'Risqué'},
  {name:'Licor',hex:'#3D0A18',cat:'escuros',finish:'Cremoso',marca:'Risqué'},
  {name:'Hoje Só Volto Amanhã',hex:'#8B1520',cat:'vermelhos',finish:'Cremoso',marca:'Risqué'},
  {name:'Bianco Puríssimo',hex:'#F5F5F5',cat:'coloridos',finish:'Cremoso',marca:'Risqué'},
  {name:'Descomplicado',hex:'#7B68C8',cat:'coloridos',finish:'Cremoso',marca:'Impala'},
  {name:'Marina',hex:'#80C8D8',cat:'coloridos',finish:'Cremoso',marca:'Impala'},
  {name:'Amore',hex:'#D8B8C8',cat:'nudes',finish:'Perolado',marca:'Impala'},
  {name:'Admire',hex:'#8B6090',cat:'escuros',finish:'Cremoso',marca:'Impala'},
  {name:'Destino',hex:'#5A1E40',cat:'escuros',finish:'Cremoso',marca:'Impala'},
  {name:'Flores',hex:'#2E9060',cat:'coloridos',finish:'Cremoso',marca:'Impala'},
  {name:'Elegante',hex:'#5A1A50',cat:'escuros',finish:'Cremoso',marca:'Impala'},
  {name:'Terra Morna',hex:'#7A4838',cat:'nudes',finish:'Cremoso',marca:'Impala'},
  {name:'Sem',hex:'#C8A8A0',cat:'nudes',finish:'Cremoso',marca:'Impala'},
  {name:'Recomeços',hex:'#606878',cat:'coloridos',finish:'Cremoso',marca:'Impala'},
  {name:'Vinho',hex:'#5A1828',cat:'escuros',finish:'Cremoso',marca:'Impala'},
  {name:'Coffee',hex:'#6A1A20',cat:'escuros',finish:'Cremoso',marca:'Impala'},
  {name:'Zaz',hex:'#C8C0E0',cat:'nudes',finish:'Cremoso',marca:'Impala'},
  {name:'Primor',hex:'#0D0D0D',cat:'escuros',finish:'Cremoso',marca:'Impala'},
  {name:'Cheia de Manias',hex:'#8B1878',cat:'escuros',finish:'Cremoso',marca:'Impala'},
  {name:'Sem Limites',hex:'#6040A0',cat:'escuros',finish:'Metálico',marca:'Impala'},
  {name:'Vivência',hex:'#3050D0',cat:'coloridos',finish:'Cremoso',marca:'Impala'},
  {name:'Bailarina',hex:'#E0C8D0',cat:'nudes',finish:'Cremoso',marca:'Impala'},
  {name:'Parceria',hex:'#6A1840',cat:'escuros',finish:'Cremoso',marca:'Anita'},
  {name:'Mas Bora',hex:'#D0F040',cat:'coloridos',finish:'Cremoso',marca:'Anita'},
  {name:'Eu Não Fiz',hex:'#2850D0',cat:'coloridos',finish:'Cremoso',marca:'Anita'},
  {name:'Lápis Lazuli',hex:'#1830C0',cat:'coloridos',finish:'Perolado',marca:'Anita'},
  {name:'Passelo a Cavalo',hex:'#3A1010',cat:'escuros',finish:'Cremoso',marca:'Anita'},
  {name:'Casaco Quentinho',hex:'#C8B0C0',cat:'nudes',finish:'Cremoso',marca:'Anita'},
  {name:'Jantar a Dois',hex:'#C0B0C8',cat:'nudes',finish:'Cremoso',marca:'Anita'},
  {name:'Cabaça de Inverno',hex:'#A898B8',cat:'nudes',finish:'Cremoso',marca:'Anita'},
  {name:'Bailarina',hex:'#C870C0',cat:'rosas',finish:'Cremoso',marca:'Dailus'},
  {name:'Sorvete de Menta',hex:'#60D8C8',cat:'coloridos',finish:'Cremoso',marca:'Dailus'},
  {name:'Pé de Laranja',hex:'#F0A070',cat:'coloridos',finish:'Cremoso',marca:'Dailus'},
  {name:'Flower Lilás',hex:'#C0C8F0',cat:'nudes',finish:'Cremoso',marca:'Dailus'},
  {name:'Flower Verde',hex:'#B8D8A0',cat:'coloridos',finish:'Cremoso',marca:'Dailus'},
  {name:'Latte',hex:'#C8B0A0',cat:'nudes',finish:'Cremoso',marca:'Dailus'},
  {name:'Lavender',hex:'#C0B0D8',cat:'nudes',finish:'Cremoso',marca:'Dailus'},
  {name:'Maré Alta',hex:'#40A8E0',cat:'coloridos',finish:'Cremoso',marca:'Dailus'},
  {name:'Pinkberry',hex:'#E8C0D0',cat:'nudes',finish:'Cremoso',marca:'Dailus'},
  {name:'Berry Coast',hex:'#E8C8E0',cat:'nudes',finish:'Cremoso',marca:'Dailus'},
  {name:'Miss Quece',hex:'#E080D0',cat:'rosas',finish:'Cremoso',marca:'Dailus'},
  {name:'Tromba de Elefante',hex:'#707888',cat:'coloridos',finish:'Cremoso',marca:'Dailus'},
];

const canvas=document.getElementById('nailCanvas');
const ctx=canvas.getContext('2d',{willReadFrequently:true});
const CW=canvas.width,CH=canvas.height;
const mCv=document.createElement('canvas');mCv.width=CW;mCv.height=CH;
const mCtx=mCv.getContext('2d',{willReadFrequently:true});
let origPx=null,maskPx=null,loaded=0;
function onLoad(){loaded++;if(loaded===2){ctx.drawImage(nailImg,0,0,CW,CH);origPx=new Uint8ClampedArray(ctx.getImageData(0,0,CW,CH).data);mCtx.drawImage(maskImg,0,0,CW,CH);maskPx=new Uint8ClampedArray(mCtx.getImageData(0,0,CW,CH).data);}}
const nailImg=new Image();nailImg.onload=onLoad;nailImg.src='data:image/jpeg;base64,'+NAIL_B64;
const maskImg=new Image();maskImg.onload=onLoad;maskImg.src='data:image/png;base64,'+MASK_B64;

function hexToRgb(hex){return[parseInt(hex.slice(1,3),16)/255,parseInt(hex.slice(3,5),16)/255,parseInt(hex.slice(5,7),16)/255];}
function rgbToHls(r,g,b){
  const max=Math.max(r,g,b),min=Math.min(r,g,b),l=(max+min)/2;
  if(max===min)return[0,l,0];
  const d=max-min,s=l>0.5?d/(2-max-min):d/(max+min);
  let h;
  if(max===r)h=((g-b)/d+(g<b?6:0))/6;
  else if(max===g)h=((b-r)/d+2)/6;
  else h=((r-g)/d+4)/6;
  return[h,l,s];
}
function hlsToRgb(h,l,s){
  if(s===0)return[l,l,l];
  const q=l<0.5?l*(1+s):l+s-l*s,p=2*l-q;
  const hue2=(p,q,t)=>{if(t<0)t+=1;if(t>1)t-=1;if(t<1/6)return p+(q-p)*6*t;if(t<0.5)return q;if(t<2/3)return p+(q-p)*(2/3-t)*6;return p;};
  return[hue2(p,q,h+1/3),hue2(p,q,h),hue2(p,q,h-1/3)];
}

function applyColor(hex){
  if(!origPx||!maskPx)return;
  const[tr,tg,tb]=hexToRgb(hex);
  const[th,,ts]=rgbToHls(tr,tg,tb);
  const d=ctx.createImageData(CW,CH);const o=d.data;
  for(let i=0;i<origPx.length;i+=4){
    const a=maskPx[i]/255;
    const or=origPx[i]/255,og=origPx[i+1]/255,ob=origPx[i+2]/255;
    if(a<0.02){o[i]=origPx[i];o[i+1]=origPx[i+1];o[i+2]=origPx[i+2];o[i+3]=255;}
    else{
      const[,l_orig]=rgbToHls(or,og,ob);
      const[nr,ng,nb]=hlsToRgb(th,l_orig,ts*0.92);
      o[i]=Math.round((or*(1-a)+nr*a)*255);
      o[i+1]=Math.round((og*(1-a)+ng*a)*255);
      o[i+2]=Math.round((ob*(1-a)+nb*a)*255);
      o[i+3]=255;
    }
  }
  ctx.putImageData(d,0,0);
}

let curCat='todos',curMarca='todas',curSearch='',selIdx=null;
const cdot=document.getElementById('cdot'),cname=document.getElementById('cname');
const cmarca=document.getElementById('cmarca'),cfinish=document.getElementById('cfinish');
const cgrid=document.getElementById('cgrid'),ctaLink=document.getElementById('ctaLink'),ctaSub=document.getElementById('ctaSub');

function filtered(){return COLORS.filter(c=>(curCat==='todos'||c.cat===curCat)&&(curMarca==='todas'||c.marca===curMarca)&&(curSearch===''||c.name.toLowerCase().includes(curSearch)||c.marca.toLowerCase().includes(curSearch)));}

function renderGrid(){
  cgrid.innerHTML='';const list=filtered();
  if(!list.length){cgrid.innerHTML='<div class="empty-msg">Nenhum esmalte encontrado</div>';return;}
  list.forEach((c,i)=>{
    const gi=COLORS.indexOf(c),card=document.createElement('div');
    card.className='ccard'+(selIdx===gi?' sel':'');card.style.animationDelay=(i*.02)+'s';
    card.innerHTML=`<div class="cswatch" style="background:${c.hex}"></div><div class="ccard-name">${c.name}</div><div class="ccard-marca">${c.marca}</div>`;
    card.addEventListener('click',()=>pick(gi));cgrid.appendChild(card);
  });
}

function pick(idx){
  selIdx=idx;const c=COLORS[idx];
  document.querySelectorAll('.ccard').forEach(e=>e.classList.remove('sel'));
  const vis=filtered(),vi=vis.indexOf(c);if(vi>=0)cgrid.children[vi]?.classList.add('sel');
  cdot.style.background=c.hex;cname.textContent=c.name;cmarca.textContent=c.marca;cfinish.textContent=c.finish;
  applyColor(c.hex);
  ctaSub.textContent='cor: '+c.name+' · '+c.marca;
  ctaLink.href='https://wa.me/message/2N4ZU6WSF2DED1?text='+encodeURIComponent('Olá, Thamires! Escolhi o esmalte "'+c.name+'" ('+c.marca+') e quero agendar 💅');
}

document.getElementById('catRow').addEventListener('click',e=>{const b=e.target.closest('.ftab');if(!b||!b.dataset.cat)return;document.querySelectorAll('#catRow .ftab').forEach(x=>x.classList.remove('active'));b.classList.add('active');curCat=b.dataset.cat;renderGrid();});
document.getElementById('marcaRow').addEventListener('click',e=>{const b=e.target.closest('.ftab');if(!b||!b.dataset.marca)return;document.querySelectorAll('#marcaRow .ftab').forEach(x=>x.classList.remove('active'));b.classList.add('active');curMarca=b.dataset.marca;renderGrid();});
document.getElementById('searchInput').addEventListener('input',e=>{curSearch=e.target.value.toLowerCase().trim();renderGrid();});
renderGrid();
</script>
</body>
</html>
