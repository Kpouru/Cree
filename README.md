<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Revista Cristiana</title>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/turn.js/4.1.0/turn.min.js"></script>
  <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
  <style>
    body {
      background: #f0f0f0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }
    #flipbook {
      width: 700px;
      height: 500px;
    }
    .page {
      background: white;
      border: 1px solid #ccc;
      padding: 20px;
      font-family: 'Georgia', serif;
      font-size: 20px;
      text-align: center;
      opacity: 0;
      transition: opacity 1s;
      background-size: cover;
      background-position: center;
      color: #333;
    }
    .page.visible {
      opacity: 1;
    }
    h1, h2 {
      background-color: rgba(255, 255, 255, 0.7);
      display: inline-block;
      padding: 10px;
      border-radius: 10px;
    }
    p {
      background-color: rgba(255, 255, 255, 0.6);
      padding: 10px;
      border-radius: 8px;
      font-size: 18px;
    }
  </style>
</head>
<body>

<div id="flipbook">
  <!-- Portada -->
  <div class="page" style="background-image: url('https://images.unsplash.com/photo-1501179693245-1c91d9f0b7c7?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80'); color: white;">
    <h1>Revista Cristiana Semanal</h1>
    <p>Inspiración y Fe para tu Vida</p>
  </div>

  <!-- Artículo 1 -->
  <div class="page" style="background-image: url('https://images.unsplash.com/photo-1528715471579-d1dbb5d70d62?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80');">
    <h2>La Fuerza de la Oración</h2>
    <p>"La oración es el puente entre el hombre y Dios. En cada palabra, en cada silencio, Dios escucha."</p>
  </div>

  <!-- Artículo 2 -->
  <div class="page" style="background-image: url('https://images.unsplash.com/photo-1588689943653-cbf1e3ba4e07?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80');">
    <h2>Amar al Prójimo</h2>
    <p>"Amar al otro como a ti mismo es vivir el Evangelio en cada acción diaria."</p>
  </div>

  <!-- Reflexión final -->
  <div class="page" style="background-image: url('https://images.unsplash.com/photo-1588679182340-79ea7c2ee3e1?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80');">
    <h2>Reflexión de la Semana</h2>
    <p>"La fe mueve montañas. Confía en el plan divino y avanza con esperanza."</p>
  </div>

  <!-- Contraportada -->
  <div class="page" style="background-image: url('https://images.unsplash.com/photo-1521208912874-cb0400c6272d?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80'); color: white;">
    <h2>¡Nos vemos la próxima semana!</h2>
    <p>Que Dios te bendiga abundantemente.</p>
  </div>
</div>

<script>
  $("#flipbook").turn({
    width: 700,
    height: 500,
    autoCenter: true,
    when: {
      turned: function(event, page, view) {
        $('.page').removeClass('visible');
        $(this).find('.page').eq(view[0]-1).addClass('visible');
        $(this).find('.page').eq(view[1]-1).addClass('visible');
      }
    }
  });
</script>

</body>
</html>
