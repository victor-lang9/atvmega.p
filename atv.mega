<?php

$jogos = [
    "Mega-Sena" => ["min" => 6, "max" => 20, "preco" => 4.50, "numeros" => 60],
    "Quina" => ["min" => 5, "max" => 15, "preco" => 1.50, "numeros" => 80],
    "Lotomania" => ["min" => 50, "max" => 50, "preco" => 2.50, "numeros" => 100],
    "Lotofácil" => ["min" => 15, "max" => 18, "preco" => 2.00, "numeros" => 25]
];

echo "Escolha um jogo: \n";
echo "1 - Mega-Sena\n2 - Quina\n3 - Lotomania\n4 - Lotofácil\n";
$jogoEscolhido = trim(fgets(STDIN));

switch ($jogoEscolhido) {
    case 1:
        $jogo = $jogos["Mega-Sena"];
        break;
    case 2:
        $jogo = $jogos["Quina"];
        break;
    case 3:
        $jogo = $jogos["Lotomania"];
        break;
    case 4:
        $jogo = $jogos["Lotofácil"];
        break;
    default:
        echo "Jogo inválido!\n";
        exit;
}

echo "Quantas apostas você deseja gerar? ";
$qtdApostas = (int) trim(fgets(STDIN));

echo "Quantas dezenas você deseja jogar (min {$jogo['min']}, max {$jogo['max']})? ";
$qtdDezenas = (int) trim(fgets(STDIN));

if ($qtdDezenas < $jogo['min'] || $qtdDezenas > $jogo['max']) {
    echo "Erro: O número de dezenas deve estar entre {$jogo['min']} e {$jogo['max']}.\n";
    exit;
}

function gerarAposta($jogo, $qtdDezenas) {
    $numeros = range(1, $jogo['numeros']);
    shuffle($numeros);
    $aposta = array_slice($numeros, 0, $qtdDezenas); 
    return $aposta;
}

$total = 0;
for ($i = 1; $i <= $qtdApostas; $i++) {
    $aposta = gerarAposta($jogo, $qtdDezenas);
    sort($aposta);
    echo "Aposta $i: " . implode(", ", $aposta) . "\n";
    $total += $jogo['preco'];
}

echo "\nTotal gasto: R$ " . number_format($total, 2, ',', '.') . "\n";

?>
