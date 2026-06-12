---
layout: default
title: IC Student Quiz - Diseño canónico
---

# Ejemplo de ejercicio: Diseño canónico (codificando estados como naturales)

{% capture macro_enunciado %}
<div style="border: 1px solid #000; padding: 20px; max-width: 650px; width: 100%; border-radius: 8px; background-color: #f9f9f9;"> 
Saca la tabla de transición y obtén la expresión mínima suma de productos del bit ... del siguiente autómata.<br>
Codifica los estados según se indica en la tabla. No olvides aprovechar los don't cares (si los hay).
</div>
{% endcapture %}

{% capture macro_formato_y_ejemplo %}
Formato de respuesta: <b><u><a href="https://atc.unizar.es/mkgen/mkgen.html#N4Ig5iBcIPQwBAZwK4Ft4HsBm8AOAnDAE2QGMAXReAdwEtyALeUgQwDsM3bWAbZ42mzDwAFBnxEApvklF4ANxb5aLAEY9JiAJQAdNnBqT4M0hlSpJbOckSDhjI4BwCAEqSwyHkvgBRAB4FNW054AGUGcXJ4AEE2RGppQFwCPB5kMEF4cgx4Fh4eDGo8aVRkchZyWk4qbAyGIwJiMkp4dIckND09RFL8SPgAXiQO2P6MotEdEABqCaQtACoh8jGRgEcARnGQAHaZlYAGLQB+TZ2QeAANI714G5uEeH2TmcvD69v4e-Oh9ZuBifWAOQzBD-NYTPSPEb-PZAs4gkD7cFsc63P4gc6wj7wCZfEAgAA0IEQUAA2tsCVMKQCKQAfCnrel7CnnEAAXUJRCgRLQmBw9RIFCodEYzHYnG4OX4RDsonEUhkckUyjUGm0FNIUHI+GQkgAvkA">suma de productos (var. ord. en productos) (sdp)</a></u></b><br>
  
<table>
  <tr>
    <td style="padding: 15px 25px; vertical-align: top;">Ejemplo:</td>
    <td style="padding: 15px 25px; vertical-align: top;">q1·X+q0'·X'+q1'</td>
  </tr>
</table><br>
{% endcapture %}

{% capture macro_teclado_enlace %}
<div id="div1" style="border: 1px solid #000; padding: 20px; max-width: 650px; width: 100%; border-radius: 8px; background-color: #f9f9f9;"> 
{{ macro_formato_y_ejemplo }}
Pulsa en el enlace para acceder al teclado.<br>
Luego pulsa el botón '← Atrás' del navegador para volver.
</div>
{% endcapture %}

{% capture macro_teclado_incrustado %}
<div id="div2" style="border: 1px solid #000; padding: 20px; max-width: 650px; width: 100%; border-radius: 8px; background-color: #f9f9f9;"> 
{{ macro_formato_y_ejemplo }}
<select id="pagina" onchange="cargarPagina()">
 <option value="teclado_sdp3.html" data-w="400" data-h="250" data-h-movil="320">sdp</option>
</select>
  <button type="button" onclick="recargar()">↻ Recargar teclado</button><br>

 <iframe id="visor" style="border:none; max-width: 100%;" allow="clipboard-read; clipboard-write">
 </iframe>
</div>

{% include mi_script.md %}
{% endcapture %}

{{ macro_enunciado }}
{{ macro_teclado_enlace }}
{{ macro_teclado_incrustado }}

# Instrucciones

Para crear una pregunta Moodle de este estilo:
<!-- 1. Elige la versión <button onclick="mostrar_div1()">Con teclado enlazado (sí funciona en StudentQuiz)</button>   <button onclick="mostrar_div2()">Con teclado incrustado (no funciona en StudentQuiz)</button> -->
1. Pulsa este botón para copiar el código <button onclick="copiar_codigo()">Copiar código</button>
2. Ve a la actividad 'IC Student Quiz', pulsa el botón 'Crear pregunta nueva' y elige tipo de pregunta 'Respuesta corta'.
3. Pon un nombre a tu pregunta.
4. En el campo 'Enunciado de la pregunta' selecciona la opción '<> Código fuente' del menú 'Ver'.
5. Pega el código (Ctrl-v), adapta el enunciado a tu pregunta y pulsa el botón 'Guardar'.
6. En el campo 'Respuesta' indica la respuesta y su calificación.
7. Para permitir permutaciones teclea la respuesta en el formulario de abajo y te indicará el valor a poner en el campo 'Respuesta 2'.

Nota: Si no usas el editor tinyMCE el paso 4 puede ser diferente. Puedes cambiar el editor en: Preferencias / Configuración del editor.

<iframe width="600" height="350" style="border:none;" src="https://webdiis.unizar.es/~luisma/ic/teclado_regexp_sdp.html" allow="clipboard-read; clipboard-write"></iframe>   

<textarea id="codigo_div1" style="display:none;">
{{ macro_enunciado }}
{{ macro_teclado_enlace }}
</textarea>

<textarea id="codigo_div2" style="display:none;">
{{ macro_enunciado }}
{{ macro_teclado_incrustado }}
</textarea>

<script>
function copiar_codigo(){
 if (version_div==1){
  const texto = document.getElementById("codigo_div1").value;
  navigator.clipboard.writeText(texto);
  alert("Copiado código con teclado enlazado");
 }else {
  const texto = document.getElementById("codigo_div2").value;
  navigator.clipboard.writeText(texto);
  alert("Copiado código con teclado incrustado (no funciona en StudentQuiz)");
 }
}

function mostrar_div1(){
 version_div=1;
 document.getElementById("div2").style.display = "none";
 document.getElementById("div1").style.display = "block";
}
function mostrar_div2(){
 version_div=2;
 document.getElementById("div1").style.display = "none";
 document.getElementById("div2").style.display = "block";
}
let version_div=1; 
document.getElementById("div2").style.display = "none";
 
</script>
