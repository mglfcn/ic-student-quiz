---
layout: default
title: IC Student Quiz - minterm
---

# Ejemplo de ejercicio: minterm de 6 variables

Formato de respuesta: m6v<br><meta charset="UTF-8">
<p>
<script type="text/javascript">
	
	    /////////////////////////////////////////////////////////////////
	    // Autor: Luis M. Ramos luisma@unizar.es
	    // Nombre: teclado_m6v
	    // minterm de 6 variables
	    // Ejemplo: x5·x4'·x3·x2'·x1'·x0
	    // url: https://webdiis.unizar.es/~luisma/ic/teclado_m6v.html
	    // Versión: 20/09/2023
	    /////////////////////////////////////////////////////////////////	
        var indice = 5;

        function and() {
            document.getElementById("result").textContent += "·";
            document.getElementById("result2").textContent = "";
            variable();
        }

        function not() {
            document.getElementById("result").textContent += "'";
            document.getElementById("result2").textContent = "";
            document.getElementById("idnot").disabled = true;
        }

        function operador_o_not() {
            if (indice >= 0) {
                document.getElementById("idand").disabled = false;
            }
            document.getElementById("idnot").disabled = false;
            document.getElementById("idx5").disabled = true;
            document.getElementById("idx4").disabled = true;
            document.getElementById("idx3").disabled = true;
            document.getElementById("idx2").disabled = true;
            document.getElementById("idx1").disabled = true;
            document.getElementById("idx0").disabled = true;
        }

        function variable() {
            document.getElementById("idnot").disabled = true;
            document.getElementById("idand").disabled = true;
            if (indice == 5) document.getElementById("idx5").disabled = false;
            if (indice == 4) document.getElementById("idx4").disabled = false;
            if (indice == 3) document.getElementById("idx3").disabled = false;
            if (indice == 2) document.getElementById("idx2").disabled = false;
            if (indice == 1) document.getElementById("idx1").disabled = false;
            if (indice == 0) document.getElementById("idx0").disabled = false;

        }

        function x5() {
            document.getElementById("result").textContent += "x5";
            document.getElementById("result2").textContent = "";
            indice = 4;
            operador_o_not();
        }

        function x4() {
            document.getElementById("result").textContent += "x4";
            document.getElementById("result2").textContent = "";
            indice = 3;
            operador_o_not();
        }

        function x3() {
            document.getElementById("result").textContent += "x3";
            document.getElementById("result2").textContent = "";
            indice = 2;
            operador_o_not();
        }

        function x2() {
            document.getElementById("result").textContent += "x2";
            document.getElementById("result2").textContent = "";
            indice = 1;
            operador_o_not();
        }

        function x1() {
            document.getElementById("result").textContent += "x1";
            document.getElementById("result2").textContent = "";
            indice = 0;
            operador_o_not();
        }

        function x0() {
            document.getElementById("result").textContent += "x0";
            document.getElementById("result2").textContent = "";
            indice = -1;
            operador_o_not();
        }

        function borrar() {
            document.getElementById("result").textContent = "";
            document.getElementById("result2").textContent = "";
            indice = 5;
            variable();
            document.getElementById("idcopiar").disabled = false;
        }

        function copiar() {
            navigator.clipboard.writeText(document.getElementById('result').innerHTML);
            document.getElementById("result2").textContent = " Copiado. Pégalo ahora abajo.";
        }
</script>
</p><label>Pulsa los botones para generar tu respuesta y copia-pega.</label><br>
<input id="idand" type="button" value="·" onclick="and()" disabled="true" style="font-size:30px; height:50px; width:50px">
<input id="idnot" type="button" value="'" onclick="not()" disabled="true" style="font-size:30px; height:50px; width:50px">
<br>
<input id="idx5" type="button" value="x5" onclick="x5()" style="font-size:30px; height:50px; width:50px">
<input id="idx4" type="button" value="x4" onclick="x4()" disabled="true" style="font-size:30px; height:50px; width:50px">
<input id="idx3" type="button" value="x3" onclick="x3()" disabled="true" style="font-size:30px; height:50px; width:50px">
<input id="idx2" type="button" value="x2" onclick="x2()" disabled="true" style="font-size:30px; height:50px; width:50px">
<input id="idx1" type="button" value="x1" onclick="x1()" disabled="true" style="font-size:30px; height:50px; width:50px">
<input id="idx0" type="button" value="x0" onclick="x0()" disabled="true" style="font-size:30px; height:50px; width:50px">
<br>
<input type="button" value="borrar" onclick="borrar()" style="height:50px; width:50px">
<input id="idcopiar" type="button" value="copiar" onclick="copiar()" style="height:50px; width:50px">
<div id="result" style="font-size:30px;"></div>
<div id="result2">
</div>   ----------------------------------<br>Sea Z una función booleana de 6 variables Z(x5, x4, ... x0).<br>Indica cuál es su minterm m<sub>i</sub>

# Instrucciones

Para crear una pregunta Moodle de este estilo:
1. Copia el código de abajo pulsando el botón. 
2. Ve a la actividad 'IC Student Quiz' y pulsa el botón 'Crear pregunta nueva'.
   Elige tipo de pregunta 'Respuesta corta'.
3. En el campo 'Enunciado de la pregunta'  pulsa el botón ⮧ para mostrar más botones y pulsa el botón </> para mostrar el código html. 
4. Pega el código y vuelve a pulsar </> para ocultar el código html.
5. Adapta el enunciado a tu pregunta.

# Código

<button onclick="copiar_codigo()">Copiar código iframe</button>
<script>
function copiar_codigo() {
  const codigo = '<iframe src="https://webdiis.unizar.es/~luisma/ic/teclado_inst.html"
width="320"
height="350"
style="border:none;"></iframe>';
  navigator.clipboard.writeText(codigo);
  alert("Código copiado al portapapeles");
}
</script>
