<!DOCTYPE html>
<html lang="es">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Agregar Imágenes y Links</title>
  <style>
    #contenedor {
      text-align: center;
      position: relative;
    }

    .imagen {
      width: 80px;
      height: 80px;
      margin: 10px;
      position: absolute;
    }

    #miBoton {
      position: absolute;
      top: 50px;
      left: 50px;
      width: 50px;
      height: 50px;
    }
  
  </style>
</head>

<body>

  <button onclick="agregarContenido()">TE AMO <3</button>
  <button id="miBoton" onclick="moverBoton()">OK</button>

  <div id="contenedor"></div>

  <script>
    var cambioAutomatico;

    function agregarContenido() {
      var contenedor = document.getElementById('contenedor');
      contenedor.innerHTML = '';

      var imagenes = [
        'WhatsApp Image 2024-02-14 at 1.17.09 PM (1).jpeg',
        'WhatsApp Image 2024-02-14 at 1.17.09 PM (2).jpeg',
        'WhatsApp Image 2024-02-14 at 1.17.09 PM.jpeg',
        'WhatsApp Image 2024-02-14 at 1.17.47 PM.jpeg',
        '1284627_46d12.gif',
        '1284627_46d12.gif',
        '1284627_46d12.gif',
        '1284627_46d12.gif',
        '1284627_46d12.gif',
        '1284627_46d12.gif',
        '1284627_46d12.gif'
      ];

      for (var i = 0; i < imagenes.length; i++) {
        var imagen = document.createElement('img');
        imagen.src = imagenes[i];
        imagen.alt = 'Imagen ' + (i + 1);
        imagen.className = 'imagen';

        var posicionTop, posicionLeft;
        do {
          posicionTop = Math.random() * (window.innerHeight - 150);
          posicionLeft = Math.random() * (window.innerWidth - 150);
        } while (verificarPosicion(imagen, posicionTop, posicionLeft));

        imagen.style.top = posicionTop + 'px';
        imagen.style.left = posicionLeft + 'px';
        contenedor.appendChild(imagen);
      }

      var enlaceVideo = document.createElement('a');
      enlaceVideo.href = 'https://youtu.be/rrl4u6xIJUs'; 
      enlaceVideo.textContent = 'DALE CLIIIIIIIIC';
      enlaceVideo.target = '_blank'; 
      contenedor.appendChild(enlaceVideo);

      cambiarColoresAutomatico();
    }

    function verificarPosicion(imagen, top, left) {
      var imagenes = document.getElementsByClassName('imagen');
      for (var i = 0; i < imagenes.length; i++) {
        var otraImagen = imagenes[i];
        var distancia = Math.sqrt(Math.pow(top - otraImagen.offsetTop, 2) + Math.pow(left - otraImagen.offsetLeft, 2));
        if (distancia < 100) {
          return true;
        }
      }
      return false;
    }

    function cambiarColores() {
      var coloresFondo = ['#FF0000', '#00FF00', '#0000FF', '#FFFF00', '#FF00FF', '#00FFFF'];
      var coloresTexto = ['#FFFFFF', '#000000', '#CCCCCC', '#990000', '#006600', '#000099'];

      document.body.style.backgroundColor = coloresFondo[Math.floor(Math.random() * coloresFondo.length)];
      document.body.style.color = coloresTexto[Math.floor(Math.random() * coloresTexto.length)];
    }

    function cambiarColoresAutomatico() {
      cambioAutomatico = setInterval(cambiarColores, 20);
    }

    function moverBoton() {
      var boton = document.getElementById('miBoton');

      boton.style.top = (Math.random() * window.innerHeight) + 'px';
      boton.style.left = (Math.random() * window.innerWidth) + 'px';
    }
  </script>
  <p> <center>TE AMO MUCHISIMO A PASITOS DE TORTUGAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA</center></p>
  <p style="color: dimgray;"><center>FELIZ SAN VALENTIN</center></p>
</body>

</html>
