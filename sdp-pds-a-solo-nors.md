---
layout: default
title: IC Student Quiz - sdp/pds a solo NORs
---

# Ejemplo de ejercicio: suma de productos / producto de sumas → solo NORs

{% capture macro_enunciado %}
<div style="border: 1px solid #000; padding: 20px; max-width: 650px; width: 100%; border-radius: 8px; background-color: #f9f9f9;"> 
Expresa ... usando solo puertas NOR de cualquier número de entradas y puertas NOT.
Solo puedes aplicar el teorema de involución y la ley de De Morgan.
</div>
{% endcapture %}

{% capture macro_formato_y_ejemplo %}
Formato de respuesta: <b><u><a href="https://atc.unizar.es/mkgen/mkgen.html#N4Ig5iBcIPQwBAUwB4AcBOiDOWCWB7AO3gFc9Cx4iAbAT3gDkB5AJXgENCATRpgFXhh2AF2wAdQhKzD26YfHgBeBQ3zom6AKqFZtCRNXqtO9PWWGAomnQSFCbbqsZ9hS9dtL4D00-TwAFPBiIIDJhMFeJrS+AJQA1C7eUe7EngCCwvgAtkEgAOTBHgjpWS7F2coAarK47ABG1IiF8AAKsoiEvk2tmB3WOfkgQZKE3e2+nsH+4W4YOdEFw1XoNfWIngDadQDGXAC6EiAANCBYUOuhR3mXAD6X7Je1l1uXXDeX-pfRILvHr9AoGGweCIpHIlBo9GYbE4PGYAiEolOx2ekGE6BIiAAvkA">exp usando solo {NOR,NOT} (NOR)</a></u></b><br>
  
<table>
  <tr>
    <td style="padding: 15px 25px; vertical-align: top;">Ejemplos:</td>
    <td style="padding: 15px 25px; vertical-align: top;">(a’↓b)↓(c’↓d)</td>
    <td style="padding: 15px 25px; vertical-align: top;">(a’↓b↓c’↓d)’</td>
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
 <option value="teclado_NOR.html" data-w="400" data-h="250" data-h-movil="320">NOR</option>
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
