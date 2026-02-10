---
layout: default
title: IC Student Quiz - Tabla de Verdad
---

# Ejemplo de ejercicio: Tabla de Verdad

{% capture macro_enunciado %}
<div style="border: 1px solid #000; padding: 20px; max-width: 650px; width: 100%; border-radius: 8px; background-color: #f9f9f9;"> 
Obtén la tabla de verdad de ...
</div>
{% endcapture %}

{% capture macro_formato_y_ejemplo %}
Formato de respuesta: <a href="https://webdiis.unizar.es/~luisma/ic/teclado_TV.html">vector de bits de una TV</a> <b><u><a href="https://mglfcn.github.io/ic-student-quiz/kb/ic/teclado_TV.html">(TV)</a></u></b><br>
Ejemplo: 00011101<br><br>
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
 <option value="teclado_TV.html" data-w="400" data-h="600" data-h-movil="600">TV</option>
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
1. Elige la versión <button onclick="mostrar_div1()">Con teclado enlazado (sí funciona en StudentQuiz)</button>   <button onclick="mostrar_div2()">Con teclado incrustado (no funciona en StudentQuiz)</button>
2. Pulsa este botón para copiar el código <button onclick="copiar_codigo()">Copiar código</button>
3. Ve a la actividad 'IC Student Quiz', pulsa el botón 'Crear pregunta nueva' y elige tipo de pregunta 'Respuesta corta'.
4. Pon un nombre a tu pregunta.
5. En el campo 'Enunciado de la pregunta' selecciona la opción '<> Código fuente' del menú 'Ver'.
6. Pega el código (Ctrl-v), adapta el enunciado a tu pregunta y pulsa el botón 'Guardar'.
7. En el campo 'Respuesta' indica la respuesta y su calificación.

Nota: Si no usas el editor tinyMCE el paso 5 puede ser diferente. Puedes cambiar el editor en: Preferencias / Configuración del editor.

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
  alert("Copiado código con teclado enlazado (sí funciona en StudentQuiz)");
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
