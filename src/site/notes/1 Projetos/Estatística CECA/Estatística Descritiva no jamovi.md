---
{"dg-publish":true,"permalink":"/1 Projetos/Estatística CECA/Estatística Descritiva no jamovi/","tags":["gardenEntry"],"dg-note-properties":{}}
---

# Estatística Descritiva no jamovi

**Trilha 1 — Dados que sustentam decisões · Módulos I e II**

_Material adaptado de Foxcroft, D.R. & Navarro, D.J. — Learning Statistics with jamovi (2025), Capítulo 4, sob licença CC BY-SA 4.0. Os exemplos numéricos deste material usam dados reais do Estudo de Caso 1 (monitoramento da broca-da-cana)._

---

## Por que precisamos de estatística descritiva

Toda vez que você recebe um conjunto de dados novo, a primeira tarefa é encontrar uma forma de resumi-lo — compacta e fácil de entender. É disso que trata a **estatística descritiva**, em oposição à estatística inferencial. Para boa parte das pessoas, aliás, "estatística" é sinônimo de estatística descritiva: médias, percentuais, desvios. É nisso que vamos nos concentrar aqui.

Para sentir por que isso é necessário, abra a aba **«Dados»** da planilha `EC1_monitoramento_broca.xlsx` no jamovi. Ali estão os 10 pontos amostrais do talhão A — Boa Esperança, com o número de entrenós totais e brocados em cada ponto. Olhando linha por linha, dá para perceber que os valores oscilam, mas **só olhar não é uma forma eficaz de entender dados**. Para saber o que os dados estão realmente dizendo, precisamos calcular algumas estatísticas descritivas (é o que este material faz) e desenhar alguns gráficos (assunto do próximo módulo).


![Pasted image 20260806143412.png](/img/user/Pasted%20image%2020260806143412.png)

Depois de calcular a intensidade de infestação (I.I.) de cada ponto do talhão A, os 10 valores são estes:

|Ponto|1|2|3|4|5|6|7|8|9|10|
|---|---|---|---|---|---|---|---|---|---|---|
|I.I. (%)|5,09|5,29|4,50|5,53|6,31|4,80|5,29|6,11|5,69|5,38|

É esse conjunto que vamos usar como exemplo ao longo de todo o material.

---

## 1. Medidas de tendência central

Desenhar gráficos é uma forma excelente de transmitir o "espírito" do que os dados dizem, mas costuma ser útil também condensar tudo em algumas estatísticas "resumo". Na maioria das situações, a primeira coisa que você vai querer calcular é uma **medida de tendência central**: algo que indique onde fica o "meio" ou o valor "típico" dos seus dados. As três medidas mais usadas são a média, a mediana e a moda.

### 1.1 A média

A média de um conjunto de observações é a média aritmética de sempre: soma tudo, divide pelo número de valores. Peguemos os 5 primeiros pontos do talhão A — 5,09%, 5,29%, 4,50%, 5,53% e 6,31% — de I.I.:

$$\bar{X} = \frac{5,09 + 5,29 + 4,50 + 5,53 + 6,31}{5} = \frac{26,72}{5} = 5,34\%$$

A notação padrão: usamos $N$ para o número de observações sendo promediadas (aqui, $N=5$), e $X_i$ para a i-ésima observação — $X_1$ é o primeiro ponto, $X_2$ o segundo, e assim por diante.

### 1.2 Calculando a média no jamovi

Fazer essa conta na mão fica tedioso rapidamente quando o número de observações cresce — e é exatamente para isso que existe o jamovi. Passo a passo:

1. Clique em **Exploração** → **Descritivas**.
2. Selecione a variável de interesse (por exemplo, a coluna de I.I. calculada) e clique na seta para movê-la para a caixa **Variables**.
3. Uma tabela aparece automaticamente no painel de resultados, à direita, já trazendo a média.

![Pasted image 20260806144121.png](/img/user/Pasted%20image%2020260806144121.png)
Se você fizer isso com os 10 pontos do talhão A (não só os 5 primeiros), o jamovi mostra:

|I.I. (talhão A)|
|---|---|
|N|10|
|Ausentes|0|
|Média|5,40|
|Mediana|5,34|
|Desvio-padrão|0,55|

A média das 10 observações é **5,40%** — repare que é diferente da média dos 5 primeiros pontos (5,34%): cada observação nova que entra desloca a média.

### 1.3 A mediana

A segunda medida de tendência central mais usada é a **mediana**, e ela é ainda mais fácil de descrever que a média: é o valor do meio. Pegando de novo os 5 primeiros pontos do talhão A e ordenando-os:

$$4{,}50,\ 5{,}09,\ \mathbf{5{,}29},\ 5{,}53,\ 6{,}31$$

O valor do meio é **5,29%**. Fácil. Mas o que fazer se quisermos incluir o sexto ponto (4,80%) em vez de parar no quinto? A lista ordenada passa a ser:

$$4{,}50,\ 4{,}80,\ 5{,}09,\ 5{,}29,\ 5{,}53,\ 6{,}31$$

Agora há dois valores no meio, 5,09 e 5,29. A mediana é definida como a média entre eles: $(5{,}09+5{,}29)/2 = 5{,}19\%$.

Como no caso da média, ninguém calcula a mediana ordenando os dados à mão quando o conjunto é grande — o jamovi faz isso por você. Com as 10 observações do talhão A, o valor que aparece na tabela de Descritivas é **5,34%**.

### 1.4 Média ou mediana? Qual a diferença?

Saber calcular média e mediana é só metade da história. Também é preciso entender o que cada uma está dizendo sobre os dados — e o que isso implica na hora de escolher qual usar.

- A **média** é uma espécie de "centro de gravidade" do conjunto de dados: se o histograma fosse um objeto sólido, o ponto de equilíbrio (como numa gangorra) seria a média.
- A **mediana** é a "observação do meio": metade dos valores fica abaixo dela, metade fica acima.

Como regra geral:

- Para dados **nominais** (categorias sem ordem, como variedade de cana), nem média nem mediana fazem sentido, use a **moda**.
- Para dados **ordinais** (uma escala de posições, como uma nota de severidade), a mediana costuma ser mais apropriada, porque usa só a informação de ordem, não os valores exatos.
- Para dados de **intervalo ou razão** (como a I.I., que é um percentual contínuo), qualquer uma das duas serve. A média usa toda a informação disponível, o que é uma vantagem quando você tem poucos dados, mas é **muito sensível a valores extremos**.

É essa última parte que vale a pena destacar. Quando o histograma é assimétrico, média e mediana se afastam sistematicamente uma da outra, a mediana fica mais perto do "corpo" da distribuição, enquanto a média é puxada na direção da cauda.

Um exemplo concreto, direto da própria disciplina de auditoria de dados: imagine que os prejuízos estimados de cinco talhões (em milhares de reais) sejam 8, 9, 10, 11 e 12 — a média e a mediana aqui são as duas 10. Agora imagine que um sexto talhão entra na conta, mas com um valor digitado errado por um erro de planilha: 950 (em vez de, digamos, 9,5). A média salta para cerca de 167, um número que não descreve prejuízo nenhum, real ou típico, dos seis talhões. A mediana, em contraste, sobe apenas para 10,5. Se o seu objetivo é descrever o prejuízo "típico" de um talhão, a mediana sobrevive ao erro; a média, não. **Essa é, no fundo, a mesma lição da auditoria de dados do Estudo de Caso 1**: um único valor absurdo pode contaminar silenciosamente uma média, sem gerar erro nenhum no software.

### 1.5 A moda

A moda de uma amostra é simples: é o valor que ocorre com mais frequência. Ela é especialmente útil para dados **nominais**, em que média e mediana não fazem sentido.

Um exemplo com dados nominais: a coluna `variedade` da planilha «Dados» registra três variedades de cana usadas nos seis talhões. Marcando a caixa **Frequency tables** na tela de Descritivas do jamovi, você obtém uma tabela de frequências:

|Variedade|Contagem|% do total|
|---|---|---|
|RB92579|30|50%|
|RB867515|20|33%|
|SP79-1011|10|17%|

A moda aqui é **RB92579**, presente em metade dos pontos amostrais. Note que, para essa variável, o jamovi nem calcula média, mediana, mínimo ou máximo — porque `variedade` é uma variável nominal, e esses valores não têm sentido algum ali.

A moda também é útil para variáveis discretas de contagem, mesmo quando a média faz sentido. Olhando `lagartas_vivas` em todos os pontos amostrais válidos (59 pontos, com uma célula ausente já excluída):

|Lagartas por ponto|0|1|2|3|4|5|6|7|8|9|
|---|---|---|---|---|---|---|---|---|---|---|
|Frequência|13|16|13|4|4|4|1|2|1|1|

A moda é **1 lagarta por ponto** (16 ocorrências). Se alguém lhe oferecesse uma aposta em que só ganha dinheiro acertando exatamente o número de lagartas de um ponto sorteado ao acaso, seria nesse valor que valeria a pena apostar — nem a média, nem a mediana ajudariam nessa aposta específica.

---

## 2. Medidas de variabilidade

Tendência central não é o único tipo de resumo que interessa. A segunda coisa que quase sempre queremos saber é o quanto os dados estão **espalhados**. Duas parcelas com a mesma média de I.I. podem contar histórias muito diferentes se uma tem os pontos bem próximos da média e a outra tem pontos indo de quase zero a valores bem altos — e é exatamente esse tipo de diferença que o Estudo de Caso 1 pede para você investigar entre os seis talhões.

### 2.1 Amplitude

A **amplitude** (_range_) é a mais simples: o maior valor menos o menor. Nos 10 pontos do talhão A, o máximo é 6,31% e o mínimo é 4,50%, então a amplitude é **1,81 pontos percentuais**.

É também a pior das medidas de variabilidade, porque não é robusta a valores extremos. Considere um conjunto de 10 prejuízos (em R$ mil) com um erro de digitação: **−100**, 2, 3, 4, 5, 6, 7, 8, 9, 10. A amplitude desse conjunto é 110 — mas, se o valor errado fosse removido, cairia para apenas 8. Um único erro de planilha, do tipo que a auditoria do Caso 1 pede para você caçar, é capaz de multiplicar a amplitude por mais de dez vezes.

### 2.2 Amplitude interquartil (IQR)

A **amplitude interquartil** (_interquartile range_, IQR) é parecida com a amplitude, mas em vez da diferença entre o maior e o menor valor, usa a diferença entre o 25º e o 75º percentil. O 25º percentil é o menor valor $x$ tal que 25% dos dados são menores que $x$; a mediana, aliás, nada mais é do que o 50º percentil.

No jamovi, marque a caixa **Percentis**, na seção **Statistics** da tela de Descritivas, para obter o 25º, 50º e 75º percentil de uma vez. Para os 10 pontos do talhão A:

|Valor (%)|
|---|---|
|25º percentil (Q1)|5,14|
|50º percentil (mediana)|5,34|
|75º percentil (Q3)|5,65|

![Pasted image 20260806151858.png](/img/user/Pasted%20image%2020260806151858.png)

A amplitude interquartil é $5{,}65 - 5{,}14 = 0{,}51$ pontos percentuais. A forma mais simples de interpretar isso: um quarto dos pontos fica abaixo de 5,14%, um quarto fica acima de 5,65%, e a IQR é a faixa coberta pela "metade do meio" dos dados.

### 2.3 Desvio médio absoluto

As duas medidas anteriores olham para percentis. Uma abordagem diferente é escolher um ponto de referência significativo (em geral a média ou a mediana) e reportar o desvio "típico" em relação a esse ponto.

Vamos fazer isso devagar, com os 5 primeiros pontos do talhão A (média $\bar{X}=5{,}34$):

|Ponto|$X_i$|Desvio ($X_i - \bar{X}$)|Desvio absoluto|
|---|---|---|---|
|1|5,09|−0,25|0,25|
|2|5,29|−0,06|0,06|
|3|4,50|−0,84|0,84|
|4|5,53|0,18|0,18|
|5|6,31|0,97|0,97|

O desvio médio absoluto é a média dessa última coluna: $(0{,}25+0{,}06+0{,}84+0{,}18+0{,}97)/5 = 0{,}46$.

### 2.4 Variância

Do ponto de vista puramente matemático, há boas razões para preferir desvios **ao quadrado** em vez de desvios absolutos. Fazendo isso obtemos a **variância**, normalmente escrita $s^2$.

Usando os mesmos 5 pontos:

|Ponto|$X_i$|Desvio|Desvio²|
|---|---|---|---|
|1|5,09|−0,25|0,06|
|2|5,29|−0,06|0,00|
|3|4,50|−0,84|0,71|
|4|5,53|0,18|0,03|
|5|6,31|0,97|0,93|

Se você somar essa última coluna e dividir por 5 (o número de observações), chega a uma variância de 0,35. Mas se você digitar esses mesmos 5 valores no jamovi e marcar a caixa **Variance**, o número que aparece é **0,44** — diferente do que você calculou à mão.

**Isso não é bug.** O jamovi está calculando algo ligeiramente diferente: em vez de dividir pela soma dos desvios² por $N$, ele divide por $N-1$. Com $N=5$, a diferença entre dividir por 5 e por 4 é grande o bastante para mudar o resultado visivelmente. A razão para isso tem a ver com uma distinção entre "descrever a amostra que você tem" e "estimar algo sobre a população da qual a amostra veio" — quando você mede 10 pontos de um talhão, quase nunca está interessado só nesses 10 pontos: você quer usar essa amostra para dizer algo sobre o talhão inteiro, com centenas de milhares de colmos. É essa segunda finalidade que a divisão por $N-1$ serve melhor, e é por isso que o jamovi (como qualquer software estatístico) usa essa convenção por padrão.

Com todos os 10 pontos do talhão A, a variância que o jamovi reporta é **0,30**.

Vale registrar o problema mais sério da variância: ela é praticamente **impossível de interpretar** para um ser humano. Como todos os valores foram elevados ao quadrado, a unidade da variância também fica "ao quadrado", "pontos percentuais ao quadrado". Ninguém, em nenhuma reunião de diretoria, jamais vai dizer que um talhão teve uma infestação "0,30 pontos percentuais quadrados acima da média". É exatamente por isso que existe a próxima medida.

### 2.5 Desvio-padrão

Se você gosta da ideia de usar a variância por causa das suas propriedades matemáticas, mas quer um número expresso na mesma unidade dos dados originais (pontos percentuais, não pontos percentuais ao quadrado), a solução é simples: tire a raiz quadrada da variância. É o que chamamos de **desvio-padrão**, tradicionalmente denotado $s$.

Assim como a variância, o jamovi calcula o desvio-padrão dividindo por $N-1$. Para os 10 pontos do talhão A, o desvio-padrão é $\sqrt{0{,}30} = 0{,}55$, e agora sim faz sentido dizer que a I.I. do talhão A "varia, em média, cerca de 0,55 pontos percentuais em torno da média de 5,40%".

Uma regra prática útil (assumindo uma distribuição aproximadamente simétrica e em forma de sino): cerca de 68% dos dados caem dentro de 1 desvio-padrão da média, cerca de 95% dentro de 2 desvios-padrão, e cerca de 99,7% dentro de 3 desvios-padrão. É uma aproximação, funciona bem quando o histograma é razoavelmente simétrico e falha quando não é.

> **É exatamente essa regra que sustenta o cálculo do intervalo de confiança** que você vai usar no Estudo de Caso 1: o IC de 95% para a I.I. de um talhão é, essencialmente, a média mais ou menos aproximadamente 2 erros-padrão, a mesma lógica da regra dos 68-95-99,7%, só que aplicada ao erro-padrão da média em vez de ao desvio-padrão bruto.

### 2.6 Qual medida usar?

Um resumo rápido das cinco medidas de variabilidade discutidas:

- **Amplitude.** Mostra o espalhamento total. Muito vulnerável a outliers; raramente usada sozinha.
- **Amplitude interquartil.** Mostra onde está a "metade do meio" dos dados. Robusta, combina bem com a mediana. Muito usada.
- **Desvio médio absoluto.** Diz o quão longe, "em média", as observações estão da média. Fácil de interpretar, mas pouco usada na prática estatística.
- **Variância.** Elegante matematicamente, mas inútil para comunicar com um ser humano — as unidades ficam ao quadrado. Está "por baixo do capô" de praticamente todas as ferramentas estatísticas, mas raramente é reportada diretamente.
- **Desvio-padrão.** Raiz quadrada da variância. Expressa na mesma unidade dos dados, então é interpretável. É a medida de variabilidade mais usada por padrão, sempre que a média é a medida de tendência central escolhida.

Em resumo: **IQR e desvio-padrão** são, de longe, as duas medidas mais comuns na prática.

---

## 3. Assimetria e curtose

Duas estatísticas descritivas adicionais aparecem vez ou outra: a **assimetria** (_skewness_) e a **curtose** (_kurtosis_). Nenhuma das duas é tão frequente quanto as medidas de tendência central e variabilidade, mas a assimetria é importante o bastante para valer a pena conhecer.

**Assimetria** mede o quanto uma distribuição é desbalanceada. Se os dados têm uma cauda mais longa à esquerda (valores muito baixos, mas poucos valores muito altos), dizemos que a distribuição tem **assimetria negativa**. Se a cauda longa está à direita, é **assimetria positiva**. Uma distribuição simétrica tem assimetria igual a zero.

No jamovi, marque a caixa **Skewness**, na seção Statistics de Descritivas. Para os 10 pontos de I.I. do talhão A, o valor é **0,12** — muito próximo de zero, indicando uma distribuição praticamente simétrica, sem cauda longa de nenhum dos dois lados.

**Curtose** mede o quão finas ou gordas são as caudas de uma distribuição, em comparação com a curva normal (que, por convenção, tem curtose zero). Distribuições com caudas mais finas que a normal têm curtose negativa (chamadas _platicúrticas_); com caudas mais gordas, curtose positiva (_leptocúrticas_). Para o talhão A, o jamovi reporta curtose de **−0,64** — uma distribuição um pouco mais "achatada" que a normal, mas nada extremo.

Nenhuma dessas duas estatísticas tem, sozinha, grande peso na decisão do Caso 1 — mas ambas ajudam a confirmar (ou desconfiar) da suposição de normalidade que sustenta o cálculo do intervalo de confiança da seção 2.5.

---

## 4. Estatísticas descritivas por grupo

É muito comum precisar quebrar as estatísticas descritivas por alguma variável de agrupamento — no Caso 1, por talhão; aqui, para ilustrar sem antecipar as respostas do caso, vamos usar a variedade de cana.

No jamovi, isso é simples:

1. Vá a **Exploração** → **Descritivas**.
2. Mova a variável de interesse (I.I.) para a caixa **Variables**, como sempre.
3. Mova a variável de agrupamento (`variedade`) para a caixa **Split by**.
4. A tabela de resultados passa a mostrar uma coluna para cada categoria.

![Pasted image 20260806144452.png](/img/user/Pasted%20image%2020260806144452.png)

Fazendo isso com a I.I. dividida por variedade, obtemos:

|               | RB92579 | RB867515 | SP79-1011 |
| ------------- | ------- | -------- | --------- |
| N             | 30      | 19       | 9         |
| Média (%)     | 3,23    | 2,15     | 2,20      |
| Mediana (%)   | 3,13    | 1,83     | 2,17      |
| Desvio-padrão | 2,07    | 1,30     | 0,55      |

É exatamente essa técnica — Split by — que você vai usar no Caso 1 para comparar os seis talhões entre si. Repare que **N não bate com o total de 60 pontos**: isso acontece porque um dos pontos foi excluído da conta por ter um valor de entrenós brocados impossível (mais brocados que o total de entrenós existentes) — a mesma inconsistência que a auditoria do Caso 1 pede para você localizar antes de calcular qualquer coisa.

> **Um alerta prático.** Se você tentar dividir por duas variáveis de agrupamento ao mesmo tempo (por exemplo, talhão _e_ variedade), pode acabar com combinações que têm poucos ou nenhum ponto amostral, e o jamovi vai reportar algo como `NaN` ou `Inf` nessas células. Isso não é erro do software: é um aviso de que faltam dados suficientes para aquela combinação específica.

---

## 5. Escores padronizados (z-scores)

Suponha que a assistência técnica regional mantenha, hipoteticamente, um histórico de muitas safras anteriores em toda a Zona da Mata: a I.I. média entre centenas de talhões monitorados ao longo dos anos é de 3,0%, com desvio-padrão de 1,4 pontos percentuais _(valores hipotéticos, só para este exemplo — não confunda com os parâmetros oficiais do Caso 1)_.

O talhão A, com sua I.I. de 5,40%, está acima dessa média — mas quanto acima, exatamente? Dizer "5,40 dividido por 3,0" não ajuda muito, porque isso depende inteiramente da escala arbitrária da I.I.. Uma forma melhor de responder é comparar o talhão A com a distribuição inteira dos talhões da região, convertendo seu valor num **escore padronizado**, também chamado de **z-score**: o número de desvios-padrão que aquele valor está acima (ou abaixo) da média.

$$z = \frac{\text{valor observado} - \text{média}}{\text{desvio-padrão}}$$

Para o talhão A:

$$z = \frac{5{,}40 - 3{,}0}{1{,}4} = 1{,}71$$

Um z de 1,71 significa que o talhão A está a 1,71 desvios-padrão acima da média regional, usando a regra prática da seção 2.5 (cerca de 95% dos dados dentro de 2 desvios-padrão), isso o coloca entre os talhões mais infestados da região, embora não seja um valor absurdamente extremo.

A grande vantagem dos escores padronizados é que eles podem ser comparados entre variáveis diferentes, mesmo quando os valores brutos não têm a mesma escala e não podem ser comparados diretamente — porque cada z-score é uma afirmação sobre a posição relativa de uma observação dentro da sua própria distribuição, não sobre o valor bruto em si.

---

## 6. Resumo

Este material cobriu:

- **Medidas de tendência central** — média, mediana e moda: onde os dados "estão".
- **Medidas de variabilidade** — amplitude, IQR, desvio médio absoluto, variância e desvio-padrão: o quanto os dados estão espalhados.
- **Assimetria e curtose** — o quanto uma distribuição é desbalanceada e o quão finas ou gordas são suas caudas.
- **Estatísticas descritivas por grupo** — como usar **Split by** no jamovi para comparar categorias, unidades ou talhões entre si.
- **Escores padronizados** — como comparar uma observação com a distribuição de onde ela vem, mesmo entre variáveis diferentes.

Calcular estatísticas descritivas é sempre uma das primeiras coisas que se faz ao analisar dados reais — e, como você vai constatar no Estudo de Caso 1, é também onde a maior parte dos erros de interpretação nasce: uma média mal calculada, um desvio-padrão ignorado, uma célula vazia que passou despercebida. Um curso tradicional de estatística costuma dedicar só uma ou duas aulas a esse tema, e passar o resto do tempo em estatística inferencial — o que faz sentido, porque é ali que mora a parte mais difícil. Mas isso esconde a importância prática, do dia a dia, de escolher bem as suas descritivas antes de qualquer coisa.