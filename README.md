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

      <!-- Preguntas fijas -->
      <div class="question">
        <p><b>5. Cuando quiero recordar algo...</b></p>
        <label><input type="radio" name="q1" value="A" required> a) Veo una imagen mental.</label>
        <label><input type="radio" name="q1" value="B"> b) Lo repito en voz alta o en mi mente.</label>
        <label><input type="radio" name="q1" value="C"> c) Lo escribo o hago un esquema con mis manos.</label>
      </div>

      <div class="question">
        <p><b>6. Prefiero que un maestro...</b></p>
        <label><input type="radio" name="q2" value="A" required> a) Use presentaciones, gráficos o videos.</label>
        <label><input type="radio" name="q2" value="B"> b) Explique en detalle con ejemplos verbales.</label>
        <label><input type="radio" name="q2" value="C"> c) Realice dinámicas o prácticas.</label>
      </div>

      <div class="question">
        <p><b>7. Cuando leo un texto, recuerdo mejor...</b></p>
        <label><input type="radio" name="q3" value="A" required> a) Lo que veo en gráficos o subrayado.</label>
        <label><input type="radio" name="q3" value="B"> b) Lo que escucho en mi mente mientras leo.</label>
        <label><input type="radio" name="q3" value="C"> c) Lo que hago con el texto (subrayar, resumir, etc.)</label>
      </div>

      <div class="question">
        <p><b>8. En una clase, me resulta más fácil concentrarme si...</b></p>
        <label><input type="radio" name="q4" value="A" required> a) Hay presentaciones visuales.</label>
        <label><input type="radio" name="q4" value="B"> b) El docente tiene buena entonación.</label>
        <label><input type="radio" name="q4" value="C"> c) Puedo participar activamente.</label>
      </div>

      <div class="question">
        <p><b>9. Para estudiar, normalmente...</b></p>
        <label><input type="radio" name="q5" value="A" required> a) Hago mapas mentales o uso colores.</label>
        <label><input type="radio" name="q5" value="B"> b) Grabo la clase o leo en voz alta.</label>
        <label><input type="radio" name="q5" value="C"> c) Hago resúmenes o repaso haciendo ejercicios.</label>
      </div>

      <div class="question">
        <p><b>10. Me cuesta entender una explicación si...</b></p>
        <label><input type="radio" name="q6" value="A" required> a) No tiene apoyo visual.</label>
        <label><input type="radio" name="q6" value="B"> b) No se escucha claramente.</label>
        <label><input type="radio" name="q6" value="C"> c) No puedo practicarla.</label>
      </div>

      <div class="question">
        <p><b>11. Si tengo que dar direcciones a alguien...</b></p>
        <label><input type="radio" name="q7" value="A" required> a) Le dibujo un mapa.</label>
        <label><input type="radio" name="q7" value="B"> b) Le explico paso a paso.</label>
        <label><input type="radio" name="q7" value="C"> c) Lo acompaño o señalo físicamente.</label>
      </div>

      <div class="question">
        <p><b>12. En mi tiempo libre prefiero...</b></p>
        <label><input type="radio" name="q8" value="A" required> a) Ver películas o leer.</label>
        <label><input type="radio" name="q8" value="B"> b) Escuchar música o podcasts.</label>
        <label><input type="radio" name="q8" value="C"> c) Hacer deporte o actividades manuales.</label>
      </div>

      <div class="question">
        <p><b>13. Cuando conozco a alguien...</b></p>
        <label><input type="radio" name="q9" value="A" required> a) Recuerdo su rostro.</label>
        <label><input type="radio" name="q9" value="B"> b) Recuerdo su voz o nombre.</label>
        <label><input type="radio" name="q9" value="C"> c) Recuerdo el contexto o cómo me hizo sentir.</label>
      </div>

      <div class="question">
        <p><b>14. Si aprendo una nueva habilidad...</b></p>
        <label><input type="radio" name="q10" value="A" required> a) Veo videos o imágenes explicativas.</label>
        <label><input type="radio" name="q10" value="B"> b) Escucho instrucciones detalladas.</label>
        <label><input type="radio" name="q10" value="C"> c) La practico directamente.</label>
      </div>

      <div class="question">
        <p><b>15. En una exposición me siento más cómodo...</b></p>
        <label><input type="radio" name="q11" value="A" required> a) Apoyándome con diapositivas.</label>
        <label><input type="radio" name="q11" value="B"> b) Explicando verbalmente lo que sé.</label>
        <label><input type="radio" name="q11" value="C"> c) Moviéndome o haciendo demostraciones.</label>
      </div>

      <div class="question">
        <p><b>16. Si algo me llama la atención, suele ser...</b></p>
        <label><input type="radio" name="q12" value="A" required> a) Su apariencia.</label>
        <label><input type="radio" name="q12" value="B"> b) Su sonido.</label>
        <label><input type="radio" name="q12" value="C"> c) Su textura o funcionamiento.</label>
      </div>

      <div class="question">
        <p><b>17. Me resulta más fácil recordar...</b></p>
        <label><input type="radio" name="q13" value="A" required> a) Imágenes y colores.</label>
        <label><input type="radio" name="q13" value="B"> b) Conversaciones o sonidos.</label>
        <label><input type="radio" name="q13" value="C"> c) Lo que hice en una actividad.</label>
      </div>

      <div class="question">
        <p><b>18. Prefiero profesores que...</b></p>
        <label><input type="radio" name="q14" value="A" required> a) Usan imágenes, diagramas y pizarras.</label>
        <label><input type="radio" name="q14" value="B"> b) Explican con claridad y buen tono.</label>
        <label><input type="radio" name="q14" value="C"> c) Hacen talleres y prácticas.</label>
      </div>

      <div class="question">
        <p><b>19. Cuando estudio, me ayuda más…</b></p>
        <label><input type="radio" name="q15" value="A" required> a) Usar esquemas o resúmenes visuales.</label>
        <label><input type="radio" name="q15" value="B"> b) Escuchar explicaciones.</label>
        <label><input type="radio" name="q15" value="C"> c) Realizar ejercicios prácticos.</label>
      </div>

      <div class="question">
        <p><b>20. Cuando pienso en una palabra nueva...</b></p>
        <label><input type="radio" name="q16" value="A" required> a) Imagino cómo se escribe.</label>
        <label><input type="radio" name="q16" value="B"> b) La pronuncio mentalmente.</label>
        <label><input type="radio" name="q16" value="C"> c) Me imagino usándola en un contexto.</label>
      </div>

      <div class="question">
        <p><b>21. Si tengo que elegir un curso en línea prefiero...</b></p>
        <label><input type="radio" name="q17" value="A" required> a) Que tenga muchos recursos visuales.</label>
        <label><input type="radio" name="q17" value="B"> b) Que incluya audios o podcasts.</label>
        <label><input type="radio" name="q17" value="C"> c) Que tenga actividades interactivas.</label>
      </div>

      <div class="question">
        <p><b>22. Cuando estoy en clase, suelo...</b></p>
        <label><input type="radio" name="q18" value="A" required> a) Tomar apuntes con dibujos o colores.</label>
        <label><input type="radio" name="q18" value="B"> b) Escuchar con atención sin escribir mucho.</label>
        <label><input type="radio" name="q18" value="C"> c) Participar activamente con preguntas o ejercicios.</label>
      </div>

      <div class="question">
        <p><b>23. Al aprender mejoro si...</b></p>
        <label><input type="radio" name="q19" value="A" required> a) Puedo ver lo que estudio.</label>
        <label><input type="radio" name="q19" value="B"> b) Escucho explicaciones claras.</label>
        <label><input type="radio" name="q19" value="C"> c) Lo practico o lo aplico.</label>
      </div>

      <div class="question">
        <p><b>24. Prefiero libros que...</b></p>
        <label><input type="radio" name="q20" value="A" required> a) Tengan ilustraciones o gráficos.</label>
        <label><input type="radio" name="q20" value="B"> b) Sean narrativos o con diálogos.</label>
        <label><input type="radio" name="q20" value="C"> c) Tengan actividades al final de cada capítulo.</label>
      </div>

      <button type="submit">Ver Resultado</button>
    </form>

    <div id="resultado"></div>
  </div>

  <script>
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
