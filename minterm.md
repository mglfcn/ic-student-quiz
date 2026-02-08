---
layout: default
title: IC Student Quiz - minterm
---

# Ejemplo de ejercicio: minterm de 6 variables

<div style="border: 1px solid #000; padding: 20px; width: 650px; border-radius: 8px; background-color: #f9f9f9;">
Sea Z una función booleana de 6 variables Z(x5, x4, ... x0).<br>
Indica cuál es su minterm m<sub>i</sub><br>
</div>

<div id="contenedorIframe" style="border: 1px solid #000; padding: 10px; width: 650px; border-radius: 8px; background-color: #f9f9f9;">
Formato de respuesta:
<select id="pagina" onchange="cargarPagina()">
 <option value="teclado_m6v.html" data-w="400" data-h="250" data-h-movil="320">m6v</option>
 <!-- <option value="teclado_m6v.html" data-w="650" data-h="200" data-h-movil="320">m6v</option> -->
</select>
<button type="button" onclick="recargar()">↻ Recargar teclado</button>

 <iframe id="visor" style="border:none; max-width: 100%;" allow="clipboard-read; clipboard-write">
 </iframe>
</div>

<script>
 const servidores = [
  //"https://mglfcn.github.io/mkgen/",
  //"https://webdiis.unizar.es/~luisma/mkgen/kb/",
  "kb/ic/", //comentar este en el textarea
  //"https://mglfcn.github.io/ic-student-quiz/kb/ic/", // comentar este en github
  "https://webdiis.unizar.es/~luisma/ic/"
 ];

 let servidorActual = 0;

 function cargarPagina() {
  servidorActual = 0;
  actualizarIframe();
 }

 function recargar() {
  servidorActual = (servidorActual + 1) % servidores.length;
  actualizarIframe();
 }

 function actualizarIframe() {
  const select = document.getElementById("pagina");
  const option = select.options[select.selectedIndex];

  const iframe = document.getElementById("visor");

  // tamaño específico por página
  iframe.width = option.dataset.w;
  if (esMovil() && option.dataset.hMovil) {
   iframe.height = option.dataset.hMovil;
  } else {
   iframe.height = option.dataset.h;
  }

  // URL final
  iframe.src = servidores[servidorActual] + option.value;
 }

 function esMovil() {
  return window.innerWidth < 450;
 }
 cargarPagina();
</script>

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

<div style="border: 1px solid #000; padding: 20px; max-width: 650px; width: 100%; border-radius: 8px; background-color: #f9f9f9;">
Sea Z una función booleana de 6 variables Z(x5, x4, ... x0).<br>
Indica cuál es su minterm m<sub>i</sub><br>
</div>

<div id="contenedorIframe" style="border: 1px solid #000; padding: 10px; max-width: 650px; width: 100%; border-radius: 8px; background-color: #f9f9f9;">
Formato de respuesta:
<select id="pagina" onchange="cargarPagina()">
 <option value="teclado_m6v.html" data-w="400" data-h="250" data-h-movil="320">m6v</option>
 <!-- <option value="teclado_m6v.html" data-w="650" data-h="200" data-h-movil="320">m6v</option> -->
</select>
<button type="button" onclick="recargar()">↻ Recargar teclado</button>

 <iframe id="visor" style="border:none; max-width: 100%;" allow="clipboard-read; clipboard-write">
 </iframe>
</div>

<script>
 const servidores = [
  //"https://mglfcn.github.io/mkgen/",
  //"https://webdiis.unizar.es/~luisma/mkgen/kb/",
  //"kb/ic/", //comentar este en el textarea
  "https://mglfcn.github.io/ic-student-quiz/kb/ic/", // comentar este en github
  "https://webdiis.unizar.es/~luisma/ic/"
 ];

 let servidorActual = 0;

 function cargarPagina() {
  servidorActual = 0;
  actualizarIframe();
 }

 function recargar() {
  servidorActual = (servidorActual + 1) % servidores.length;
  actualizarIframe();
 }

 function actualizarIframe() {
  const select = document.getElementById("pagina");
  const option = select.options[select.selectedIndex];

  const iframe = document.getElementById("visor");

  // tamaño específico por página
  iframe.width = option.dataset.w;
  if (esMovil() && option.dataset.hMovil) {
   iframe.height = option.dataset.hMovil;
  } else {
   iframe.height = option.dataset.h;
  }

  // URL final
  iframe.src = servidores[servidorActual] + option.value;
 }

 function esMovil() {
  return window.innerWidth < 450;
 }
 cargarPagina();
</script>

</textarea>

<script>
function copiar_codigo(){
  const texto = document.getElementById("codigo").value;
  navigator.clipboard.writeText(texto);
  alert("Código copiado");
}
</script>
