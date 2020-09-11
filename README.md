# Atividade-Virtual-2

#HTML

<!DOCTYPE html>
<html>
	<head>
		<title>
			MultiCalculadora
		</title>
	</head>
	<style rel="stylesheet" href="bordas.css" />
	<script src="scriptMulti.js"></script>
	<body>
		<fieldset class="fieldset-border">
			<legend class="legend-border">MultiCalculadora</legend>
			<br>
				<input name="options" type="radio" id="radio1" onclick="mostraI()" checked="checked">IMC
				<input name="options" type="radio" id="radio2" onclick="mostraR()">Retângulo
				<input name="options" type="radio" id="radio3" onclick="mostraC()">Círculo
			</br>
			<p id="label">
				Peso:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<input type="text" name="peso" id="peso" size="10">
				<br><br>Altura:&nbsp;&nbsp;<input type="text" name="altura" id="alt" size="10"></br></br>
				<button type="button" onclick="calcularImc();">Calcular</button>
			</p>
			<p id="label1" style="display:none">
				Base:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<input type="text1" name="base" id="base" size="10">
				<br><br>Altura:&nbsp;&nbsp;<input type="text1" name="altura1" id="alt1" size="10"></br></br>
				<button type="button" onclick="calcularRetangulo();">Calcular</button>
			</p>
			<p id="label2" style="display:none">
				Raio:&nbsp;&nbsp;<input type="text1" name="base" id="raio" size="10">
				<br><br><button type="button" onclick="calcularCirculo();">Calcular</button></br></br>
			</p>
		</fieldset>
	</body>
</html>

#CSS

.fieldset-border {
  border: 1px groove #ddd !important;
  padding: 0 1.4em 1.4em 1.4em !important;
  margin: 0 0 1.5em 0 !important;
  -webkit-box-shadow: 0px 0px 0px 0px #000;
  box-shadow: 0px 0px 0px 0px #000;
}

.fieldset-border .legend-border {
  font-size: 1.2em !important;
  text-align: left !important;
  width: auto;
  padding: 0 10px;
  border-bottom: none;
}


#JS

function mostraI() {
	if (document.getElementById("radio1").checked == true){
		document.getElementById("label").style.display = "block";
		document.getElementById("label1").style.display = "none";
		document.getElementById("label2").style.display = "none";
	} else {
		document.getElementById("label").style.display = "none";
	}
}

function mostraR() {
	if (document.getElementById("radio2").checked == true){
		document.getElementById("label1").style.display = "block";
		document.getElementById("label").style.display = "none";
		document.getElementById("label2").style.display = "none";
	} else {
		document.getElementById("label1").style.display = "none";
	}
}
	
function mostraC() {
	if (document.getElementById("radio3").checked == true){
		document.getElementById("label2").style.display = "block";					
		document.getElementById("label1").style.display = "none";
		document.getElementById("label").style.display = "none";
	} else {
		document.getElementById("label2").style.display = "none";
	}
}
				
function calcularImc(){
	var num1 = document.getElementById("peso").value;
	var num2 = document.getElementById("alt").value;
	var imc = (parseFloat(num1)/(parseFloat(num2)*(parseFloat(num2))));
	alert("IMC: " + imc);
}

function calcularRetangulo(){
	var num3 = document.getElementById("base").value;
	var num4 = document.getElementById("alt1").value;
	var area = (parseFloat(num3))*(parseFloat(num4));
	alert("Área do Retângulo: " + area);
}		
				
function calcularCirculo(){
	var num5 = document.getElementById("raio").value;
	var areaCirc = Math.PI*(parseFloat(num5)*parseFloat(num5));
	alert("Área do Círculo: " + areaCirc);
}

