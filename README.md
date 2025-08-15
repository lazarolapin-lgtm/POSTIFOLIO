https://github.com/lazarolapin2-design
# POSTIFOLIO
Logotipo
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Galeria de Imagens</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"> 

  <!-- LightGallery CSS -->
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/lightgallery@2.7.1/css/lightgallery-bundle.min.css"> 

  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f5f5f5;
      margin: 0;
      padding: 20px;
    } 

    h1 {
      text-align: center;
      margin-bottom: 20px;
      color: #333;
    } 

    .gallery {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 15px;
    } 

    .gallery a {
      display: block;
      overflow: hidden;
      border-radius: 10px;
      background: white;
      box-shadow: 0 2px 6px rgba(0,0,0,0.1);
      transition: transform 0.2s ease;
    } 

    .gallery a:hover {
      transform: scale(1.02);
    } 

    .gallery img {
      width: 100%;
      height: auto;
      display: block;
    }
  </style>
</head>
<body> 

<h1>Minha Galeria Online</h1> 

<div class="gallery" id="lightgallery"></div> 

<!-- LightGallery JS -->
<script src="https://cdn.jsdelivr.net/npm/lightgallery@2.7.1/lightgallery.umd.js"></script>
<script src="https://cdn.jsdelivr.net/npm/lightgallery@2.7.1/plugins/zoom/lg-zoom.umd.js"></script>
<script src="https://cdn.jsdelivr.net/npm/lightgallery@2.7.1/plugins/fullscreen/lg-fullscreen.umd.js"></script>
<script src="https://cdn.jsdelivr.net/npm/lightgallery@2.7.1/plugins/thumbnail/lg-thumbnail.umd.js"></script> 

<script>
  // Lista de imagens (pode usar URLs diretas)
  const imagens = [
    {
      src: "imagem1.jpg",
      thumb: "imagem1_thumbnail.jpg",
      titulo: "Imagem 1",
      descricao: "Descrição da imagem 1"
    },
    {
      src: "imagem2.jpg",
      thumb: "imagem2_thumbnail.jpg",
      titulo: "Imagem 2",
      descricao: "Descrição da imagem 2"
    },
    {
      src: "https://picsum.photos/id/1015/1200/800",
      thumb: "https://picsum.photos/id/1015/300/200",
      titulo: "Paisagem",
      descricao: "Uma linda paisagem"
    }
  ]; 

  // Inserir imagens dinamicamente no HTML
  const galeria = document.getElementById('lightgallery');
  imagens.forEach(img => {
    const link = document.createElement('a');
    link.href = img.src;
    link.dataset.subHtml = <h4>${img.titulo}</h4><p>${img.descricao}</p>; 

    const imagem = document.createElement('img');
    imagem.src = img.thumb;
    imagem.alt = img.titulo; 

    link.appendChild(imagem);
    galeria.appendChild(link);
  }); 

  // Iniciar LightGallery com plugins
  lightGallery(galeria, {
    plugins: [lgZoom, lgFullscreen, lgThumbnail],
    speed: 500
  });
</script> 

</body>
</html>
