# qizzdio
<!DOCTYPE html>
<html>
<head>
	<title>Calculadora</title>
	<meta charset="UTF-8">
	<style>
		body {
			font-family: Arial, sans-serif;
			background-color: #f2f2f2;
			margin: 0;
			padding: 0;
		}

		h1 {
			color: #444444;
			margin-top: 20px;
			margin-bottom: 10px;
			text-align: center;
		}

		.container {
			width: 400px;
			margin: 0 auto;
			background-color: #ffffff;
			padding: 20px;
			border-radius: 5px;
			box-shadow: 0 2px 5px rgba(0, 0, 0, 0.3);
		}

		input[type="number"] {
			display: block;
			margin: 10px 0;
			padding: 10px;
			width: 100%;
			border: 1px solid #cccccc;
			border-radius: 3px;
			font-size: 16px;
			box-sizing: border-box;
		}

		input[type="submit"] {
			background-color: #4CAF50;
			color: #ffffff;
			padding: 10px 20px;
			border: none;
			border-radius: 3px;
			font-size: 16px;
			cursor: pointer;
		}

		input[type="submit"]:hover {
			background-color: #3e8e41;
		}

		.result {
			margin-top: 20px;
			padding: 10px;
			background-color: #cccccc;
			border-radius: 3px;
			font-size: 18px;
			text-align: center;
		}
	</style>
</head>
<body>
	<div class="container">
		<h1>Calculadora</h1>
		<form method="post">
			<input type="number" name="num1" placeholder="Digite o primeiro número" required>
			<input type="number" name="num2" placeholder="Digite o segundo número" required>
			<select name="operacao">
				<option value="soma">Soma</option>
				<option value="subtracao">Subtração</option>
				<option value="multiplicacao">Multiplicação</option>
				<option value="divisao">Divisão</option>
			</select>
			<input type="submit" value="Calcular">
		</form>
		<?php
			if(isset($_POST['num1']) && isset($_POST['num2']) && isset($_POST['operacao'])){
				$num1 = $_POST['num1'];
				$num2 = $_POST['num2'];
				$operacao = $_POST['operacao'];

				if(!empty($num1) && !empty($num2)){
					switch($operacao){
						case 'soma':
							$resultado = $num1 + $num2;
							echo "<div class='result'>O resultado da soma é: $resultado</div>";
							break;
						case 'subtracao':
							$resultado = $num1 - $num2;
							echo "<div class='result'>O resultado da subtração é: $resultado</div>";
							break;
						case 'multiplicacao':
							$resultado = $num1 * $num2;
							echo "<div class='result'>O resultado da multiplicação é: $resultado</div>";
