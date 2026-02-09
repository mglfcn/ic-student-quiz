---
layout: default
title: IC Student Quiz - minterm
---

# Ejemplo de ejercicio: minterm de 6 variables

{% capture macro_enunciado %}
<div style="border: 1px solid #000; padding: 20px; max-width: 650px; width: 100%; border-radius: 8px; background-color: #f9f9f9;"> 
Sea Z una función booleana de 6 variables Z(x5, x4, ... x0).<br>
Indica cuál es su minterm m<sub>i</sub>
</div>
{% endcapture %}

{% capture macro_teclado_incrustado %}
<div style="border: 1px solid #000; padding: 20px; max-width: 650px; width: 100%; border-radius: 8px; background-color: #f9f9f9;"> 
Formato de respuesta: minterm de 6 variables
 
<select id="pagina" onchange="cargarPagina()">
 <option value="teclado_m6v.html" data-w="400" data-h="250" data-h-movil="320">m6v</option>
</select><br>
Ejemplo: x5’·x4·x3’·x2·x1’·x0<br>
<button type="button" onclick="recargar()">↻ Recargar teclado</button><br>

 <iframe id="visor" style="border:none; max-width: 100%;" allow="clipboard-read; clipboard-write">
 </iframe>
</div>

{% include mi_script.md %}
 
{% endcapture %}

{% capture macro_teclado_enlace %}

<div style="border: 1px solid #000; padding: 20px; max-width: 650px; width: 100%; border-radius: 8px; background-color: #f9f9f9;"> 
Formato de respuesta: minterm de 6 variables <b><u><a href="https://mglfcn.github.io/ic-student-quiz/kb/ic/teclado_m6v.html">m6v</a></u></b><br>
Ejemplo: x5’·x4·x3’·x2·x1’·x0<br>
Las preguntas StudentQuiz de Moodle no soportan teclados incrustados.<br>
Pulsa en el enlace para acceder al teclado en otra pestaña.
</div>
 
{% endcapture %}
{{ macro_enunciado }}
// elegir entre macro_teclado_incrustado y macro_teclado_enlace (también en el texarea linea 61)
{{ macro_teclado_enlace }}

# Instrucciones

Para crear una pregunta Moodle de este estilo:
1. Pulsa este botón para copiar el código <button onclick="copiar_codigo()">Copiar código</button>
2. Ve a la actividad 'IC Student Quiz', pulsa el botón 'Crear pregunta nueva' y elige tipo de pregunta 'Respuesta corta'.
3. Pon un nombre a tu pregunta.
4. En el campo 'Enunciado de la pregunta' selecciona la opción '<> Código fuente' del menú 'Ver'.
5. Pega el código (Ctrl-v), adapta el enunciado a tu pregunta y pulsa el botón 'Guardar'.
6. En el campo 'Respuesta' indica la respuesta y su calificación.

Nota: Si no usas el editor tinyMCE el paso 4 puede ser diferente. Puedes cambiar el editor en: Preferencias / Configuración del editor.

<textarea id="codigo" style="display:none;">
{{ macro_enunciado }}
{{ macro_teclado_enlace }}
</textarea>

<script>
function copiar_codigo(){
 const texto = document.getElementById("codigo").value;
 navigator.clipboard.writeText(texto);
 alert("Código copiado");
}
</script>
