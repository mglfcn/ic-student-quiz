---
layout: default
title: IC Student Quiz - minterm
---

# Ejemplo de ejercicio: minterm de 6 variables

Sea Z una función booleana de 6 variables Z(x5, x4, ... x0).<br>
Indica cuál es su minterm m<sub>i</sub>

Pulsa en el botón para generar la respuesta en el formato: <a href="teclado_m6v.html" target="_blank">m6v</a>

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
</textarea>
<script>
function copiar_codigo(){
  const texto = document.getElementById("codigo").value;
  navigator.clipboard.writeText(texto);
  alert("Código copiado");
}
</script>
