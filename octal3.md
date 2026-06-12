---
layout: default
title: IC Student Quiz - Octal (3 dígitos)
---

# Ejemplo de ejercicio: Octal (3 dígitos)

{% capture macro_enunciado %}
<div style="border: 1px solid #000; padding: 20px; max-width: 650px; width: 100%; border-radius: 8px; background-color: #f9f9f9;"> 
Convierte ... a octal.
</div>
{% endcapture %}

{% capture macro_formato_y_ejemplo %}
Formato de respuesta: <b><u><a href="https://atc.unizar.es/mkgen/mkgen.html#N4Ig5iBcIPQwBAZgLQBMCWZ0Bd4HsBjbAQwBt4A3AUyLwCd4AKABzqoDN0APK1eAdxwALeAHIADKICUAHQB2AZxJ1cAXnisO3fEQD6GMDuz7MRk2HmbOXeOpkhx9+YWMHb8ANriAjACZEACwArABsAOwAuvLw8CAANCAKUB4O8SDeab5piGkAPmkBaUFpIWlhIBEJqFAgKAY4RmSUNNj0TFbcvALCYpJSaQRQ2HQArlQAvkA">vector de 3 dígitos octales (oct3)</a></u></b><br>
<table>
  <tr>
    <td style="padding: 15px 25px; vertical-align: top;">Ejemplos:</td>
    <td style="padding: 15px 25px; vertical-align: top;">0347</td>
    <td style="padding: 15px 25px; vertical-align: top;">0072</td>
    <td style="padding: 15px 25px; vertical-align: top;">0006</td>
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
 <option value="teclado_oct3.html" data-w="400" data-h="300" data-h-movil="370">oct3</option>
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

Nota: Si no usas el editor tinyMCE el paso 4 puede ser diferente. Puedes cambiar el editor en: Preferencias / Configuración del editor.

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
