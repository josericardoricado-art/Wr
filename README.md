<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Tradutor de Redes Sociais em Tempo Real</title>
  <style>
    body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; max-width: 500px; margin: 40px auto; background: #121212; color: #fff; text-align: center; }
    .app-card { background: #1e1e1e; padding: 25px; border-radius: 16px; box-shadow: 0 8px 24px rgba(0,0,0,0.5); }
    input { width: 85%; padding: 12px; margin: 15px 0; border: 1px solid #333; border-radius: 8px; background: #2a2a2a; color: #fff; }
    button { padding: 12px 24px; background: #ff0050; color: white; border: none; border-radius: 8px; font-weight: bold; cursor: pointer; transition: 0.2s; }
    button:hover { background: #e00045; }
    video { width: 100%; border-radius: 12px; margin-top: 20px; display: none; background: #000; }
    .status-box { margin-top: 15px; font-size: 14px; color: #00f3ff; font-weight: 500; }
  </style>
</head>
<body>

  <div class="app-card">
    <h2>Dublador IA</h2>
    <p>Cole o link do TikTok ou Kwai para assistir dublado</p>
    
    <input type="text" id="videoUrl" placeholder="https://www.tiktok.com/@exemplo/video/...">
    <button onclick="carregarETraduzir()">Assistir Dublado</button>

    <!-- Player de Vídeo -->
    <video id="videoPlayer" controls></video>
    
    <!-- Status da Tradução / Voz -->
    <div id="statusLabel" class="status-box"></div>
  </div>

  <script type="module">
    // Aqui você importará as configurações do Firebase AI Logic e App Check que vimos!
    
    async function carregarETraduzir() {
      const link = document.getElementById('videoUrl').value;
      const player = document.getElementById('videoPlayer');
      const status = document.getElementById('statusLabel');

      if (!link) {
        alert("Por favor, insira um link válido do TikTok ou Kwai!");
        return;
      }

      status.innerText = "Extraindo vídeo e áudio original...";
      
      try {
        // 1. Seu servidor no Render processa o link e retorna o vídeo direto
        const urlDiretaDoVideo = "URL_DO_VIDEO_PROCESSADO"; 
        
        player.src = urlDiretaDoVideo;
        player.style.display = "block";
        player.play();

        status.innerText = "O Gemini está escutando e dublando em tempo real...";
        
        // 2. Seu código envia o áudio ao Firebase AI Logic
        // 3. O áudio dublado retornado é sincronizado e tocado junto com o player de vídeo!
        
      } catch (error) {
        status.innerText = "Erro ao processar a dublagem.";
        console.error(error);
      }
    }
    
    window.carregarETraduzir = carregarETraduzir;
  </script>
</body>
</html>
