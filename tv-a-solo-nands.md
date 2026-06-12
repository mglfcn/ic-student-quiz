---
layout: default
title: IC Student Quiz - TV a solo NANDs
---

# Ejemplo de ejercicio: TV → forma canónica / forma mínima → solo NANDs

{% capture macro_enunciado %}
<div style="border: 1px solid #000; padding: 20px; max-width: 650px; width: 100%; border-radius: 8px; background-color: #f9f9f9;"> 
Obtén la [1ªFC/2ªFC/mínima suma de productos/mínimo producto de sumas] de la función Z y exprésala usando solo puertas {NAND,NOT}.<br>Una vez calculada la forma canónica/mínima solo puedes aplicar  el teorema de involución y la ley de De Morgan.<br><br>
    <table style="text-align: center;" border="1" frame="border" rules="groups">
    <colgroup align="center" span="3">
    </colgroup>
    <thead>
        <tr>
            <th scope="col" style="text-align: center;">&nbsp;a&nbsp;</th>
            <th scope="col" style="text-align: center;">&nbsp;b&nbsp;</th>
            <th scope="col" style="text-align: center;">&nbsp;c&nbsp;</th>
            <th scope="col" style="text-align: center;"> &nbsp;Z&nbsp;</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="text-align: center;">0</td>
            <td style="text-align: center;">0</td>
            <td style="text-align: center;">0</td>
            <td style="text-align: center;">x</td>
        </tr>
        <tr>
            <td style="text-align: center;">0</td>
            <td style="text-align: center;">0</td>
            <td style="text-align: center;">1</td>
            <td style="text-align: center;">x</td>
        </tr>
        <tr>
            <td style="text-align: center;">0</td>
            <td style="text-align: center;">1</td>
            <td style="text-align: center;">0</td>
            <td style="text-align: center;">x</td>
        </tr>
        <tr>
            <td style="text-align: center;">0</td>
            <td style="text-align: center;">1</td>
            <td style="text-align: center;">1</td>
            <td style="text-align: center;">x</td>
        </tr></tbody><tbody>
        <tr>
            <td style="text-align: center;">1</td>
            <td style="text-align: center;">0</td>
            <td style="text-align: center;">0</td>
            <td style="text-align: center;">x</td>
        </tr>
        <tr>
            <td style="text-align: center;">1</td>
            <td style="text-align: center;">0</td>
            <td style="text-align: center;">1</td>
            <td style="text-align: center;">x</td>
        </tr>
        <tr>
            <td style="text-align: center;">1</td>
            <td style="text-align: center;">1</td>
            <td style="text-align: center;">0</td>
            <td style="text-align: center;">x</td>
        </tr>
        <tr>
            <td style="text-align: center;">1</td>
            <td style="text-align: center;">1</td>
            <td style="text-align: center;">1</td>
            <td style="text-align: center;">x</td>
        </tr>
    </tbody>
</table>
</div>
{% endcapture %}

{% capture macro_formato_y_ejemplo %}
Formato de respuesta: <b><u><a href="https://atc.unizar.es/mkgen/mkgen.html#N4Ig5iBcIPQwBAUwB4AcBOiDOWCWB7AO3gFc9Cx4iAbAT3gDkBBBgEXgENCATRgeQAq8MBwAu2ADqEpWUR3Sj48ALxKGXbn3QBVQvNpSp6nlt36VjDQFE06KUoRn0tGxkOFj3V3eIWnL23gACngJEEBEwjD4f28ASgBqdxjbewsmUXwAW1CQAHIw1IR0rPdi7NUANXlcDgAjakRC+AAFeURCbybWzA7AsPyQUOlCbvbvCzCgqM9xsNiC4ar0GvrECwBtOoBjbgBdKRAAGhAsKHWIo7zLgB9Ljkvay63L7hvLoMvYkF3j1+gUDDYPBEUjkSg0ejMNicHj8IQicSnY7PSCidAkRAAXyAA">exp usando solo {NAND,NOT} (NAND)</a></u></b><br>
  
<table>
  <tr>
    <td style="padding: 15px 25px; vertical-align: top;">Ejemplos:</td>
    <td style="padding: 15px 25px; vertical-align: top;">((a↑b’)↑c)’</td>
    <td style="padding: 15px 25px; vertical-align: top;">a↑b’↑c</td>
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
 <option value="teclado_NAND.html" data-w="400" data-h="250" data-h-movil="320">NAND</option>
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
7. Para permitir permutaciones teclea la respuesta en uno de los formularios de abajo y te indicará el valor a poner en el campo 'Respuesta 2'.

Nota: Si no usas el editor tinyMCE el paso 4 puede ser diferente. Puedes cambiar el editor en: Preferencias / Configuración del editor.

<iframe width="500" height="350" style="border:none;" src="https://mglfcn.github.io/ic-student-quiz/kb/ic/teclado_regexp_sdp_NAND.html" allow="clipboard-read; clipboard-write"></iframe>  
<iframe width="500" height="350" style="border:none;" src="https://mglfcn.github.io/ic-student-quiz/kb/ic/teclado_regexp_pds_NAND.html" allow="clipboard-read; clipboard-write"></iframe> 


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
