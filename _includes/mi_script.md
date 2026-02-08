<script>
 const servidores = [
  //"https://mglfcn.github.io/mkgen/",
  //"https://webdiis.unizar.es/~luisma/mkgen/kb/",
  //"kb/ic/", //no funciona en el textarea (para Moodle)
  //"/ic-student-quiz/kb/ic/", //no funciona en el textarea (para Moodle)
  "https://mglfcn.github.io/ic-student-quiz/kb/ic/",
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

function copiar_codigo(){
 const texto = document.getElementById("codigo").value;
 navigator.clipboard.writeText(texto);
 alert("Código copiado");
}
  
 cargarPagina();
</script>
