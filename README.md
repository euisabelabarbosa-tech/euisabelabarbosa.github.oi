<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Almoxarifado ETEC</title>

<!-- Fontes -->
<link href="https://fonts.googleapis.com/css2?family=Merriweather:wght@400;700&family=Outfit:wght@300;400;500;600&display=swap" rel="stylesheet">

<style>
  body { font-family: "Outfit", sans-serif; margin: 0; background: #e0dbdb; text-align: center; }
  header { position: fixed; top: 0; width: 100%; background: rgb(235, 229, 229); box-shadow: 0 2px 4px rgba(0,0,0,0.1); z-index: 1000; padding: 8px 20px; display: flex; flex-direction: column; align-items: center; }
  header h1 { font-size: 35px; font-family: "Merriweather", serif; font-weight: 700; margin: 10px 0; }
  header button { margin: 5px; padding: 5px 12px; cursor: pointer; background: none; border: none; font-size: 16px; font-family: "Merriweather", serif; font-weight: 500; color: black; transition: color 0.3s; }
  header button:hover { color: red; }
  header input { margin-left: 1px; padding: 3px 6px; border-radius: 15px; border: 0px solid #ccc; }
  main { padding-top: 105px; max-width: 1200px; margin: 0 auto; }
  .carousel { position: relative; width: 90%; max-width: 800px; aspect-ratio: 16 / 9; margin: 20px auto; overflow: hidden; border-radius: 10px; box-shadow: 0 4px 10px rgba(0,0,0,0.2); }
  .carousel img { width: 100%; height: 100%; object-fit: cover; position: absolute; top: 0; left: 0; transition: opacity 1s; }
  .carousel button { position: absolute; top: 50%; transform: translateY(-50%); background: rgba(255,255,255,0.6); border: none; padding: 10px; cursor: pointer; border-radius: 50%; font-size: 18px; }
  .carousel .prev { left: 10px; } .carousel .next { right: 10px; }
  section { padding: 40px 20px; text-align: center; }
  .inicio-texto h2 { font-family: "Merriweather", serif; font-size: 36px; margin: 0; }
  .inicio-texto h4 { font-family: "Merriweather", serif; font-size: 24px; margin: 5px 0 20px 0; font-weight: 500; }
  .inicio-texto p { font-size: 16px; max-width: 900px; margin: 0 auto 20px auto; line-height: 1.6; text-align: center; }
  .cards { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px,1fr)); gap: 20px; margin-top: 20px; justify-items: center; }
  .card { background: white; padding: 10px 10px 20px 10px; border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.2); text-align: center; transform: rotate(-1deg); transition: transform 0.3s; width: 200px; position: relative; cursor: pointer; }
  .card:hover { transform: rotate(0deg) scale(1.05); }
  .card img { width: 100%; height: 150px; object-fit: cover; border-radius: 6px; margin-bottom: 10px; }
  .card h3 { margin: 5px 0; font-size: 16px; font-weight: 600; color: black; transition: color 0.3s; }
  .card:hover h3 { color: red; }
  .tooltip { position: absolute; bottom: 120%; left: 50%; transform: translateX(-50%); background: rgba(0,0,0,0.8); color: white; padding: 6px 10px; border-radius: 6px; font-size: 13px; opacity: 0; pointer-events: none; transition: opacity 0.3s; white-space: nowrap; }
  .card:hover .tooltip { opacity: 1; }
  
  /* Formulário de cadastro */
  .form-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 15px; max-width: 800px; margin: 0 auto; background: white; padding: 20px; border-radius: 10px; box-shadow:0 4px 10px rgba(0,0,0,0.1); }
  .form-group { display: flex; flex-direction: column; }
  .form-group label { font-weight: 500; margin-bottom: 5px; text-align: left; }
  .form-group input, .form-group select { padding: 8px; border-radius: 5px; border: 1px solid #ccc; }
  .form-group.full-width { grid-column: 1 / -1; }
  .conditional { display: none; }
  button[type="submit"] { background:#0066cc; color:white; border:none; border-radius:5px; padding:10px; cursor:pointer; font-size:16px; transition:0.3s; }
  button[type="submit"]:hover { background:#005bb5; }

  /* Estilo da seção de detalhes */
  .detalhes-container { display:flex; flex-direction:column; align-items:center; max-width:800px; margin:0 auto; padding:20px; background:white; border-radius:10px; box-shadow:0 4px 10px rgba(0,0,0,0.2); }
  .detalhes-flex { display:flex; gap:20px; align-items:flex-start; width:100%; flex-wrap: wrap; }
  .detalhes-flex img { width:350px; height:420px; object-fit:cover; border-radius:8px; flex-shrink:0; }
  .detalhes-info { text-align:left; display:flex; flex-direction:column; gap:10px; font-size:16px; }
  .detalhes-container button { margin-top:20px; padding:10px 20px; background:#0066cc; color:white; border:none; border-radius:5px; cursor:pointer; }

  /* Sobre */
 .sobre-texto {
    background-color: #fff;
    padding: 40px;
    border-radius: 15px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
    max-width: 900px;
    text-align: justify;
    line-height: 1.8;
    color: #333;
    font-family: 'Merriweather', serif;
}

.sobre-texto h2 {
    text-align:center;
    font-size:32px;
    margin-bottom:20px;
}

</style>
</head>
<body>

<header>
  <div style="display:flex; align-items:center; justify-content:center; gap:20px;">
    <img src="https://leonardo-energy.org.br/wp-content/uploads/2017/07/LOGO-ETEC.jpg" height="80" alt="Logo ETEC">
    <img src="https://bkpsitecpsnew.blob.core.windows.net/uploadsitecps/sites/101/2021/02/Logo.png" height="90" alt="Logo CPS">
    <h1>ALMOXARIFADO ETEC</h1>
  </div>
  <div style="display:flex; align-items:center; justify-content:center; flex-wrap: wrap; gap:10px;">
    <button onclick="showPage('inicio')">Início</button>
    <button onclick="showPage('sobre')">Sobre</button>
    <button onclick="showPage('componentes')">Componentes</button>
    <button onclick="showPage('equipamentos')">Equipamentos</button>
    <button onclick="showPage('ferramentas')">Ferramentas</button>
    <button onclick="showPage('cadastro')">Cadastro</button>
    🔍 <input type="text" id="search" placeholder="Pesquisar..." oninput="filterItems()">
  </div>
</header>

<main>
  <!-- Início -->
  <section id="inicio">
    <div class="carousel">
      <img src="imagens/COMPONENTES.png" alt="Slide 1">
      <img src="imagens/circuitos.png" alt="Slide 2" style="opacity:0;">
      <img src="imagens/automoção.png" alt="Slide 3" style="opacity:0;">
      <img src="https://blog.win-source.net/wp-content/uploads/2023/12/%E8%A7%A3%E5%86%B3%E7%94%B5%E5%AD%90%E5%85%83%E4%BB%B6%E5%B0%8F%E6%89%B9%E9%87%8F%E9%87%87%E8%B4%AD%E9%9A%BE%E9%A2%98-1_proc.jpg" alt="Slide 4" style="opacity:0;">
      <button class="prev" onclick="prevImage()">◀</button>
      <button class="next" onclick="nextImage()">▶</button>
    </div>

    <div class="inicio-texto">
      <h2>BEM VINDO AO ALMOXARIFADO DIGITAL</h2>
      <h4>DA ETEC CAROLINA CARINHATO SAMPAIO</h4>
       <p>Este site apresenta e fornece acesso rápido aos componentes, ferramentas e equipamentos disponíveis no almoxarifado da ETEC, permitindo que alunos e professores consultem, conheçam e solicitem empréstimos de forma organizada e digital.</p>
    </div>

    <div class="cards">
      <div class="card" onclick="showPage('componentes')">
        <img src="imagens/componentes.placasite.png" alt="Componentes">
        <h3>Componentes</h3>
        <p>Confira os componentes eletrônicos disponíveis para seus projetos e aulas práticas.</p>
      </div>
      <div class="card" onclick="showPage('equipamentos')">
        <img src="imagens/equipamentos.placasite.png" alt="Equipamentos">
        <h3>Equipamentos</h3>
        <p>Veja os equipamentos disponíveis para empréstimo e uso supervisionado em laboratório.</p>
      </div>
      <div class="card" onclick="showPage('ferramentas')">
        <img src="imagens/ferramentas.placasite.png" alt="Ferramentas">
        <h3>Ferramentas</h3>
        <p>Explore as ferramentas disponíveis para uso em atividades práticas e projetos.</p>
      </div>
    </div>
  </section>

  <!-- Sobre -->
  <section id="sobre" style="display:none;">
    <div class="sobre-texto">
      <h2>Sobre o Projeto</h2>
      <p>
      Esse site foi desenvolvido como parte de um Projeto de Conclusão de Curso (TCC) pelos alunos do curso técnico em Eletrônica da ETEC Carolina Carinhato Sampaio. Seu principal objetivo é oferecer uma plataforma moderna, organizada e acessível para todos que frequentam a instituição, com foco especial em alunos, professores e coordenadores do curso.
      <br><br>
      Um almoxarifado é um setor responsável pelo armazenamento, controle, organização e distribuição de materiais, componentes e equipamentos utilizados em atividades educacionais e práticas laboratoriais. No contexto do curso de Eletrônica, esse espaço é essencial para garantir que os recursos estejam sempre disponíveis e em bom estado para os projetos desenvolvidos na escola.
      <br><br>
      Pensando nisso, este site foi criado para facilitar o acesso às informações sobre os componentes eletrônicos, ferramentas e equipamentos disponíveis no almoxarifado da instituição. A plataforma permite que os usuários conheçam cada item com mais detalhes, compreendendo sua função, aplicação e disponibilidade.
      <br><br>
      Além disso, o sistema possibilita o registro de empréstimos, permitindo que alunos e professores retirem temporariamente componentes ou equipamentos para utilização em aulas práticas, projetos escolares ou atividades extracurriculares, de forma organizada e com controle eficiente de devoluções.
      <br><br>
      Com isso, o Almoxarifado Digital contribui para tornar os processos mais transparentes, estimular o uso responsável dos recursos disponíveis, apoiar projetos e atividades práticas com maior agilidade e fortalecer a interação entre alunos, professores e a coordenação do curso.
    </p>
    </div>
  </section>

  <!-- Componentes -->
  <section id="componentes" style="display:none;">
    <h2>Componentes</h2>
    <div class="cards" id="componentes-list"></div>
  </section>

  <!-- Equipamentos -->
  <section id="equipamentos" style="display:none;">
    <h2>Equipamentos</h2>
    <div class="cards" id="equipamentos-list"></div>
  </section>

  <!-- Ferramentas -->
  <section id="ferramentas" style="display:none;">
    <h2>Ferramentas</h2>
    <div class="cards" id="ferramentas-list"></div>
  </section>

  <!-- Cadastro -->
  <section id="cadastro" style="display:none;">
    <h2>Cadastro de Empréstimo</h2>
    <form id="cadastroForm" onsubmit="saveCadastro(event)" class="form-grid">
      <div class="form-group full-width">
        <label>Nome Completo</label>
        <input type="text" id="nome" required>
      </div>
      <div class="form-group">
        <label>Tipo de Usuário</label>
        <select id="tipoUsuario" onchange="toggleCamposUsuario()" required>
          <option value="">Selecione</option>
          <option value="aluno">Aluno</option>
          <option value="professor">Professor</option>
          <option value="coordenador">Coordenador</option>
          <option value="modular">Modular</option>
        </select>
      </div>
      <div class="form-group">
        <label>Email Institucional</label>
        <input type="email" id="email" required>
      </div>
      <div class="form-group conditional" id="rmDiv">
        <label>RM</label>
        <input type="text" id="rm">
      </div>
      <div class="form-group conditional" id="serieDiv">
        <label>Série</label>
        <input type="text" id="serie">
      </div>
      <div class="form-group conditional" id="cursoDiv">
        <label>Curso</label>
        <input type="text" id="curso">
      </div>
      <div class="form-group full-width">
    <label>Componentes</label>
    <select id="itemEmprestadoComponentes" required>
        <option value="">Selecione</option>
        <option value="nenhum">Nenhum empréstimo</option>

        <!-- Botões, Interruptores e Controles -->
        <optgroup label="Botões, Interruptores e Controles">
            <option value="botoes">Botões</option>
            <option value="interruptores">Interruptores</option>
            <option value="push-trava">Push button com trava</option>
            <option value="push-comum">Push button comum</option>
            <option value="chave-alavanca">Chave alavanca</option>
            <option value="interruptor-lamina">Interruptor mestre de lâmina de canivete</option>
            <option value="controle-rgb">Controle RGB</option>
        </optgroup>

        <!-- Displays e LCDs -->
        <optgroup label="Displays e LCDs">
            <option value="display-7seg">Display de 7 segmentos</option>
            <option value="display-grande">Display grande</option>
            <option value="display-pequeno">Display pequeno</option>
            <option value="lcd-fio">LCD com fio</option>
            <option value="lcd-grande-sem-fio">LCD grande sem fio</option>
            <option value="lcd-pequeno-sem-fio">LCD pequeno sem fio</option>
            <option value="lcd-quebrado">LCD pequeno sem fio (quebrado)</option>
            <option value="lcd-botao">LCD com botão</option>
        </optgroup>

        <!-- LEDs e Lâmpadas -->
        <optgroup label="LEDs e Lâmpadas">
            <option value="led-piranha-azul">LED piranha azul</option>
            <option value="led-piranha-verde">LED piranha verde</option>
            <option value="led-piranha-vermelho">LED piranha vermelho</option>
            <option value="lampada-torpedo">Lâmpada torpedo 42 mm</option>
            <option value="lampada-incandescente">Lâmpada incandescente 150 W</option>
            <option value="lampada-led">Lâmpada LED 3 W</option>
            <option value="reed-switch">Ampola reed switch</option>
            <option value="lampada-amplificador">Lâmpada para amplificador</option>
            <option value="lampada-teleslide">Lâmpada teleslide 12 V</option>
            <option value="lampada-lbt">Lâmpada LBT 36 W</option>
            <option value="lampada-indicadora">Lâmpada indicadora 40 mA</option>
        </optgroup>

        <!-- Potenciômetros -->
        <optgroup label="Potenciômetros">
            <option value="pot-250k">Potenc. 250k</option>
            <option value="pot-220k">Potenc. 220k</option>
            <option value="pot-470r">Potenc. 470R</option>
            <option value="pot-10k">Potenc. 10k</option>
            <option value="pot-2k">Potenc. 2k</option>
            <option value="pot-1k">Potenc. 1k</option>
            <option value="pot-4r">Potenc. 4 ohms</option>
            <option value="pot-50k">Potenc. 50k</option>
            <option value="pot-5k">Potenc. 5k</option>
            <option value="pot-10m">Potenc. 10M</option>
            <option value="pot-470k">Potenc. 470k</option>
            <option value="pot-4k">Potenc. 4k</option>
            <option value="pot-2m">Potenc. 2M</option>
            <option value="pot-50r">Potenc. 50 ohms</option>
            <option value="pot-1m">Potenc. 1M</option>
            <option value="pot-100k">Potenc. 100k</option>
            <option value="pot-500k">Potenc. 500k</option>
            <option value="pot-4m">Potenc. 4M</option>
            <option value="pot-20k">Potenc. 20k</option>
            <option value="pot-duplo">Potenciômetro duplo</option>
        </optgroup>

        <!-- Resistores -->
        <optgroup label="Resistores">
            <option value="res-1r">Resistor 1Ω</option>
            <option value="res-33k">Resistor 33k</option>
            <option value="res-820r">Resistor 820Ω</option>
            <option value="res-15k">Resistor 15k</option>
            <option value="res-1m2">Resistor 1M2</option>
            <option value="res-5k6">Resistor 5k6</option>
            <option value="res-3k3">Resistor 3k3</option>
            <option value="res-1m5">Resistor 1M5</option>
            <option value="res-22k">Resistor 22k</option>
            <option value="res-120k">Resistor 120k</option>
            <option value="res-220r">Resistor 220Ω</option>
            <option value="res-100k">Resistor 100k</option>
            <option value="res-680r">Resistor 680R</option>
            <option value="res-8k2">Resistor 8k2</option>
            <option value="res-1k">Resistor 1k</option>
            <option value="res-71k5">Resistor 71.5k</option>
            <option value="res-82k">Resistor 82k</option>
            <option value="res-27r">Resistor 27Ω</option>
            <option value="res-33r">Resistor 33Ω</option>
            <option value="res-18k">Resistor 18k</option>
        </optgroup>

        <!-- Diodos -->
        <optgroup label="Diodos">
            <option value="diodo">Diodo</option>
            <option value="diodo-zener">Diodo Zener</option>
            <option value="diodo-1n914">Diodo 1N914</option>
        </optgroup>

        <!-- Transistores -->
        <optgroup label="Transistores">
            <option value="transistor">Transistor</option>
            <option value="transistor-npn">Transistor NPN</option>
            <option value="transistor-pnp">Transistor PNP</option>
            <option value="transistores-genericos">Transistores genéricos</option>
            <option value="transistor-potencia">Transistor de potência</option>
        </optgroup>

        <!-- Passivos -->
        <optgroup label="Passivos, Bobinas e Cabos">
            <option value="carretel-bobinas">Carretel de bobinas</option>
            <option value="bobina-inducao">Bobina de indução</option>
            <option value="fio-esmaltado">Rolo de fio de cobre esmaltado</option>
            <option value="ldr">LDR</option>
            <option value="capas-teclado">Capas de teclado</option>
            <option value="fios">Fios</option>
            <option value="tripot-voltagem">Tripot de voltagem</option>
            <option value="cabo-mdm">Cabo MDM</option>
        </optgroup>

        <!-- Componentes Diversos -->
        <optgroup label="Componentes Diversos">
            <option value="voltimetro">Voltímetro</option>
            <option value="multimetro">Multímetro</option>
            <option value="contador">Contador</option>
            <option value="conector-bnc">Conector BNC</option>
            <option value="conector-rede">Conector de cabo de rede</option>
            <option value="conector-borne">Conector borne</option>
            <option value="conector-dc">Conector de alimentação DC</option>
            <option value="conversor-boost">Conversor boost</option>
            <option value="conversor-voltagem">Conversor de voltagem</option>
            <option value="transformador">Transformador</option>
            <option value="protoboard">Protoboard</option>
            <option value="fonte">Fonte</option>
            <option value="fonte-sol">Fonte de Sol</option>
            <option value="fonte-chaveada">Fonte chaveada</option>
            <option value="oscilador">Oscilador</option>
            <option value="ressonador">Ressonador</option>
            <option value="valvula">Válvula</option>
            <option value="valvula-8pinos">Válvula de 8 pinos</option>
            <option value="cabeca-magnetica">Cabeça magnética</option>
            <option value="cpu">CPU</option>
            <option value="teclado-silicone">Teclado de silicone</option>
            <option value="pcb">Placa / PCB</option>
            <option value="termostato">Termostato</option>
            <option value="sis-integrado">Sistema integrado não identificado</option>
            <option value="motor">Motor</option>
            <option value="porta-fusivel">Porta-fusível</option>
            <option value="rele-schrack">Relé de potência Schrack RP510024</option>
            <option value="tda">TDA</option>
        </optgroup>
    </select>
</div>


<!-- ======================== FERRAMENTAS =========================== -->

<div class="form-group full-width">
    <label>Ferramentas</label>
    <select id="itemEmprestadoFerramentas" required>
        <option value="">Selecione</option>
        <option value="nenhum">Nenhum empréstimo</option>

        <optgroup label="Ferramentas">
            <option value="alicate-amperimetro">Alicate amperímetro</option>
            <option value="alicate-corte">Alicate de corte</option>
            <option value="alicate-rebitador">Alicate rebitador</option>
            <option value="alicate-universal">Alicate universal</option>
            <option value="alicates-normais">Alicates normais</option>
            <option value="apoio-ferro-solda">Apoiador de ferro de solda</option>
            <option value="descador">Descador</option>
            <option value="ferro-solda">Ferro de solda</option>
            <option value="fita-veda-rosca">Rolo de fita veda rosca</option>
            <option value="furador">Furador</option>
            <option value="furadores-placa">Furadores de placa</option>
            <option value="kit-ferramentas">Kit de ferramentas</option>
            <option value="kit-lab-educacional">Kit de laboratório educacional</option>
            <option value="mini-molas">Mini molas</option>
            <option value="molas">Molas</option>
            <option value="pacote-fixador">Pacote de fixador</option>
            <option value="paquimetro">Paquímetro</option>
            <option value="parafusos">Parafusos</option>
            <option value="pinca">Pinça</option>
            <option value="porcas">Porcas</option>
            <option value="pregos">Pregos</option>
            <option value="terminais">Terminais</option>
            <option value="sugador-solda">Sugador de solda</option>
        </optgroup>
    </select>
</div>



<!-- ======================== EQUIPAMENTOS =========================== -->

<div class="form-group full-width">
    <label>Equipamentos</label>
    <select id="itemEmprestadoEquipamentos" required>
        <option value="">Selecione</option>
        <option value="nenhum">Nenhum empréstimo</option>

        <optgroup label="Equipamentos">
            <option value="caixa-disjuntor">Caixa de disjuntor</option>
            <option value="cooler">Cooler</option>
            <option value="fio-rede">Fio de rede</option>
            <option value="rele">Relé</option>
            <option value="rele-estado-solido">Relé de estado sólido</option>
        </optgroup>
    </select>
</div>

      <div class="form-group">
        <label>Data do Empréstimo</label>
        <input type="date" id="emprestimo" required>
      </div>
      <div class="form-group full-width">
        <button type="submit">Cadastrar</button>
      </div>
    </form>
  </section>

  <!-- Detalhes do Produto -->
  <section id="detalhes" style="display:none;">
    <div class="detalhes-container">
      <h2 id="detalhes-nome"></h2>
      <div class="detalhes-flex">
        <img id="detalhes-img" src="" alt="">
        <div id="detalhes-info" class="detalhes-info"></div>
      </div>
      <button onclick="showPage(lastPage)">⬅ Voltar</button>
    </div>
  </section>
</main>

<footer>© 2025 Almoxarifado ETEC - Projeto TCC</footer>

<script>
const images = document.querySelectorAll('.carousel img');
let current = 0;
setInterval(nextImage, 5000);

function showPage(pageId) {
  document.querySelectorAll('main section').forEach(s => s.style.display = 'none');
  document.getElementById(pageId).style.display = 'block';
}

function nextImage() {
  images[current].style.opacity = 0;
  current = (current + 1) % images.length;
  images[current].style.opacity = 1;
}
function prevImage() {
  images[current].style.opacity = 0;
  current = (current - 1 + images.length) % images.length;
  images[current].style.opacity = 1;
}

let lastPage = "inicio";

// Produtos
const componentes = {

"Ampola reed switch": { qtd: 42, voltagem:" 100V a 350V", corrente:"0,5A a 1A ", funcao:"Interromper ou permitir a passagem de corrente elétrica em um circuito ", desc:"interruptor magnético selado que fecha um circuito elétrico na presença de um campo magnético.", img:"https://images.tcdn.com.br/img/img_prod/900872/ampola_reed_2x14_na_1979_1_fdb4ff34ce7fcaf0ca7940c5dc536318_20250818175717.png" },

"Bobina de indução": { qtd: "30", voltagem:"110V ou 220V", funcao:"Armazena energia em um campo magnético e controla a passagem de corrente em circuitos elétricos e eletrônicos", desc:"Componente que gera campo magnético ao receber corrente, usado para filtrar sinais e armazenar energia", img:"https://http2.mlstatic.com/D_NQ_NP_2X_982093-CBT80119321847_102024-T-bobina-de-induco-de-placa-de-aquecimento-dc5-120v-grande-e.webp" },

"Botões de Comando": { qtd: 5, voltagem:"125V / 250V AC", corrente:"125V / 250V AC", funcao:"acionar, interromper ou controlar uma função elétrica ou eletrônica em um equipamento ou circuito.", desc:"usado para acionar ou interromper funções elétricas ao ser pressionado.", img:"https://images.tcdn.com.br/img/img_prod/717867/botao_de_comando_saliente_metalico_22_5mm_220v_679_1_23cec9700e5deff490b56014bf433318_20251006165400.jpg" },

"Cabeças magnéticas": { qtd: 18, voltagem:"3V e 12V", corrente:"5 mA e 20 mA", funcao:"Ler e gravar dados em superfícies magnéticas.", desc:"Usadas para leitura e gravação em fitas ou discos magnéticos.", img:"https://http2.mlstatic.com/D_982055-MLB74754820846_032024-C.jpg" },

"Carretel de bobinas": { qtd: 27, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Chaves alavanca": { qtd: 44, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Conectores BNC": { qtd: 5, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Conectores borne": { qtd: 19, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Conectores de alimentação DC": { qtd: 9, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Conectores de cabo de rede": { qtd: 3, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Contadores": { qtd: 3, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Controles RGB": { qtd: 2, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Conversor boost": { qtd: 1, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Conversores de voltagem": { qtd: 2, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"CPUs": { qtd: 2, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Diode 1N914": { qtd: "4 pacotes", voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Diodo (genérico)": { qtd: null, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Diodo Zener": { qtd: "20 pacotes", voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Display grande": { qtd: 5, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Display pequeno": { qtd: "5+", voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Displays de 7 segmentos": { qtd: 4, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Fonte chaveada": { qtd: 1, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Fonte de Sol": { qtd: 1, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Fontes": { qtd: 19, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Interruptor mestre de lâmina de canivete": { qtd: 3, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Interruptores": { qtd: 31, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"LCD com botão": { qtd: 1, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"LCD com fio": { qtd: 5, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"LCD grande sem fio": { qtd: 6, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"LCD pequeno sem fio": { qtd: 1, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"LCD pequeno sem fio quebrado": { qtd: 3, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" }
,
"LED 10mm Amarelo": { qtd:"", voltagem:"2V", corrente:"20mA", funcao:"Emissor de luz amarela de alto brilho.", desc:"", img:"https://http2.mlstatic.com/...webp" },

"LED 10mm Branco": { qtd:"", voltagem:"3V", corrente:"20mA", funcao:"Emissor de luz branca.", desc:"", img:"imagens/led_branco10.jpg" },

"LED 10mm Verde": { qtd:"", voltagem:"2V", corrente:"20mA", funcao:"Emissor de luz verde de alto brilho.", desc:"", img:"https://mvelectronica.s3.us-east-2.amazonaws.com/...webp" },

"LED 10mm Vermelho": { qtd:"", voltagem:"2V", corrente:"20mA", funcao:"Emissor de luz vermelha de alto brilho.", desc:"", img:"https://encrypted-tbn0.gstatic.com/...jpg" },

"LED 3mm Amarelo": { qtd:"", voltagem:"2V", corrente:"20mA", funcao:"Emissor de luz.", desc:"", img:"imagens/led_branco10.jpg" },

"LED 3mm Azul": { qtd:"", voltagem:"3V", corrente:"20mA", funcao:"Emissor de luz azul.", desc:"", img:"imagens/led_branco10.jpg" },

"LED 3mm Branco": { qtd:"", voltagem:"3V", corrente:"20mA", funcao:"Emissor de luz branca.", desc:"", img:"imagens/led_branco10.jpg" },

"LED 3mm Verde": { qtd:"", voltagem:"2V", corrente:"20mA", funcao:"Emissor de luz.", desc:"", img:"imagens/led_branco10.jpg" },

"LED 3mm Vermelho": { qtd:"", voltagem:"2V", corrente:"20mA", funcao:"Emissor de luz.", desc:"", img:"imagens/led_branco10.jpg" },

"LED 5mm Amarelo": { qtd:"", voltagem:"2V", corrente:"20mA", funcao:"Emissor de luz amarela.", desc:"Comum em indicadores luminosos.", img:"https://cdn.awsli.com.br/...jpg" },

"LED 5mm Azul": { qtd:"", voltagem:"3V", corrente:"20mA", funcao:"Emissor de luz azul.", desc:"Usado em decoração e sinalização técnica.", img:"https://backend.ryndackcomponentes.com.br/...jpg" },

"LED 5mm Branco": { qtd:"", voltagem:"3V", corrente:"20mA", funcao:"Emissor de luz branca.", desc:"Usado em projetos eletrônicos e iluminação.", img:"imagens/led_branco10.jpg" },

"LED 5mm Verde": { qtd:"", voltagem:"2V", corrente:"20mA", funcao:"Emissor de luz verde.", desc:"Utilizado em projetos eletrônicos e sinalizações.", img:"https://cdn.awsli.com.br/...jpg" },

"LED 5mm Vermelho": { qtd:"", voltagem:"2V", corrente:"20mA", funcao:"Emissor de luz.", desc:"Usado em sinalização e indicadores.", img:"https://backend.ryndackcomponentes.com.br/media/catalog/product/1/0/1090.jpg" },

"LED piranha azul": { qtd: 20, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"LED piranha verde": { qtd: 20, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"LED piranha vermelho": { qtd: 20, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Lâmpada incandescente 150W": { qtd: 1, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Lâmpada indicadora 40mA": { qtd: 7, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Lâmpada LBT 36W": { qtd: 5, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Lâmpada LED 3W": { qtd: 3, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Lâmpada para amplificador": { qtd: 12, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Lâmpada teleslide 12V": { qtd: 8, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Lâmpada torpedo 42mm": { qtd: 5, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Motores": { qtd: 2, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Multímetros": { qtd: 13, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Osciladores": { qtd: 29, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Placas / PCBs": { qtd: 13, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Porta-fusível": { qtd: 84, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Potenc. 10k": { qtd: 4, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Potenc. 10M": { qtd: 3, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Potenc. 100k": { qtd: 3, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Potenc. 1k": { qtd: 3, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Potenc. 1M": { qtd: 7, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Potenc. 20k": { qtd: 1, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Potenc. 220k": { qtd: 4, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Potenc. 250k": { qtd: 4, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Potenc. 2k": { qtd: 1, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Potenc. 2M": { qtd: 1, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Potenc. 4 ohms": { qtd: 1, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Potenc. 4k": { qtd: 1, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Potenc. 470k": { qtd: 4, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Potenc. 470R": { qtd: 2, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Potenc. 50 ohms": { qtd: 1, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Potenc. 50k": { qtd: 6, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Potenc. 500k": { qtd: 1, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Potenc. 5k": { qtd: 5, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Potenciômetros duplos": { qtd: 4, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Protoboards": { qtd: 8, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Push buttons com trava": { qtd: 14, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Push buttons comuns": { qtd: 144, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Relé de potência Schrack RP510024": { qtd: 3, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Resistor 100k": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Resistor 120k": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Resistor 15k": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Resistor 18k": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Resistor 1k": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Resistor 1M2": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Resistor 1M5": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Resistor 1Ω": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Resistor 220Ω": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Resistor 22k": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Resistor 27Ω": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Resistor 33k": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Resistor 33Ω": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Resistor 3k3": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Resistor 5k6": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Resistor 680R": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Resistor 71.5k": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Resistor 820Ω": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Resistor 82k": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Resistor 8k2": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Ressonadores": { qtd: 36, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Sistema integrado não identificado": { qtd: 600, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"TDA": { qtd: 100, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Teclado de silicone": { qtd: 15, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Termostatos": { qtd: 5, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Transformador": { qtd: 1, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Transistor (genérico)": { qtd: null, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Transistor NPN": { qtd: 350, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Transistor PNP": { qtd: 300, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Transistor de potência": { qtd: null, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Transistores genéricos": { qtd: 150, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Válvulas": { qtd: 27, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Válvulas de 8 pinos": { qtd: 9, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Voltímetros": { qtd: 17, voltagem:".", corrente:".", funcao:".", desc:".", img:".jpg" }

};

const equipamentos = {
 
"Caixas de disjuntor": {
  voltagem:"",
  corrente:"",
  funcao:"Protege e organiza disjuntores.",
  desc:"Caixas para instalação de disjuntores residenciais ou industriais.",
  img:"imagens/caixa_disjuntor.jpg",
  quantidade:3
},

"Carretel de bobinas": { 
  qtd: 27,
  funcao:".", 
  desc:"", 
  img:".jpg" 
},

"Chaves alavanca": {
  voltagem:"",
  corrente:"",
  funcao:"Liga e desliga circuitos por meio de alavanca.",
  desc:"Chaves robustas usadas em painéis e equipamentos.",
  img:"imagens/chave_alavanca.jpg",
  quantidade:44
},

"Coolers": {
  voltagem:"",
  corrente:"",
  funcao:"Resfria equipamentos eletrônicos.",
  desc:"Coolers diversos para refrigeração de circuitos.",
  img:"imagens/cooler.jpg",
  quantidade:10
},

"Fio de rede": {
  voltagem:"44 V a 57 V",
  funcao:"Transmite sinais de rede.",
  desc:"Cabo de rede para conexão Ethernet.",
  img:"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQbT8V_16axNmDqBAFe5LdmuKcBneQrQ50DAQ&s",
  quantidade:1
},

"Relés 2 canais": {
  voltagem:"5VDC, 12VDC, 24VDC",
  corrente:"10A, 25A, 40A",
  funcao:"Comuta circuitos usando sinais elétricos.",
  desc:"Relés eletromecânicos convencionais.",
  img:"https://cdn.awsli.com.br/300x300/468/468162/produto/19414409/106e8da5c7.jpg",
  quantidade:6
},

"Relés de estado sólido": {
  voltagem:"24-480 VAC",
  corrente:"Entrada: 3-32 VDC Saída: 10A-100A ",
  funcao:"Comuta circuitos eletrônicos sem partes móveis.",
  desc:"Relé eletrônico de alta velocidade e longa durabilidade.",
  img:"imagens/relé_estado_solido.jpg",
  quantidade:2
}

};

const ferramentas = {
"Alicate amperímetro": {
  Quant:"",  
  funcao:"Mede corrente elétrica.",
  desc:"Ferramenta utilizada para medições rápidas.",
  img:"https://daxonart8aj4m.cloudfront.net/Custom/Content/Products/25/12/25123_48655-multmetro-digital-com-alicate-ampermetro_z1_638656597941271093.webp"
},

"Alicate de corte": {
  Quant:"",
  funcao:"Corta fios e terminais.",
  desc:"Ferramenta de corte para eletrônica.",
  img:"https://antferramentas.vtexassets.com/arquivos/ids/161906-800-auto?v=635857862083600000&width=800&height=auto&aspect=true"
},

"Alicate rebitador": {
  Quant:"",
  funcao:"Aplica rebites.",
  desc:"Usado para fixação mecânica.",
  img:"https://img.irroba.com.br/fit-in/600x600/filters:fill(fff):quality(80)/hidrauli/catalog/api/hidrauli_citelirr/62cdbe315fcb2.jpg"
},

"Alicate Universal": {
  Quant:"",
  funcao:"Aperta, corta e dobra fios.",
  desc:"Ferramenta multiuso para eletricista.",
  img:"https://www.dutramaquinas.com.br/shared/img/produto/alta/144969_alicate_universal_isolado_aco_cromo_vanadio_8.webp"
},

"Apoiador de ferro de solda": {
  Quant:"",
  funcao:"Suporta o ferro de solda aquecido.",
  desc:"Evita acidentes e queimaduras.",
  img:"https://http2.mlstatic.com/D_Q_NP_939810-MLA93087988986_092025-O.webp"
},

"Descapadores": {
  Quant:"",
  funcao:"Remove isolamento de fios.",
  desc:"Indispensável para montagem eletrônica.",
  img:"https://http2.mlstatic.com/D_Q_NP_928816-MLU76716505754_062024-O.webp"
},

"Ferros de solda": {
  Quant:"", 
  funcao:"Realiza soldagem eletrônica.",
  desc:"Ferramenta aquecida para soldar componentes.",
  img:"https://cdn.awsli.com.br/757/757427/produto/38811943/3caabcdaf6.jpg"
},

"Furador": {
  Quant:"", 
  funcao:"Fura materiais diversos.",
  desc:"Ferramenta para pequenos furos em PCB.",
  img:"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTZjMkz5LeLJ0MyjvoMtcxvBvf6RckecQJux67nZhRt7ln9XuadCVPqquV0zzJyHqxwCX4&usqp=CAU"
},

"Furadores de placa": {
  Quant:"",
  funcao:"Fura placas de circuito.",
  desc:"Serve para criar furos em placas de fenolite.",
  img:"https://images.tcdn.com.br/img/img_prod/751846/perfurador_de_placa_de_circuito_impresso_2069_2_e454488580eac336426b0e2b9148b059_20240418040229.jpg"
},

"Interruptor mestre de lâmina de canivete": {
  Quant:"", 
  funcao:"Liga e desliga circuitos.",
  desc:"Interruptor estilo chave de lâmina.",
  img:"imagens/interruptor_lamina.jpg"
},

"Kit de ferramentas": {
  Quant:"",
  funcao:"Conjunto variado de ferramentas.",
  desc:"Contém itens básicos para manutenção.",
  img:"https://cdn.awsli.com.br/600x700/1551/1551409/produto/222240738/14011-xeizfso8ea.jpg"
},

"Kit de laboratório educacional": {
  Quant:"",
  funcao:"Suporte para estudos em eletrônica.",
  desc:"Inclui ferramentas e componentes diversos.",
  img:"imagens/kit_laboratorio.jpg"
},

"Mini molas": {
  Quant:"",
  funcao:"Retorno mecânico leve.",
  desc:"Aplicadas em peças pequenas.",
  img:"https://m.media-amazon.com/images/I/51JkMJUA-yL._SL1100_.jpg"
},

"Molas": {
  Quant:"",
  funcao:"Pressão mecânica.",
  desc:"Usadas em mecanismos gerais.",
  img:"https://ae01.alicdn.com/kf/S1a048f293d8e4b77b9fb9e6dc7c9c21aG.jpg"
},

"Pacote de fixador": {
  Quant:"",
  funcao:"Seguro de peças e componentes.",
  desc:"Conjunto de fixadores diversos.",
  img:"https://http2.mlstatic.com/D_NQ_NP_821406-MLA92549119152_092025-O.webp"
},

"Paquímetro": {
  Quant:"",
  funcao:"Mede dimensões com precisão.",
  desc:"Ferramenta de medição milimétrica.",
  img:"https://www.paraflex.com.br/wp-content/uploads/2022/12/paquimetro-aco.webp"
},


"Pinça": {
  Quant:"1",
  funcao:"Segura pequenos componentes.",
  desc:"Usada em SMD e eletrônica fina.",
  img:"https://images.tcdn.com.br/img/img_prod/1231250/pinca_adson_reta_18cm_2621_1_6783523b959b6d46f6e2d92f97b727c9.jpg"
},

"Porcas e Parafusos": {
  Quant:"",
  funcao:"Fixação com parafusos.",
  desc:"Porcas metálicas para montagem.",
  img:"https://www.amimetalurgica.com.br/wp-content/uploads/2018/01/parafusos.png"
},

"Pregos": {
  Quant:"",
  funcao:"Fixação mecânica.",
  desc:"Usados para prender materiais.",
  img:"https://images.tcdn.com.br/img/img_prod/765502/prego_3x8_1kg_12373_1_058d3d0f928a54a02e07a49badb7f610.jpg"
},

"Rolo de fita veda rosca": {
  Quant:"",
  funcao:"Veda conexões roscadas.",
  desc:"Usado em encanamento e vedação geral.",
  img:"https://img.irroba.com.br/fit-in/600x600/filters:fill(fff):quality(80)/atacadoz/catalog/api/atacadoz_integrac/67bcd0633f094.jpg" 
},

"Sugadores de solda": {
  Quant:"",
  funcao:"Remove solda derretida.",
  desc:"Utilizado para retrabalho em placas.",
  img:"https://www.sotudo.com.br/imagens/produtos/m/16175_1.jpg"
},

"Terminais": {
  Quant:"",
  funcao:"Conecta fios e componentes.",
  desc:"Diversos tipos de terminais elétricos.",
  img:"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQYWqTQ39h1nAYup2qOD2BFCgwSkZgaoCLYCA&s"
}

};

function fillList(id, items) {
  const container = document.getElementById(id);
  container.innerHTML = '';
  Object.entries(items).forEach(([nome, info]) => {
    const div = document.createElement('div');
    div.className = 'card';
    div.innerHTML = `<h3>${nome}</h3><div class="tooltip">${info.desc}</div>`;
    div.onclick = () => showDetalhes(nome, info, id);
    container.appendChild(div);
  });
}

fillList('componentes-list', componentes);
fillList('equipamentos-list', equipamentos);
fillList('ferramentas-list', ferramentas);

function showDetalhes(nome, info, origem) {
  lastPage = origem.replace('-list', '');
  document.getElementById('detalhes-nome').textContent = nome;
  document.getElementById('detalhes-img').src = info.img;
  const infoDiv = document.getElementById('detalhes-info');
  infoDiv.innerHTML = '';
  if(info.voltagem) infoDiv.innerHTML += `<div><strong>Voltagem:</strong> ${info.voltagem}</div>`;
  if(info.corrente) infoDiv.innerHTML += `<div><strong>Corrente:</strong> ${info.corrente}</div>`;
  if(info.funcao) infoDiv.innerHTML += `<div><strong>Função:</strong> ${info.funcao}</div>`;
  if(info.desc) infoDiv.innerHTML += `<div><strong>Descrição:</strong> ${info.desc}</div>`;
  showPage('detalhes');
}

// Cadastro
function saveCadastro(event) {
  event.preventDefault();
  const nome = document.getElementById('nome').value;
  const tipo = document.getElementById('tipoUsuario').value;
  const email = document.getElementById('email').value;
  const rm = document.getElementById('rm').value;
  const serie = document.getElementById('serie').value;
  const curso = document.getElementById('curso').value;
  const item = document.getElementById('itemEmprestado').value;
  const emprestimo = document.getElementById('emprestimo').value;
  const cadastro = { nome, tipo, email, rm, serie, curso, item, emprestimo };
  let cadastros = JSON.parse(localStorage.getItem('cadastros') || '[]');
  cadastros.push(cadastro);
  localStorage.setItem('cadastros', JSON.stringify(cadastros));
  alert('Cadastro salvo com sucesso!');
  document.getElementById('cadastroForm').reset();
}

function toggleCamposUsuario() {
  const tipo = document.getElementById('tipoUsuario').value;
  const mostrar = tipo === 'aluno' || tipo === 'modular';
  document.getElementById('rmDiv').style.display = mostrar ? 'block' : 'none';
  document.getElementById('serieDiv').style.display = mostrar ? 'block' : 'none';
  document.getElementById('cursoDiv').style.display = mostrar ? 'block' : 'none';
}

// Pesquisa
function filterItems() {
  const search = document.getElementById('search').value.toLowerCase();
  ['componentes','equipamentos','ferramentas'].forEach(id => {
    const container = document.getElementById(id + '-list');
    container.querySelectorAll('.card').forEach(card => {
      card.style.display = card.textContent.toLowerCase().includes(search) ? 'block' : 'none';
    });
  });
}
</script>
</body>
</html>
