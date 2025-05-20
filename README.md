<!DOCTYPE html>
<html lang="pt-BR">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Produtos do Sérgio</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Roboto', Arial, sans-serif;
            margin: 0;
            padding: 0;
            background: linear-gradient(135deg, #001f3f 0%, #007BFF 100%);
            color: #ffffff;
            min-height: 100vh;
        }

        header {
            background: rgba(44, 62, 80, 0.95);
            color: #fff;
            padding: 40px 0 30px 0;
            text-align: center;
            font-family: 'Roboto', sans-serif;
            position: relative;
            box-shadow: 0 0 30px 10px #007BFF99, 0 0 80px 10px #001f3f55 inset;
        }

        .decorative-image {
            position: absolute;
            top: 20px;
            right: 40px;
            width: 120px;
            height: auto;
            opacity: 0.95;
            filter: drop-shadow(0 0 20px #007BFF) brightness(1.2);
        }

        .container {
            width: 95%;
            max-width: 1100px;
            margin: 40px auto 30px auto;
            display: flex;
            flex-wrap: wrap;
            gap: 32px;
            justify-content: center;
        }

        .product {
            background: linear-gradient(135deg, #001f3f 60%, #007BFF 100%);
            margin: 0;
            padding: 28px 18px 18px 18px;
            text-align: center;
            border-radius: 18px;
            box-shadow: 0 0 24px 6px #007BFF99, 0 0 40px 10px #001f3f55 inset;
            min-width: 260px;
            max-width: 320px;
            flex: 1 1 260px;
            border: 2px solid #fff2;
            transition: transform 0.2s, box-shadow 0.2s;
            position: relative;
        }

        .product:hover {
            transform: scale(1.04) translateY(-8px);
            box-shadow: 0 0 40px 12px #fff, 0 0 80px 20px #007BFF99 inset;
            border-color: #ffd700;
        }

        .product img {
            max-width: 100%;
            height: 180px;
            object-fit: cover;
            border-radius: 12px;
            box-shadow: 0 0 18px 4px #007BFF99, 0 0 30px 6px #fff3 inset;
            margin-bottom: 12px;
        }

        .product h2 {
            font-size: 1.3em;
            margin: 10px 0 6px 0;
            color: #ffd700;
            text-shadow: 0 0 8px #fff, 0 0 16px #007BFF;
        }

        .product p {
            margin: 6px 0;
            color: #fff;
            text-shadow: 0 0 6px #007BFF99;
        }

        .button {
            background: linear-gradient(90deg, #ffd700 60%, #007BFF 100%);
            color: #001f3f;
            border: none;
            padding: 12px 28px;
            cursor: pointer;
            border-radius: 8px;
            font-weight: bold;
            font-size: 1em;
            margin-top: 10px;
            box-shadow: 0 0 16px 2px #ffd70099, 0 0 10px 2px #007BFF55 inset;
            transition: background 0.2s, color 0.2s, box-shadow 0.2s;
        }

        .button:hover {
            background: linear-gradient(90deg, #fff 60%, #ffd700 100%);
            color: #007BFF;
            box-shadow: 0 0 32px 8px #ffd700, 0 0 20px 4px #007BFF99 inset;
        }

        /* Modal */
        .modal {
            display: none;
            position: fixed;
            z-index: 10;
            left: 0;
            top: 0;
            width: 100vw;
            height: 100vh;
            overflow: auto;
            background: linear-gradient(135deg, #001f3f 60%, #007BFF 100%);
            background-color: rgba(0, 0, 0, 0.85);
            backdrop-filter: blur(2px);
        }

        .modal-content {
            background: linear-gradient(135deg, #001f3f 60%, #007BFF 100%);
            margin: 7% auto;
            padding: 30px 20px 20px 20px;
            border: 2px solid #ffd700;
            width: 95%;
            max-width: 420px;
            text-align: center;
            border-radius: 18px;
            box-shadow: 0 0 40px 10px #ffd70099, 0 0 80px 20px #007BFF99 inset;
            color: #fff;
            position: relative;
        }

        .modal-content img {
            width: 90px;
            margin-bottom: 10px;
            filter: drop-shadow(0 0 16px #ffd700) brightness(1.2);
        }

        .close {
            color: #ffd700;
            float: right;
            font-size: 32px;
            font-weight: bold;
            margin-top: -10px;
            margin-right: -10px;
            text-shadow: 0 0 10px #fff, 0 0 20px #ffd700;
            cursor: pointer;
        }

        .close:hover,
        .close:focus {
            color: #fff;
            text-shadow: 0 0 20px #ffd700, 0 0 40px #fff;
        }

        .contact-button {
            margin: 10px 5px 0 5px;
        }

        input[type="text"],
        input[type="email"] {
            width: 90%;
            padding: 10px;
            margin: 8px 0;
            border-radius: 6px;
            border: 1px solid #ffd700;
            background: #222b;
            color: #fff;
            font-size: 1em;
            box-shadow: 0 0 8px #007BFF55 inset;
        }

        input[type="text"]:focus,
        input[type="email"]:focus {
            outline: none;
            border-color: #fff;
            box-shadow: 0 0 16px #ffd700, 0 0 8px #007BFF99 inset;
        }

        @media (max-width: 700px) {
            .container {
                flex-direction: column;
                gap: 18px;
            }

            .product {
                min-width: 90vw;
                max-width: 98vw;
            }
        }

        footer {
            background: rgba(44, 62, 80, 0.95);
            color: #fff;
            text-align: center;
            padding: 18px 0 10px 0;
            position: relative;
            bottom: 0;
            width: 100%;
            font-size: 1.1em;
            box-shadow: 0 0 30px 10px #007BFF99, 0 0 80px 10px #001f3f55 inset;
        }

        footer a {
            color: #ffd700;
            text-decoration: underline;
            font-weight: bold;
            transition: color 0.2s;
        }

        footer a:hover {
            color: #fff;
            text-shadow: 0 0 10px #ffd700, 0 0 20px #fff;
        }
    </style>
</head>

<body>
    <header>
        <h1>Locomotiva da Alegria</h1>
        <img src="img/Personagen.png" alt="Imagem Decorativa" class="decorative-image">
    </header>
    <div class="container" id="product-container">
        <!-- Os produtos serão carregados aqui dinamicamente -->
    </div>
    <section class="container" id="eventos-fixos">
        <div class="product" style="box-shadow: 0 0 32px 8px #ffd700, 0 0 40px 10px #007BFF99 inset; cursor:pointer;" onclick="abrirModal('Aniversário', 'Valor a Combinar')">
            <h2>Aniversário</h2>
            <img src="img/Aniversario.jpeg" alt="Aniversário" />
            <p><b>Preço:</b> Valor a Combinar</p>
            <p>Leve a Locomotiva da Alegria para animar sua festa de aniversário!</p>
        </div>
        <div class="product" style="box-shadow: 0 0 32px 8px #ffd700, 0 0 40px 10px #007BFF99 inset; cursor:pointer;" onclick="abrirModal('Casamento', 'Valor a Combinar')">
            <h2>Casamento</h2>
            <img src="img/Casamento.JPG" alt="Casamento" />
            <p><b>Preço:</b> Valor a Combinar</p>
            <p>Deixe seu casamento ainda mais inesquecível com a Locomotiva da Alegria!</p>
        </div>
        <div class="product" style="box-shadow: 0 0 32px 8px #ffd700, 0 0 40px 10px #007BFF99 inset; cursor:pointer;" onclick="abrirModal('Formatura', 'Valor a Combinar')">
            <h2>Formatura</h2>
            <img src="img/Formatura.jpg" alt="Formatura" />
            <p><b>Preço:</b> Valor a Combinar</p>
            <p>Comemore sua conquista com muita diversão e brilho!</p>
        </div>
        <div class="product" style="box-shadow: 0 0 32px 8px #ffd700, 0 0 40px 10px #007BFF99 inset; cursor:pointer;" onclick="abrirModal('Porta de Loja', 'Valor a Combinar')">
            <h2>Porta de Loja</h2>
            <img src="img/porta de loja.jpg" alt="Porta de Loja" />
            <p><b>Preço:</b> Valor a Combinar</p>
            <p>Chame atenção para sua loja com a Locomotiva da Alegria!</p>
        </div>
        <div style="width:100%;text-align:center;margin:32px 0 0 0;">
            <a href="https://www.instagram.com/locomotivadaalegriaofc" target="_blank" style="
                display: inline-block;
                background: linear-gradient(90deg, #ffd700 60%, #007BFF 100%);
                color: #001f3f;
                font-weight: bold;
                border-radius: 30px;
                padding: 12px 32px;
                font-size: 1.15em;
                text-decoration: none;
                box-shadow: 0 0 24px 6px #ffd70099, 0 0 40px 10px #007BFF55 inset;
                transition: background 0.2s, color 0.2s, box-shadow 0.2s;
                text-shadow: 0 0 10px #fff, 0 0 20px #007BFF;
                margin-top: 18px;
            ">
                <img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/instagram.svg" alt="Instagram" style="width: 24px; height: 24px; vertical-align: middle; margin-right: 10px; filter: drop-shadow(0 0 8px #ffd700);">
                Siga o organizador no Instagram: <strong>@locomotivadaalegriaofc</strong>
            </a>
        </div>
    </section>

    <!-- Modal para detalhes do produto -->
    <div id="productModal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeModal()">&times;</span>
            <img src="img/Personagen.png" alt="Imagem Decorativa" style="width: 100px; height: auto; margin-bottom: 10px; display: block; margin-left: auto; margin-right: auto;">
            <h2 id="modal-title"></h2>
            <p id="modal-stock"></p>
            <input type="text" id="modal-name" placeholder="Seu Nome" required>
            <input type="email" id="modal-email" placeholder="Seu Email" required>
            <div>
                <button class="button contact-button" onclick="fazerPedido('vinicius')">Enviar para Vinicius</button>
                <button class="button contact-button" onclick="fazerPedido('gustavo')">Enviar para Gustavo</button>
            </div>
        </div>
    </div>

    <footer>
        <p>Desenvolvido por Yuri Silva - Todos os direitos reservados &copy; 2025</p>
    </footer>
  
  

    <script>
        let selectedProduct = null;

        // Carregar produtos dinamicamente do backend
        fetch('http://localhost:3000/dados')
            .then(response => response.json())
            .then(produtos => {
                const container = document.getElementById('product-container');
                container.innerHTML = '';
                produtos.forEach(produto => {
                    const productDiv = document.createElement('div');
                    productDiv.classList.add('product');
                    productDiv.innerHTML = `
                        <img src="${produto.imagem || 'img/Personagen.png'}" alt="${produto.nome}" />
                        <h2>${produto.nome}</h2>
                        <p><b>Preço:</b> ${produto.preco}</p>
                        <button class="button" onclick="abrirModal('${produto.nome}', '${produto.preco}')">Ver Detalhes</button>
                    `;
                    container.appendChild(productDiv);
                });
            });

        function abrirModal(nome, preco) {
            selectedProduct = { nome, preco };
            document.getElementById('modal-title').textContent = nome;
            document.getElementById('modal-stock').textContent = `Preço: ${preco}`;
            document.getElementById('productModal').style.display = 'block';
        }

        function closeModal() {
            document.getElementById('productModal').style.display = 'none';
        }

        function fazerPedido(contato) {
            const nome = document.getElementById('modal-name').value;
            const email = document.getElementById('modal-email').value;

            let numeroWhatsApp;
            if (contato === 'vinicius') {
                numeroWhatsApp = '+5534988870260';
            } else if (contato === 'gustavo') {
                numeroWhatsApp = '+55349988870260';
            }

            const mensagem = `Olá, gostaria de contratar o serviço: ${selectedProduct.nome}.\nNome: ${nome}\nEmail: ${email}`;
            const encodedMessage = encodeURIComponent(mensagem);
            const whatsappUrl = `https://wa.me/${numeroWhatsApp}?text=${encodedMessage}`;

            window.open(whatsappUrl, '_blank');
            closeModal();
        }
    </script>
</body>

</html>
