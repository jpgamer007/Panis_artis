<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta name="theme-color" content="#f3e7d0">
  <meta name="description" content="Panis Artis — arte em forma de pão. Delícias artesanais feitas com carinho.">
  <title>Panis Artis | Arte em forma de pão</title>

  <style>
    :root {
      --papel: #f3e7d0;
      --marrom: #4b2c1c;
      --detalhe: #a7825d;
      --claro: #fff8eb;
      --texto: #795b45;
    }

    * {
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      margin: 0;
      background: var(--papel);
      color: var(--marrom);
      font-family: Georgia, "Times New Roman", serif;
      background-image: repeating-linear-gradient(
        2deg,
        transparent,
        transparent 5px,
        rgba(75, 44, 28, 0.025) 6px
      );
    }

    header {
      text-align: center;
      padding: 35px 15px 20px;
    }

    .logo {
      border: 2px solid var(--marrom);
      border-radius: 50%;
      width: 85px;
      height: 85px;
      margin: auto;
      display: grid;
      place-items: center;
      font-size: 35px;
      font-weight: bold;
      box-shadow:
        inset 0 0 0 4px var(--papel),
        inset 0 0 0 5px var(--marrom);
    }

    h1 {
      font-size: clamp(30px, 7vw, 48px);
      letter-spacing: 3px;
      margin: 15px 0 5px;
    }

    .slogan {
      font-style: italic;
      color: var(--texto);
    }

    nav {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      gap: 22px;
      padding: 12px;
      border-top: 1px solid var(--detalhe);
      border-bottom: 1px solid var(--detalhe);
    }

    nav a {
      color: var(--marrom);
      text-decoration: none;
    }

    nav a:hover {
      text-decoration: underline;
    }

    hr {
      border: 0;
      border-top: 1px solid var(--detalhe);
      max-width: 400px;
      margin: 18px auto;
    }

    h2 {
      text-align: center;
      font-size: 30px;
      font-style: italic;
      font-weight: normal;
    }

    .intro {
      text-align: center;
      line-height: 1.7;
      padding: 0 18px;
      color: var(--texto);
      max-width: 650px;
      margin: auto;
    }

    main {
      max-width: 1000px;
      margin: 25px auto;
      padding: 0 16px;
    }

    /* ===== Catálogo ===== */
    .catalog {
      display: grid;
      grid-template-columns: repeat(
        auto-fit,
        minmax(min(100%, 240px), 1fr)
      );
      gap: 18px;
    }

    .product,
    .panel {
      background: rgba(255, 248, 235, 0.75);
      border: 1px solid #c7aa86;
      padding: 17px;
      box-shadow: 0 4px 12px rgba(75, 44, 28, 0.07);
    }

    .product {
      padding: 0;
      text-align: center;
      display: flex;
      flex-direction: column;
      overflow: hidden;
    }

    /* Moldura da foto: proporção igual para todos os cartões */
    .product-photo {
      aspect-ratio: 4 / 3;
      background: #eadbbf;
      border-bottom: 1px solid #c7aa86;
      overflow: hidden;
    }

    .product-photo img {
      display: block;
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    /* Espaço reservado enquanto a foto real não foi enviada */
    .photo-placeholder {
      width: 100%;
      height: 100%;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      gap: 10px;
      color: var(--detalhe);
      font-style: italic;
      font-size: 15px;
    }

    .photo-placeholder span:first-child {
      display: grid;
      place-items: center;
      width: 46px;
      height: 46px;
      border: 1px solid var(--detalhe);
      border-radius: 50%;
      font-style: normal;
      font-weight: bold;
      font-size: 17px;
      box-shadow: inset 0 0 0 3px #eadbbf, inset 0 0 0 4px var(--detalhe);
    }

    .product-body {
      display: flex;
      flex-direction: column;
      flex: 1;
      padding: 16px 17px 18px;
    }

    .product h3 {
      font-size: 22px;
      font-weight: normal;
      margin: 0 0 8px;
    }

    .product p {
      color: var(--texto);
      line-height: 1.5;
      margin: 0;
      flex: 1;
    }

    .price {
      font-size: 21px;
      font-weight: bold;
      margin: 14px 0 12px;
    }

    .product button {
      width: 100%;
      margin: 0;
    }

    button {
      padding: 11px 15px;
      border: 1px solid var(--marrom);
      background: var(--marrom);
      color: var(--papel);
      font: inherit;
      cursor: pointer;
      margin: 4px;
    }

    button.secondary {
      background: transparent;
      color: var(--marrom);
    }

    button:hover {
      opacity: 0.85;
    }

    button:focus-visible,
    a:focus-visible {
      outline: 3px solid var(--detalhe);
      outline-offset: 3px;
    }

    /* ===== Pedido ===== */
    .panel {
      margin-top: 24px;
    }

    .panel h2 {
      margin-top: 4px;
    }

    .empty {
      text-align: center;
      color: var(--texto);
      padding: 15px 0;
    }

    .cartrow {
      display: grid;
      grid-template-columns: 1fr auto auto;
      align-items: center;
      gap: 10px;
      padding: 12px 0;
      border-bottom: 1px dotted #c7aa86;
    }

    .qty {
      display: flex;
      align-items: center;
      gap: 5px;
    }

    .qty button {
      padding: 3px 10px;
      margin: 0;
    }

    .remove {
      background: transparent;
      color: #853b2c;
      border: 0;
      padding: 4px;
    }

    .total {
      display: flex;
      justify-content: space-between;
      gap: 12px;
      font-size: 23px;
      margin: 20px 0;
      padding-top: 15px;
      border-top: 2px solid var(--detalhe);
    }

    .wide {
      width: 100%;
      margin: 5px 0;
    }

    #payment {
      display: none;
      text-align: center;
      border-top: 1px solid var(--detalhe);
      margin-top: 25px;
      padding-top: 20px;
    }

    #payment.visible {
      display: block;
    }

    #qrcode {
      display: flex;
      justify-content: center;
      margin: 18px auto;
      min-height: 10px;
    }

    #pixCode {
      width: 100%;
      min-height: 100px;
      padding: 10px;
      background: var(--claro);
      color: var(--marrom);
      border: 1px solid var(--detalhe);
      overflow-wrap: anywhere;
    }

    .notice {
      font-size: 14px;
      line-height: 1.6;
      color: var(--texto);
    }

    /* ===== Nossa história ===== */
    .about {
      max-width: 700px;
      margin: 50px auto;
      padding: 20px;
      text-align: center;
      line-height: 1.7;
    }

    .about h3 {
      font-size: 21px;
      font-style: italic;
      font-weight: normal;
      color: var(--texto);
      margin: 0 0 18px;
    }

    .about p {
      margin: 0 0 16px;
    }

    footer {
      text-align: center;
      padding: 30px 12px;
      font-style: italic;
      color: var(--texto);
      border-top: 1px solid var(--detalhe);
      background: rgba(167, 130, 93, 0.08);
    }

    @media (max-width: 560px) {
      nav {
        gap: 12px;
      }

      .cartrow {
        grid-template-columns: 1fr auto;
      }

      .cartrow .remove {
        grid-column: 1 / -1;
        justify-self: end;
      }
    }
  </style>
</head>

<body>
  <header id="inicio">
    <div class="logo" aria-label="Logotipo Panis Artis">PA</div>
    <h1>Panis Artis</h1>
    <p class="slogan">Arte em forma de pão</p>
    <hr>
    <p class="intro">
      Feito à mão, com carinho e dedicação.
      Descubra nossas delícias artesanais e escolha suas favoritas.
    </p>
  </header>

  <nav aria-label="Navegação principal">
    <a href="#inicio">Início</a>
    <a href="#produtos">Produtos</a>
    <a href="#pedido" id="navPedido">Meu pedido</a>
    <a href="#historia">Nossa história</a>
  </nav>

  <main>
    <section id="produtos">
      <h2>Nossas delícias</h2>
      <p class="intro">
        Cada receita é preparada com cuidado para deixar seu dia mais gostoso.
      </p>
      <hr>
      <div class="catalog" id="catalog"></div>
    </section>

    <section class="panel" id="pedido">
      <h2>Seu pedido</h2>

      <div id="cartItems">
        <p class="empty">
          Seu cesto está vazio. Escolha uma delícia do nosso catálogo!
        </p>
      </div>

      <div class="total">
        <span>Total</span>
        <strong id="total">R$ 0,00</strong>
      </div>

      <button class="wide" onclick="startPayment()">
        Gerar Pix do pedido
      </button>

      <button class="wide secondary" onclick="copyOrder()">
        Copiar resumo do pedido
      </button>

      <button class="wide secondary" onclick="clearCart()">
        Limpar cesto
      </button>

      <div id="payment">
        <h2>Pagamento por Pix</h2>
        <p>Valor do pedido: <strong id="paymentTotal"></strong></p>

        <div id="qrcode"></div>

        <p>Escaneie o QR Code usando o aplicativo do seu banco.</p>
        <p class="notice">Ou copie o código Pix abaixo:</p>

        <textarea
          id="pixCode"
          readonly
          aria-label="Código Pix copia e cola"
        ></textarea>

        <button onclick="copyPix()">Copiar código Pix</button>

        <p class="notice">
          Após pagar, envie o resumo do pedido à Panis Artis.
          O pagamento será conferido manualmente antes da entrega.
          Aguarde a confirmação do recebimento.
        </p>
      </div>
    </section>

    <section class="about" id="historia">
      <h2>Nossa história</h2>
      <hr>
      <h3>Um sonho que ganhou forma a cada fornada</h3>

      <p>A Panis Artis nasceu de um sonho: o desejo de participar do PHN.</p>

      <p>
        O que começou como uma vontade pessoal acabou se transformando em
        algo muito maior. A partir da ideia de produzir e vender pães
        artesanais, surgiu a oportunidade de unir trabalho, dedicação e
        propósito em um só projeto.
      </p>

      <p>
        Com o apoio da família, cada pão passou a representar não apenas um
        produto feito artesanalmente, mas também um passo em direção à
        realização de um sonho.
      </p>

      <p>
        Assim nasceu a Panis Artis: de um desejo que se transformou em
        iniciativa, de uma iniciativa que se tornou trabalho e de um
        trabalho feito com carinho, dedicação e fé.
      </p>
    </section>
  </main>

  <footer>
    <strong>Panis Artis</strong>
    <p>Arte em forma de pão.</p>
    <p>© <span id="year"></span> Panis Artis</p>
  </footer>

  <script>
    /* ===== Gerador de QR Code embutido (modo byte, correção M, versões 1 a 10) =====
       Não depende de nenhum site externo. Cria um SVG dentro do elemento informado. */
    var QRCode = (function () {
      // [dados totais, bytes de correção por bloco, blocos curtos, tamanho do bloco curto, blocos longos]
      var TABLE = {
        1:  [16, 10, 1, 16, 0],
        2:  [28, 16, 1, 28, 0],
        3:  [44, 26, 1, 44, 0],
        4:  [64, 18, 2, 32, 0],
        5:  [86, 24, 2, 43, 0],
        6:  [108, 16, 4, 27, 0],
        7:  [124, 18, 4, 31, 0],
        8:  [154, 22, 2, 38, 2],
        9:  [182, 22, 3, 36, 2],
        10: [216, 26, 4, 43, 1]
      };
      var ALIGN = {
        1: [], 2: [6, 18], 3: [6, 22], 4: [6, 26], 5: [6, 30], 6: [6, 34],
        7: [6, 22, 38], 8: [6, 24, 42], 9: [6, 26, 46], 10: [6, 28, 50]
      };

      // Aritmética de Galois (GF 256)
      var EXP = new Array(512), LOG = new Array(256);
      (function () {
        var x = 1;
        for (var i = 0; i < 255; i++) {
          EXP[i] = x;
          LOG[x] = i;
          x <<= 1;
          if (x & 0x100) x ^= 0x11D;
        }
        for (var j = 255; j < 512; j++) EXP[j] = EXP[j - 255];
      })();

      function gfMul(a, b) {
        if (a === 0 || b === 0) return 0;
        return EXP[LOG[a] + LOG[b]];
      }

      function generator(degree) {
        var poly = [1];
        for (var i = 0; i < degree; i++) {
          var next = new Array(poly.length + 1).fill(0);
          for (var j = 0; j < poly.length; j++) {
            next[j] ^= poly[j];
            next[j + 1] ^= gfMul(poly[j], EXP[i]);
          }
          poly = next;
        }
        return poly;
      }

      function reedSolomon(data, degree) {
        var gen = generator(degree);
        var result = new Array(degree).fill(0);
        for (var i = 0; i < data.length; i++) {
          var factor = data[i] ^ result[0];
          result.shift();
          result.push(0);
          for (var j = 0; j < degree; j++) {
            result[j] ^= gfMul(gen[j + 1], factor);
          }
        }
        return result;
      }

      function utf8Bytes(text) {
        var encoded = unescape(encodeURIComponent(text));
        var bytes = [];
        for (var i = 0; i < encoded.length; i++) bytes.push(encoded.charCodeAt(i));
        return bytes;
      }

      function buildCodewords(bytes, version) {
        var info = TABLE[version];
        var dataTotal = info[0];
        var bits = [];

        function push(value, length) {
          for (var i = length - 1; i >= 0; i--) bits.push((value >>> i) & 1);
        }

        push(4, 4); // modo byte
        push(bytes.length, version >= 10 ? 16 : 8);
        bytes.forEach(function (b) { push(b, 8); });

        var capacityBits = dataTotal * 8;
        push(0, Math.min(4, capacityBits - bits.length));
        while (bits.length % 8 !== 0) bits.push(0);

        var codewords = [];
        for (var i = 0; i < bits.length; i += 8) {
          var value = 0;
          for (var j = 0; j < 8; j++) value = (value << 1) | bits[i + j];
          codewords.push(value);
        }
        var pad = [0xEC, 0x11], p = 0;
        while (codewords.length < dataTotal) codewords.push(pad[p++ % 2]);

        // Divide em blocos e calcula a correção de erros
        var ecLen = info[1];
        var shortBlocks = info[2], shortSize = info[3], longBlocks = info[4];
        var blocks = [], ecs = [], pos = 0, b;
        for (b = 0; b < shortBlocks + longBlocks; b++) {
          var size = b < shortBlocks ? shortSize : shortSize + 1;
          var block = codewords.slice(pos, pos + size);
          pos += size;
          blocks.push(block);
          ecs.push(reedSolomon(block, ecLen));
        }

        var result = [];
        var maxSize = shortSize + (longBlocks ? 1 : 0);
        for (var k = 0; k < maxSize; k++) {
          for (b = 0; b < blocks.length; b++) {
            if (k < blocks[b].length) result.push(blocks[b][k]);
          }
        }
        for (var e = 0; e < ecLen; e++) {
          for (b = 0; b < ecs.length; b++) result.push(ecs[b][e]);
        }
        return result;
      }

      function bchFormat(data) {
        var rem = data;
        for (var i = 0; i < 10; i++) rem = (rem << 1) ^ ((rem >>> 9) * 0x537);
        return ((data << 10) | rem) ^ 0x5412;
      }

      function bchVersion(version) {
        var rem = version;
        for (var i = 0; i < 12; i++) rem = (rem << 1) ^ ((rem >>> 11) * 0x1F25);
        return (version << 12) | rem;
      }

      function maskFunction(mask, r, c) {
        switch (mask) {
          case 0: return (r + c) % 2 === 0;
          case 1: return r % 2 === 0;
          case 2: return c % 3 === 0;
          case 3: return (r + c) % 3 === 0;
          case 4: return (Math.floor(r / 2) + Math.floor(c / 3)) % 2 === 0;
          case 5: return ((r * c) % 2) + ((r * c) % 3) === 0;
          case 6: return (((r * c) % 2) + ((r * c) % 3)) % 2 === 0;
          default: return (((r + c) % 2) + ((r * c) % 3)) % 2 === 0;
        }
      }

      function makeMatrix(codewords, version, mask) {
        var size = version * 4 + 17;
        var modules = [], reserved = [], i, j;
        for (i = 0; i < size; i++) {
          modules.push(new Array(size).fill(false));
          reserved.push(new Array(size).fill(false));
        }

        function setFunction(r, c, dark) {
          if (r < 0 || c < 0 || r >= size || c >= size) return;
          modules[r][c] = dark;
          reserved[r][c] = true;
        }

        function finder(row, col) {
          for (var dr = -1; dr <= 7; dr++) {
            for (var dc = -1; dc <= 7; dc++) {
              var inside = dr >= 0 && dr <= 6 && dc >= 0 && dc <= 6;
              var dark = inside && (dr === 0 || dr === 6 || dc === 0 || dc === 6 ||
                (dr >= 2 && dr <= 4 && dc >= 2 && dc <= 4));
              setFunction(row + dr, col + dc, dark);
            }
          }
        }

        finder(0, 0);
        finder(0, size - 7);
        finder(size - 7, 0);

        for (i = 8; i < size - 8; i++) {
          setFunction(6, i, i % 2 === 0);
          setFunction(i, 6, i % 2 === 0);
        }

        var align = ALIGN[version];
        for (i = 0; i < align.length; i++) {
          for (j = 0; j < align.length; j++) {
            var skip = (i === 0 && j === 0) ||
                       (i === 0 && j === align.length - 1) ||
                       (i === align.length - 1 && j === 0);
            if (skip) continue;
            for (var dr = -2; dr <= 2; dr++) {
              for (var dc = -2; dc <= 2; dc++) {
                var dist = Math.max(Math.abs(dr), Math.abs(dc));
                setFunction(align[i] + dr, align[j] + dc, dist !== 1);
              }
            }
          }
        }

        // Áreas de formato (reservadas) e módulo escuro
        for (i = 0; i < 9; i++) {
          if (i === 6) continue; // preserva o padrão de temporização
          setFunction(8, i, false);
          setFunction(i, 8, false);
        }
        for (i = 0; i < 8; i++) {
          setFunction(8, size - 1 - i, false);
          setFunction(size - 1 - i, 8, false);
        }
        setFunction(size - 8, 8, true);

        // Informação de versão (versão 7 ou maior)
        if (version >= 7) {
          var vbits = bchVersion(version);
          for (i = 0; i < 18; i++) {
            var bit = ((vbits >>> i) & 1) === 1;
            var a = size - 11 + (i % 3);
            var b2 = Math.floor(i / 3);
            setFunction(a, b2, bit);
            setFunction(b2, a, bit);
          }
        }

        // Posiciona os dados em zigue-zague
        var bitIndex = 0, totalBits = codewords.length * 8;
        var upward = true;
        for (var col = size - 1; col > 0; col -= 2) {
          if (col === 6) col--;
          for (var step = 0; step < size; step++) {
            var row = upward ? size - 1 - step : step;
            for (var x = 0; x < 2; x++) {
              var cc = col - x;
              if (reserved[row][cc]) continue;
              var dark2 = false;
              if (bitIndex < totalBits) {
                dark2 = ((codewords[bitIndex >>> 3] >>> (7 - (bitIndex & 7))) & 1) === 1;
                bitIndex++;
              }
              if (maskFunction(mask, row, cc)) dark2 = !dark2;
              modules[row][cc] = dark2;
            }
          }
          upward = !upward;
        }

        // Informação de formato (correção M = 00)
        var fbits = bchFormat((0 << 3) | mask);
        function fbit(n) { return ((fbits >>> n) & 1) === 1; }
        for (i = 0; i <= 5; i++) modules[i][8] = fbit(i);
        modules[7][8] = fbit(6);
        modules[8][8] = fbit(7);
        modules[8][7] = fbit(8);
        for (i = 9; i < 15; i++) modules[8][14 - i] = fbit(i);
        for (i = 0; i < 8; i++) modules[8][size - 1 - i] = fbit(i);
        for (i = 8; i < 15; i++) modules[size - 15 + i][8] = fbit(i);
        modules[size - 8][8] = true;

        return modules;
      }

      function penalty(m) {
        var size = m.length, score = 0, r, c, k;

        for (r = 0; r < size; r++) {
          var runR = 1, runC = 1;
          for (c = 1; c < size; c++) {
            if (m[r][c] === m[r][c - 1]) { runR++; } else { if (runR >= 5) score += runR - 2; runR = 1; }
            if (m[c][r] === m[c - 1][r]) { runC++; } else { if (runC >= 5) score += runC - 2; runC = 1; }
          }
          if (runR >= 5) score += runR - 2;
          if (runC >= 5) score += runC - 2;
        }

        for (r = 0; r < size - 1; r++) {
          for (c = 0; c < size - 1; c++) {
            var v = m[r][c];
            if (v === m[r][c + 1] && v === m[r + 1][c] && v === m[r + 1][c + 1]) score += 3;
          }
        }

        var pat1 = [true, false, true, true, true, false, true, false, false, false, false];
        var pat2 = pat1.slice().reverse();
        function matches(get, pat) {
          for (var q = 0; q < 11; q++) if (get(q) !== pat[q]) return false;
          return true;
        }
        for (r = 0; r < size; r++) {
          for (c = 0; c <= size - 11; c++) {
            (function (rr, cc) {
              if (matches(function (q) { return m[rr][cc + q]; }, pat1) ||
                  matches(function (q) { return m[rr][cc + q]; }, pat2)) score += 40;
              if (matches(function (q) { return m[cc + q][rr]; }, pat1) ||
                  matches(function (q) { return m[cc + q][rr]; }, pat2)) score += 40;
            })(r, c);
          }
        }

        var dark = 0;
        for (r = 0; r < size; r++) for (c = 0; c < size; c++) if (m[r][c]) dark++;
        k = Math.floor(Math.abs(dark * 20 - size * size * 10) / (size * size));
        score += k * 10;
        return score;
      }

      function create(text) {
        var bytes = utf8Bytes(text);
        var version = 0, v;
        for (v = 1; v <= 10; v++) {
          var overhead = v >= 10 ? 3 : 2; // modo + tamanho (em bytes, arredondado)
          var capacity = Math.floor((TABLE[v][0] * 8 - (v >= 10 ? 20 : 12)) / 8);
          if (bytes.length <= capacity) { version = v; break; }
        }
        if (!version) throw new Error("Texto grande demais para o QR Code.");

        var codewords = buildCodewords(bytes, version);
        var best = null, bestScore = Infinity;
        for (var mask = 0; mask < 8; mask++) {
          var matrix = makeMatrix(codewords, version, mask);
          var score = penalty(matrix);
          if (score < bestScore) { bestScore = score; best = matrix; }
        }
        return best;
      }

      function QR(element, options) {
        var matrix = create(String(options.text));
        var size = matrix.length, quiet = 4, total = size + quiet * 2;
        var path = "";
        for (var r = 0; r < size; r++) {
          for (var c = 0; c < size; c++) {
            if (matrix[r][c]) path += "M" + (c + quiet) + " " + (r + quiet) + "h1v1h-1z";
          }
        }
        var px = options.width || 220;
        element.innerHTML =
          '<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 ' + total + " " + total +
          '" width="' + px + '" height="' + px + '" role="img" aria-label="QR Code do Pix" ' +
          'shape-rendering="crispEdges" style="max-width:100%;height:auto;background:#fff">' +
          '<rect width="100%" height="100%" fill="#fff"/>' +
          '<path d="' + path + '" fill="#000"/></svg>';
      }

      QR.CorrectLevel = { L: 1, M: 0, Q: 3, H: 2 };
      QR._create = create; // usado apenas para testes
      return QR;
    })();

  </script>

  <script>
    // =====================================================================
    // COMO EDITAR O CATÁLOGO
    // Cada produto é um bloco { ... } da lista abaixo.
    //   id          número único (não repita; não reutilize o de um produto removido)
    //   name        nome que aparece no cartão
    //   description texto curto (pode deixar "" para não mostrar descrição)
    //   price       preço em reais, com ponto: 12.50 aparece como R$ 12,50
    //   image       caminho da foto dentro do repositório (pasta images/)
    //               Se a foto não existir, o cartão mostra "Foto em breve".
    //
    // Para ADICIONAR um produto: copie um bloco, cole depois dele (com vírgula)
    // e troque os dados. Para REMOVER: apague o bloco inteiro.
    //
    // ATENÇÃO: nomes, preços e descrições abaixo são provisórios.
    // =====================================================================
    const products = [
      {
        id: 1,
        name: "Pão artesanal",
        description: "Uma delícia feita com cuidado.",
        price: 12.00,
        image: "images/pao-artesanal.jpg"
      },
      {
        id: 2,
        name: "Biscoitinho amanteigado",
        description: "Perfeito para acompanhar um café.",
        price: 7.99,
        image: "images/biscoitinho-amanteigado.jpg"
      },
      {
        id: 3,
        name: "Casadinho de goiabada",
        description: "Uma combinação clássica e saborosa.",
        price: 9.99,
        image: "images/casadinho-de-goiabada.jpg"
      },
      {
        id: 4,
        name: "Cinnamon roll",
        description: "Massa macia com aroma de canela.",
        price: 2.00,
        image: "images/cinnamon-roll.jpg"
      },
      {
        id: 5,
        name: "Amanteigado de maizena",
        description: "Leve, delicado e saboroso.",
        price: 7.99,
        image: "images/amanteigado-de-maizena.jpg"
      },
      {
        id: 6,
        name: "Biscoitos da casa",
        description: "Uma opção artesanal para compartilhar.",
        price: 10.00,
        image: "images/biscoitos-da-casa.jpg"
      }
    ];

    // CONFIGURAÇÃO PIX:
    // Para chave de telefone, use o formato internacional: +55 + DDD + número.
    // Não publique o site para receber pagamentos sem testar com o app do banco.
    const PIX_KEY = "+5522981114534";
    const PIX_RECEIVER = "PANIS ARTIS";
    const PIX_CITY = "CASIMIRO DE ABREU";

    const cart = {};

    // ---------- Dinheiro (cálculos em centavos, para evitar erros de arredondamento) ----------

    function toCents(value) {
      return Math.round(Number(value) * 100);
    }

    function money(cents) {
      return (cents / 100).toLocaleString("pt-BR", {
        style: "currency",
        currency: "BRL"
      });
    }

    // Confere a lista de produtos e calcula o preço em centavos de cada um.
    const catalogProducts = (function () {
      const seen = {};
      return products.filter(function (product) {
        const valid =
          product &&
          Number.isFinite(Number(product.id)) &&
          !seen[product.id] &&
          Number.isFinite(Number(product.price)) &&
          Number(product.price) >= 0;

        if (!valid) {
          console.error("Produto ignorado (confira id repetido ou preço inválido):", product);
          return false;
        }

        seen[product.id] = true;
        product.priceCents = toCents(product.price);
        return true;
      });
    })();

    function escapeHTML(value) {
      return String(value).replace(/[&<>"']/g, function (char) {
        const replacements = {
          "&": "&amp;",
          "<": "&lt;",
          ">": "&gt;",
          '"': "&quot;",
          "'": "&#039;"
        };
        return replacements[char];
      });
    }

    // ---------- Catálogo ----------

    function placeholderHTML() {
      return `
        <div class="photo-placeholder">
          <span aria-hidden="true">PA</span>
          <span>Foto em breve</span>
        </div>
      `;
    }

    function photoHTML(product) {
      if (!product.image) {
        return placeholderHTML();
      }

      return `<img src="${escapeHTML(product.image)}" alt="Foto de ${escapeHTML(product.name)}" decoding="async">`;
    }

    function renderProducts() {
      const catalog = document.getElementById("catalog");

      catalog.innerHTML = catalogProducts.map(function (product) {
        const description = product.description
          ? `<p>${escapeHTML(product.description)}</p>`
          : `<p></p>`;

        return `
          <article class="product">
            <div class="product-photo">${photoHTML(product)}</div>
            <div class="product-body">
              <h3>${escapeHTML(product.name)}</h3>
              ${description}
              <div class="price">${money(product.priceCents)}</div>
              <button onclick="addToCart(${product.id}, this)">
                Adicionar ao pedido
              </button>
            </div>
          </article>
        `;
      }).join("");

      // Se uma foto não carregar (arquivo ausente ou nome errado), mostra o espaço reservado.
      catalog.querySelectorAll(".product-photo img").forEach(function (img) {
        function showPlaceholder() {
          img.parentElement.innerHTML = placeholderHTML();
        }

        img.addEventListener("error", showPlaceholder, { once: true });

        if (img.complete && img.naturalWidth === 0) {
          showPlaceholder();
        }
      });
    }

    // ---------- Carrinho ----------

    function flashButton(button) {
      if (!button) return;

      clearTimeout(button._timer);
      button.textContent = "Adicionado ✓";
      button._timer = setTimeout(function () {
        button.textContent = "Adicionar ao pedido";
      }, 1200);
    }

    function addToCart(id, button) {
      cart[id] = (cart[id] || 0) + 1;
      hidePayment();
      renderCart();
      flashButton(button);
    }

    function changeQuantity(id, amount) {
      cart[id] = (cart[id] || 0) + amount;

      if (cart[id] <= 0) {
        delete cart[id];
      }

      hidePayment();
      renderCart();
    }

    function removeItem(id) {
      delete cart[id];
      hidePayment();
      renderCart();
    }

    // Total em centavos
    function getTotal() {
      return catalogProducts.reduce(function (sum, product) {
        return sum + product.priceCents * (cart[product.id] || 0);
      }, 0);
    }

    function getItemCount() {
      return Object.keys(cart).reduce(function (sum, id) {
        return sum + cart[id];
      }, 0);
    }

    function renderCart() {
      const container = document.getElementById("cartItems");
      const selected = catalogProducts.filter(function (product) {
        return cart[product.id] > 0;
      });

      if (selected.length === 0) {
        container.innerHTML = `
          <p class="empty">
            Seu cesto está vazio. Escolha uma delícia do nosso catálogo!
          </p>
        `;
      } else {
        container.innerHTML = selected.map(function (product) {
          return `
            <div class="cartrow">
              <div>
                <strong>${escapeHTML(product.name)}</strong>
                <div class="notice">${money(product.priceCents)} cada</div>
              </div>

              <div class="qty">
                <button
                  aria-label="Diminuir quantidade"
                  onclick="changeQuantity(${product.id}, -1)"
                >−</button>

                <span>${cart[product.id]}</span>

                <button
                  aria-label="Aumentar quantidade"
                  onclick="changeQuantity(${product.id}, 1)"
                >+</button>
              </div>

              <button
                class="remove"
                onclick="removeItem(${product.id})"
              >Remover</button>
            </div>
          `;
        }).join("");
      }

      document.getElementById("total").textContent = money(getTotal());

      const count = getItemCount();
      document.getElementById("navPedido").textContent =
        count > 0 ? "Meu pedido (" + count + ")" : "Meu pedido";
    }

    function hidePayment() {
      document.getElementById("payment").classList.remove("visible");
      document.getElementById("qrcode").innerHTML = "";
      document.getElementById("pixCode").value = "";
    }

    function getOrderText() {
      const selected = catalogProducts.filter(function (product) {
        return cart[product.id] > 0;
      });

      if (selected.length === 0) {
        return "";
      }

      const lines = selected.map(function (product) {
        return cart[product.id] + "x " + product.name +
          " — " + money(product.priceCents * cart[product.id]);
      });

      return [
        "PANIS ARTIS — RESUMO DO PEDIDO",
        "",
        ...lines,
        "",
        "TOTAL: " + money(getTotal()),
        "",
        "Por favor, confirme a disponibilidade e a entrega."
      ].join("\n");
    }

    async function copyText(text, successMessage) {
      try {
        await navigator.clipboard.writeText(text);
        alert(successMessage);
      } catch (error) {
        const field = document.createElement("textarea");
        field.value = text;
        field.style.position = "fixed";
        field.style.left = "-9999px";
        document.body.appendChild(field);
        field.select();

        const copied = document.execCommand("copy");
        field.remove();

        if (copied) {
          alert(successMessage);
        } else {
          prompt("Copie o texto abaixo:", text);
        }
      }
    }

    async function copyOrder() {
      const orderText = getOrderText();

      if (!orderText) {
        alert("Adicione pelo menos um produto ao pedido!");
        return;
      }

      await copyText(orderText, "Resumo do pedido copiado!");
    }

    function clearCart() {
      if (Object.keys(cart).length === 0) {
        alert("O cesto já está vazio.");
        return;
      }

      if (!confirm("Deseja remover todos os produtos do cesto?")) {
        return;
      }

      Object.keys(cart).forEach(function (id) {
        delete cart[id];
      });

      hidePayment();
      renderCart();
    }

    // ---------- Pix ----------

    function tlv(id, value) {
      const text = String(value);
      return id + String(text.length).padStart(2, "0") + text;
    }

    function crc16(payload) {
      let crc = 0xFFFF;

      for (let i = 0; i < payload.length; i++) {
        crc ^= payload.charCodeAt(i) << 8;

        for (let bit = 0; bit < 8; bit++) {
          if (crc & 0x8000) {
            crc = (crc << 1) ^ 0x1021;
          } else {
            crc <<= 1;
          }

          crc &= 0xFFFF;
        }
      }

      return crc.toString(16).toUpperCase().padStart(4, "0");
    }

    function normalizeText(text, maxLength) {
      return text.normalize("NFD")
        .replace(/[\u0300-\u036f]/g, "")
        .replace(/[^A-Za-z0-9 ]/g, "")
        .trim()
        .slice(0, maxLength);
    }

    // amountCents: valor do pedido em centavos
    function buildPixPayload(amountCents) {
      const key = PIX_KEY.trim();

      if (!key || key === "SUA-CHAVE-PIX-AQUI") {
        throw new Error(
          "A chave Pix ainda não foi configurada no código."
        );
      }

      if (!Number.isInteger(amountCents) || amountCents <= 0) {
        throw new Error("O valor do pedido não é válido.");
      }

      const merchantAccount =
        tlv("00", "BR.GOV.BCB.PIX") +
        tlv("01", key);

      const payload =
        tlv("00", "01") +
        tlv("01", "12") +
        tlv("26", merchantAccount) +
        tlv("52", "0000") +
        tlv("53", "986") +
        tlv("54", (amountCents / 100).toFixed(2)) +
        tlv("58", "BR") +
        tlv("59", normalizeText(PIX_RECEIVER, 25)) +
        tlv("60", normalizeText(PIX_CITY, 15)) +
        tlv("62", tlv("05", "***")) +
        "6304";

      return payload + crc16(payload);
    }

    function startPayment() {
      const total = getTotal();

      if (total <= 0) {
        alert("Adicione pelo menos um produto antes de gerar o Pix.");
        return;
      }

      if (typeof QRCode === "undefined") {
        alert(
          "Não foi possível carregar o gerador de QR Code. Recarregue a página e tente novamente."
        );
        return;
      }

      try {
        const payload = buildPixPayload(total);

        document.getElementById("paymentTotal").textContent = money(total);
        document.getElementById("pixCode").value = payload;

        const qr = document.getElementById("qrcode");
        qr.innerHTML = "";

        new QRCode(qr, {
          text: payload,
          width: 220,
          height: 220,
          correctLevel: QRCode.CorrectLevel.M
        });

        document.getElementById("payment").classList.add("visible");
        document.getElementById("payment").scrollIntoView({
          behavior: "smooth",
          block: "start"
        });
      } catch (error) {
        alert(error.message || "Não foi possível gerar o Pix.");
      }
    }

    async function copyPix() {
      const payload = document.getElementById("pixCode").value;

      if (!payload) {
        alert("Gere o Pix primeiro.");
        return;
      }

      await copyText(
        payload,
        "Código copiado! Confira os dados no aplicativo do seu banco antes de pagar."
      );
    }

    document.getElementById("year").textContent = new Date().getFullYear();

    renderProducts();
    renderCart();
  </script>
</body>
</html>
