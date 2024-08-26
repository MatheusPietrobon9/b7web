// FAIXA CADASTRAL
<?php


require 'constantes.php';
include 'dados.php';
require 'functions.php';



   
?>

<!-- estrutura HTML pro CSS -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Explorando Variáveis em PHP</title>
<style>
                          /* css */
body{
display: flex;
justify-content: center;
align-items: center;
height: 100vh;
margin: 0;
}
.container{
display: flex;
justify-content: center;
align-items: center;
height: 100%;
}
.card{
background: #fff;
border-radius: 8px;
box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
padding: 20px;
max-width: 400px;
text-align: center;
}
h1{
color: #333;
}
p{
color: #666;
font-size: 1.1em;
}
strong{
color: #000;
}
</style>
</head>

<body>
    <!-- FICHA CADASTRAL -->
    <div class="container">
    <div class="card">
        <h1>Ficha Cadastral</h1>
        <p>Nome: <strong><?php echo $nome; ?> </strong></p>
        <p>Idade: <strong><?php echo $idade;?> </strong></p>
        <p>Sexo: <strong><?php echo $sexo; ?> </strong></p>
        <p>Salário Mensal: <strong><?php echo number_format($salario_Mensal, 2, ',', '.'); ?> </strong></p>
        <p>Salário Anual: <strong><?php echo CalcularSalarioAnual($salario_Mensal) ; ?></strong></p>

        <p>Status de Emprego: <strong><?php echo $esta_empregado == true ? 'Empregado' : 'Desempregado'; ?> </strong></p>

        <p>Anos para Aposentadoria: <strong><?php echo $anos_necessarios_para_aposentar - $idade; ?> </strong></p>


        <p>Habilidades: <strong><?php echo implode(', ', $habilidades); ?> </strong></p>

</div>
</div>
</body>
</html>
</body>
</html>

















//Dados.php

<?php 


$nome = 'Matheus';
$idade = 18;
$sexo = 'Masculino';
$salario_Mensal = 2210.30;
$esta_empregado = true;
$habilidades = [
    'php', 'javaScript', 'html', 'css'
];

$anos_necessarios_para_aposentar = $sexo == 'M' ? IDADE_APOSENTADORIA_MASCULINA : IDADE_APOSENTADORIA_FEMENINA;

$situacao_emprego = $esta_empregado == true ? 'Empregado' : 'Desempregado';



// FUNCTION.PHP

<?php 

// Calculo do Salario Anual

/**
 * Uma função para descobrir o salario anual
 * 
 * @param float $salario_Mensal Um calculo para q o salario mensal, descubra o salario anual no caso * 12;
 * @param float $salarioAnual Resultado do salario anual
 * 
 * @return float retorna o salario anual
 */
function CalcularSalarioAnual(float $salario_Mensal) : string  {
    $tercoDeFerias = $salario_Mensal / 3;
    $salarioAnual = ($salario_Mensal * 13) + $tercoDeFerias;
    return convertNumberToBrl($salarioAnual);
};

// Quantos anos faltam para se aposentar


// Transformar um Numero, em valor monetário;

/**
 * Transforma os numeros para modo normal Brasileiro
 * 
 * @param float $number valor numerico
 * @return string $valor monetario
 */
function convertNumberToBrl(float $number) : string {
   return  number_format($number, 2, ',', '.');
}



//CONSTANTES.PHP

<?php

// Criando uma constante;
// Uma constante sempre vai possuir letras maisculas
// nunca vai ter seu valor alterado
// Não se redefini uma constante


define('IDADE_APOSENTADORIA_MASCULINA',65);
define('IDADE_APOSENTADORIA_FEMENINA',62);



