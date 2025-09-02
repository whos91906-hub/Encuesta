<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Encuesta de Estilos de Aprendizaje - VAK</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f9;
      margin: 0;
      padding: 20px;
    }
    .container {
      max-width: 800px;
      margin: auto;
      background: white;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.1);
    }
    h2, h3 { text-align: center; }
    .question { margin: 20px 0; }
    button {
      display: block;
      width: 100%;
      padding: 12px;
      margin-top: 20px;
      background: #4CAF50;
      color: white;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      font-size: 16px;
    }
    button:hover { background: #45a049; }
    #resultado {
      margin-top: 20px;
      padding: 15px;
      border-radius: 8px;
      background: #eafaf1;
      font-weight: bold;
      text-align: center;
      display: none;
    }
    label { display: block; margin: 5px 0; }
  </style>
</head>
<body>
  <div class="container">
    <h2>Encuesta de Estilos de Aprendizaje - VAK</h2>
    <form id="encuestaForm">

      <!-- Datos Generales -->
      <div class="question">
        <p><b>1. Edad:</b></p>
        <input type="number" name="edad" min="5" max="100" required>
      </div>

      <div class="question">
        <p><b>2. Género:</b></p>
        <label><input type="radio" name="genero" value="Femenino" required> Femenino</label>
        <label><input type="radio" name="genero" value="Masculino"> Masculino</label>
      </div>

      <div class="question">
        <p><b>3. Tiempo aproximado de estudio diario:</b></p>
        <label><input type="radio" name="tiempo" value="15-30min" required> 15 a 30 minutos</label>
        <label><input type="radio" name="tiempo" value="45min-1h"> 45 minutos a 1 hora</label>
        <label><input type="radio" name="tiempo" value="1h-1.5h"> 1 hora a 1 hora y media</label>
        <label><input type="radio" name="tiempo" value="2h+"> 2 horas en adelante</label>
      </div>

      <div class="question">
        <p><b>4. Ciclo que cursa actualmente:</b></p>
        <input type="text" name="ciclo" required>
      </div>

      <h3>Preguntas - Modelo VAK</h3>

      <!-- Preguntas VAK -->
      <div id="preguntas"></div>

      <button type="submit">Ver Resultado</button>
    </form>

    <div id="resultado"></div>
  </div>

  <script>
    // Lista de preguntas
    const preguntas = [
      "Cuando quiero recordar algo...",
      "Prefiero que un maestro...",
      "Cuando leo un texto, recuerdo mejor...",
      "En una clase, me resulta más fácil concentrarme si...",
      "Para estudiar, normalmente...",
      "Me cuesta entender una explicación si...",
      "Si tengo que dar direcciones a alguien...",
      "En mi tiempo libre prefiero...",
      "Cuando conozco a alguien...",
      "Si aprendo una nueva habilidad...",
      "En una exposición me siento más cómodo...",
      "Si algo me llama la atención, suele ser...",
      "Me resulta más fácil recordar...",
      "Prefiero profesores que...",
      "Cuando estudio, me ayuda más…",
      "Cuando pienso en una palabra nueva...",
      "Si tengo que elegir un curso en línea prefiero...",
      "Cuando estoy en clase, suelo...",
      "Al aprender mejoro si...",
      "Prefiero libros que..."
    ];

    const opciones = [
      ["a) Veo una imagen mental.", "b) Lo repito en voz alta o en mi mente.", "c) Lo escribo o hago un esquema con mis manos."],
      ["a) Use presentaciones, gráficos o videos.", "b) Explique en detalle con ejemplos verbales.", "c) Realice dinámicas o prácticas."],
      ["a) Lo que veo en gráficos o subrayado.", "b) Lo que escucho en mi mente mientras leo.", "c) Lo que hago con el texto (subrayar, resumir, etc.)"],
      ["a) Hay presentaciones visuales.", "b) El docente tiene buena entonación.", "c) Puedo participar activamente."],
      ["a) Hago mapas mentales o uso colores.", "b) Grabo la clase o leo en voz alta.", "c) Hago resúmenes o repaso haciendo ejercicios."],
      ["a) No tiene apoyo visual.", "b) No se escucha claramente.", "c) No puedo practicarla."],
      ["a) Le dibujo un mapa.", "b) Le explico paso a paso.", "c) Lo acompaño o señalo físicamente."],
      ["a) Ver películas o leer.", "b) Escuchar música o podcasts.", "c) Hacer deporte o actividades manuales."],
      ["a) Recuerdo su rostro.", "b) Recuerdo su voz o nombre.", "c) Recuerdo el contexto o cómo me hizo sentir."],
      ["a) Veo videos o imágenes explicativas.", "b) Escucho instrucciones detalladas.", "c) La practico directamente."],
      ["a) Apoyándome con diapositivas.", "b) Explicando verbalmente lo que sé.", "c) Moviéndome o haciendo demostraciones."],
      ["a) Su apariencia.", "b) Su sonido.", "c) Su textura o funcionamiento."],
      ["a) Imágenes y colores.", "b) Conversaciones o sonidos.", "c) Lo que hice en una actividad."],
      ["a) Usan imágenes, diagramas y pizarras.", "b) Explican con claridad y buen tono.", "c) Hacen talleres y prácticas."],
      ["a) Usar esquemas o resúmenes visuales.", "b) Escuchar explicaciones.", "c) Realizar ejercicios prácticos."],
      ["a) Imagino cómo se escribe.", "b) La pronuncio mentalmente.", "c) Me imagino usándola en un contexto."],
      ["a) Que tenga muchos recursos visuales.", "b) Que incluya audios o podcasts.", "c) Que tenga actividades interactivas."],
      ["a) Tomar apuntes con dibujos o colores.", "b) Escuchar con atención sin escribir mucho.", "c) Participar activamente con preguntas o ejercicios."],
      ["a) Puedo ver lo que estudio.", "b) Escucho explicaciones claras.", "c) Lo practico o lo aplico."],
      ["a) Tengan ilustraciones o gráficos.", "b) Sean narrativos o con diálogos.", "c) Tengan actividades al final de cada capítulo."]
    ];

    // Generar preguntas dinámicamente
    const preguntasDiv = document.getElementById("preguntas");
    preguntas.forEach((pregunta, i) => {
      let html = `<div class="question"><p><b>${i+5}. ${pregunta}</b></p>`;
      html += `<label><input type="radio" name="q${i+1}" value="A" required> ${opciones[i][0]}</label>`;
      html += `<label><input type="radio" name="q${i+1}" value="B"> ${opciones[i][1]}</label>`;
      html += `<label><input type="radio" name="q${i+1}" value="C"> ${opciones[i][2]}</label>`;
      html += `</div>`;
      preguntasDiv.innerHTML += html;
    });

    // Procesar resultados
    document.getElementById("encuestaForm").addEventListener("submit", function(e) {
      e.preventDefault();

      let respuestas = { A: 0, B: 0, C: 0 };
      let datos = new FormData(e.target);

      for (let [key, value] of datos.entries()) {
        if (value === "A" || value === "B" || value === "C") {
          respuestas[value]++;
        }
      }

      let total = respuestas.A + respuestas.B + respuestas.C;
      let porcentajeA = ((respuestas.A / total) * 100).toFixed(1);
      let porcentajeB = ((respuestas.B / total) * 100).toFixed(1);
      let porcentajeC = ((respuestas.C / total) * 100).toFixed(1);

      let resultadoTexto = `📊 Resultados:<br>
        Visual (A): ${respuestas.A} respuestas (${porcentajeA}%)<br>
        Auditivo (B): ${respuestas.B} respuestas (${porcentajeB}%)<br>
        Kinestésico (C): ${respuestas.C} respuestas (${porcentajeC}%)<br><br>`;

      if (respuestas.A > respuestas.B && respuestas.A > respuestas.C) {
        resultadoTexto += "✅ Tu estilo de aprendizaje predominante es <b>VISUAL</b> 📖";
      } else if (respuestas.B > respuestas.A && respuestas.B > respuestas.C) {
        resultadoTexto += "✅ Tu estilo de aprendizaje predominante es <b>AUDITIVO</b> 🎧";
      } else if (respuestas.C > respuestas.A && respuestas.C > respuestas.B) {
        resultadoTexto += "✅ Tu estilo de aprendizaje predominante es <b>KINESTÉSICO</b> 🤸";
      } else {
        resultadoTexto += "⚖️ Tienes un estilo de aprendizaje <b>mixto</b>.";
      }

      let resultadoDiv = document.getElementById("resultado");
      resultadoDiv.innerHTML = resultadoTexto;
      resultadoDiv.style.display = "block";
      resultadoDiv.scrollIntoView({ behavior: "smooth" });
    });
  </script>
</body>
</html>
