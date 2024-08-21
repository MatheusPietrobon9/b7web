# b7web
<?php

// Criando uma constante;
// Uma constante sempre vai possuir letras maisculas
// nunca vai ter seu valor alterado
// Não se redefini uma constante
define('IDADE_APOSENTADORIA_MASCULINA',65);
define('IDADE_APOSENTADORIA_FEMENINA',62);

// valores

$nome = 'Matheus';
$idade = 18;
$sexo = 'Masculino';
$salario_Mensal = 2210.30;
$salario_Anual = $salario_Mensal * 12;
$esta_empregado = true;
$habilidades = [
    'php', 'javaScript', 'html', 'css'
];

// Codigos

// operador ternario, RESUME o if
// variavel = () ? ... : ...;
// variavel = () ? valor_se_atender_condição : caso_não_atender_condição;

$situacao_emprego = null;
$situacao_emprego = $esta_empregado == true ? 'Empregado' : 'Desempregado';

   
// operador ternario, RESUME o if
$anos_necessarios_para_aposentar = null;
$anos_necessarios_para_aposentar = $sexo == 'Masculino' ? IDADE_APOSENTADORIA_MASCULINA : IDADE_APOSENTADORIA_FEMENINA;




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
        <p>Salário Anual: <strong><?php echo number_format($salario_Mensal * 12, 2, ',', '.') ; ?></strong></p>

        <p>Status de Emprego: <strong><?php echo $situacao_emprego; ?> </strong></p>

        <p>Anos para Aposentadoria: <strong><?php echo $anos_necessarios_para_aposentar - $idade; ?> </strong></p>


        <p>Habilidades: <strong><?php echo implode(', ', $habilidades); ?> </strong></p>

</div>
</div>
</body>
</html>
</body>
</html>
