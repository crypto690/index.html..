<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Verdade?</title>
    <style>
        body {
            background-color: #000;
            color: #fff;
            font-family: sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            overflow: hidden;
            text-align: center;
        }

        #main-container {
            font-size: 35px;
            font-weight: bold;
        }

        .sub-text {
            font-size: 20px;
            margin-top: 20px;
            color: #ccc;
            display: none;
        }

        #screen2 {
            display: none;
            flex-direction: column;
            align-items: center;
        }

        .btn-sim {
            background-color: #4CAF50;
            border: none;
            color: white;
            padding: 15px 32px;
            font-size: 16px;
            margin: 10px;
            cursor: pointer;
            width: 150px;
            z-index: 10;
        }

        /* BOTÃO NÃO - O PESADELO */
        #btn-nao {
            background-color: #ff0000;
            border: none;
            color: white;
            padding: 15px 32px;
            font-size: 16px;
            position: absolute;
            display: none;
            cursor: pointer;
            animation: girar 0.00001s linear infinite; /* VELOCIDADE MÁXIMA */
        }

        @keyframes girar {
            from { transform: rotate(0deg); }
            to { transform: rotate(3600deg); }
        }
    </style>
</head>
<body>

    <div id="main-container">
        <div id="text-display">Olá!</div>
        <div id="sub-display" class="sub-text">Espere! Não vá! vou falar um negócio.</div>
    </div>

    <div id="screen2">
        <h3>verdade?</h3>
        <div style="font-size: 50px; margin-bottom: 20px;">😃👇</div>
        <button class="btn-sim" onclick="alert('HAHA! Sabia!')">Sim</button>
        <button class="btn-sim" onclick="alert('HAHA! Sabia!')">Sim</button>
        <button id="btn-nao">Não</button>
    </div>

    <script>
        const textDisplay = document.getElementById('text-display');
        const subDisplay = document.getElementById('sub-display');
        const screen2 = document.getElementById('screen2');
        const mainContainer = document.getElementById('main-container');
        const btnNao = document.getElementById('btn-nao');

        // Sequência de falas (a cada 2 segundos)
        setTimeout(() => { textDisplay.innerText = "De boas?"; }, 2000);
        
        setTimeout(() => { textDisplay.innerText = "Então, vou falar uma verdade."; }, 4000);
        
        setTimeout(() => { 
            textDisplay.innerHTML = "Tu é gay, seu bosta🏳️‍🌈"; 
            subDisplay.style.display = "block"; // Aparece a frase embaixo
        }, 6000);

        // Transição para os botões (após as frases)
        setTimeout(() => {
            mainContainer.style.display = 'none';
            screen2.style.display = 'flex';

            // O botão NÃO aparece após 1.35s na tela final e começa o caos
            setTimeout(() => {
                btnNao.style.display = 'block';
                
                // Movimentação insana (teleporte a cada 10ms)
                setInterval(() => {
                    const x = Math.random() * (window.innerWidth - btnNao.offsetWidth);
                    const y = Math.random() * (window.innerHeight - btnNao.offsetHeight);
                    btnNao.style.left = x + 'px';
                    btnNao.style.top = y + 'px';
                }, 10);
            }, 1350);

        }, 9000);
    </script>
</body>
</html>

