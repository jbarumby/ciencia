# 1. Título

**Dinâmica da soma dos algarismos dos quadrados e pares de primos gêmeos**

## 2. Resumo

Neste artigo estudo a dinâmica discreta da função
\[
 f:\mathbb N_{>0}\longrightarrow\mathbb N_{>0},\qquad f(n)=S(n^2),
\]
em que \(S(n)\) é a soma dos algarismos da expansão decimal de \(n\). Demonstro que toda órbita entra no conjunto finito \(\{1,\ldots,99\}\) e, por uma verificação finita explicitamente justificada, classifico todos os ciclos: \((1)\), \((9)\) e \((13,16)\). A congruência \(f(n)\equiv n^2\pmod 9\) determina qual desses ciclos é terminal. Em particular, para todo par de primos gêmeos \((p,p+2)\), com \(p>3\), as duas órbitas terminam no ciclo \((13,16)\), em fases opostas, se \(p\equiv2\) ou \(5\pmod9\), e terminam no ponto fixo \(1\) se \(p\equiv8\pmod9\). Saliento que o resultado é condicional apenas à existência de cada par considerado; ele não estabelece a infinitude dos primos gêmeos.

## 3. Palavras-chave

Soma dos algarismos; dinâmica discreta; iteração aritmética; congruências módulo \(9\); primos gêmeos.

## 4. Introdução

Investigo a iteração da soma dos algarismos do quadrado, isto é, a sucessão definida por \(x_0=n\) e \(x_{k+1}=f(x_k)\). Meu objetivo é separar duas questões: a classificação global das órbitas de \(f\) e a especialização dessa classificação aos pares de primos gêmeos. A primeira será resolvida por uma estimativa de descida, seguida de uma inspeção finita completa; a segunda decorrerá de restrições elementares, mas decisivas, sobre os resíduos módulo \(3\) e módulo \(9\).

Não emprego exemplos numéricos como substitutos de demonstrações. A única etapa computacional ou enumerativa necessária será formulada como uma verificação finita de valores explicitamente delimitados. A razão matemática de sua suficiência é a descida estrita demonstrada adiante.

## 5. Definições e notação

Para \(n\in\mathbb N_{>0}\), escrevo unicamente
\[
 n=\sum_{j=0}^{d-1}a_j10^j,\qquad a_j\in\{0,1,\ldots,9\},\quad a_{d-1}\ne0,
\]
e defino \(S(n)=\sum_{j=0}^{d-1}a_j\). Defino \(f(n)=S(n^2)\) e \(f^0(n)=n\), \(f^{k+1}(n)=f(f^k(n))\). A órbita positiva de \(n\) é \(\mathcal O(n)=\{f^k(n):k\ge0\}\).

Chamo \(C=(c_0,\ldots,c_{\ell-1})\) de ciclo de período \(\ell\) quando os \(c_i\) são distintos e \(f(c_i)=c_{i+1}\), com índices tomados módulo \(\ell\). Direi que uma órbita termina em \(C\) se existe \(N\ge0\) tal que \(f^N(n)\in C\); então todos os iterados subsequentes pertencem a \(C\). Esta é uma definição de periodicidade eventual, não uma afirmação sobre convergência no sentido real.

## 6. Propriedade modular da soma dos algarismos

**Proposição 6.1.** Para todo \(m\in\mathbb N_{>0}\), vale \(S(m)\equiv m\pmod9\). Consequentemente,
\[
 f(n)\equiv n^2\pmod9.
\]

**Demonstração.** Como \(10\equiv1\pmod9\), da expansão decimal de \(m\) resulta
\[
 m=\sum_{j=0}^{d-1}a_j10^j\equiv\sum_{j=0}^{d-1}a_j=S(m)\pmod9.
\]
Aplicando a identidade a \(m=n^2\), obtenho \(f(n)=S(n^2)\equiv n^2\pmod9\). \(\square\)

Introduzo agora a aplicação residual \(q:\mathbb Z/9\mathbb Z\to\mathbb Z/9\mathbb Z\), \(q(\bar r)=\overline{r^2}\). A Proposição 6.1 implica, por indução em \(k\),
\[
 \overline{f^k(n)}=q^k(\bar n). \tag{3.1}
\]
A igualdade (3.1) é o vínculo rigoroso entre a classe residual inicial e as classes residuais de toda a órbita; a identificação do ciclo terminal exigirá adicionalmente a classificação dos ciclos inteiros.

## 7. Lema da descida

**Lema 7.1.** Se \(n\ge100\), então \(f(n)<n\).

**Demonstração.** Seja \(d\ge3\) o número de algarismos de \(n\). Então \(n\ge10^{d-1}\), e \(n^2<10^{2d}\); logo \(n^2\) possui no máximo \(2d\) algarismos. Portanto
\[
 f(n)=S(n^2)\le9(2d)=18d.
\]
Para \(d=3\), tem-se \(18d=54<100=10^{d-1}\). Se \(18d<10^{d-1}\) para algum \(d\ge3\), então
\[
18(d+1)=18d+18<10^{d-1}+18<10^d,
\]
pois \(18<9\cdot10^{d-1}\). Por indução, \(18d<10^{d-1}\le n\) para todo \(d\ge3\). Assim \(f(n)<n\). \(\square\)

## 8. Redução a um conjunto finito

**Proposição 8.1.** Toda órbita de \(f\) encontra o conjunto \(A=\{1,2,\ldots,99\}\).

**Demonstração.** Se \(n\in A\), nada há a provar. Se \(n\ge100\), o Lema 7.1 dá \(f(n)<n\). Enquanto os iterados permanecerem maiores ou iguais a \(100\), eles formam uma sequência estritamente decrescente de inteiros positivos. Tal sequência não pode ser infinita; portanto algum iterado é menor que \(100\), isto é, pertence a \(A\). \(\square\)

Além disso, \(f(A)\subseteq A\): para \(1\le n\le99\), vale \(n^2\le9801\), que tem no máximo quatro algarismos, e assim \(f(n)\le36<100\). Logo, depois de entrar em \(A\), a órbita nunca o deixa. Em um conjunto finito, uma sequência infinita deve repetir um valor; determinismo de \(f\) implica que, a partir da primeira repetição, a órbita é periódica. Assim, a classificação dos ciclos em \(A\) classifica todos os ciclos de \(f\).

## 9. Classificação dos ciclos

**Proposição 9.1.** Os únicos ciclos de \(f\) em \(\mathbb N_{>0}\) são
\[
 (1),\qquad(9),\qquad(13,16).
\]

**Demonstração.** Pela Proposição 8.1 e pela invariância de \(A\), basta verificar \(f(n)\) para \(n\in A\). A verificação finita abaixo exibe, sem omitir casos, o cálculo direto de \(S(n^2)\) para cada \(n\in A\):
\[
\begin{array}{c|l}
 n&f(n)\\ \hline
1\text{--}9&1,4,9,7,7,9,13,10,9\\
10\text{--}19&1,4,9,16,16,9,13,19,9,10\\
20\text{--}29&4,9,16,16,18,13,19,18,19,13\\
30\text{--}39&9,16,7,18,13,10,18,19,13,9\\
40\text{--}49&7,16,18,22,19,9,10,13,9,7\\
50\text{--}59&7,9,13,19,18,10,13,18,16,16\\
60\text{--}69&9,13,19,27,19,13,18,25,16,18\\
70\text{--}79&13,10,18,19,22,18,25,25,18,13\\
80\text{--}89&10,18,19,31,18,16,25,27,22,19\\
90\text{--}99&9,19,22,27,25,16,18,22,19,18
\end{array}
\]
Logo \(f(A)=\{1,4,7,9,10,13,16,18,19,22,25,27,31\}=:B\). Um segundo cálculo direto, agora apenas nos treze elementos de \(B\), fornece
\[
\begin{array}{c|rrrrrrrrrrrrr}
x&1&4&7&9&10&13&16&18&19&22&25&27&31\\ \hline
f(x)&1&7&13&9&1&16&13&9&10&16&13&18&16.
\end{array}
\]
Esta tabela é uma verificação aritmética finita, não uma inferência empírica: cada uma de suas entradas é, por definição, a soma dos algarismos do quadrado do inteiro indicado. Ela é suficiente porque todo ciclo está contido em \(A\), todo elemento de \(A\) é enviado para \(B\), e a tabela contém a imagem de cada elemento de \(B\). Pela tabela, os únicos componentes cíclicos são \(1\mapsto1\), \(9\mapsto9\) e \(13\mapsto16\mapsto13\). \(\square\)

## 10. Análise das classes módulo 9

**Teorema 10.1.** Para todo \(n\in\mathbb N_{>0}\), o ciclo terminal é determinado por \(n\pmod9\) da seguinte forma:
\[
\begin{array}{c|c}
n\pmod9&\text{ciclo terminal}\\ \hline
0,3,6&(9)\\
1,8&(1)\\
2,4,5,7&(13,16).
\end{array}
\]

**Demonstração.** A dinâmica de \(q(\bar r)=\overline{r^2}\) é
\[
0\mapsto0,\ 1\mapsto1,\ 2\mapsto4,\ 3\mapsto0,\ 4\mapsto7,\ 5\mapsto7,\ 6\mapsto0,\ 7\mapsto4,\ 8\mapsto1.
\]
Assim, as classes \(0,3,6\) chegam a \(\bar0\); as classes \(1,8\) chegam a \(\bar1\); e as classes \(2,4,5,7\) chegam ao 2-ciclo residual \(\bar4\leftrightarrow\bar7\). Pela Proposição 9.1, os únicos ciclos inteiros possíveis são \((1)\), \((9)\) e \((13,16)\), cujas respectivas classes residuais são \(\bar1\), \(\bar0\) e \(\bar4\leftrightarrow\bar7\). A identidade (3.1) exclui qualquer ciclo cujo padrão residual seja incompatível com a órbita residual de \(n\). Como toda órbita tem um ciclo terminal, a correspondência indicada é forçada. \(\square\)

## 11. Estudo dos primos gêmeos

Se \((p,p+2)\) é um par de primos gêmeos com \(p>3\), então \(p\not\equiv0\pmod3\). Também \(p+2\not\equiv0\pmod3\). Como os únicos resíduos não nulos módulo \(3\) são \(1\) e \(2\), a congruência \(p\equiv1\pmod3\) implicaria \(p+2\equiv0\pmod3\), impossível porque \(p+2>3\) seria primo e múltiplo de \(3\). Portanto
\[
 p\equiv2\pmod3. \tag{8.1}
\]
Os resíduos módulo \(9\) compatíveis com (8.1) são precisamente \(2,5,8\). Em consequência,
\[
(p,p+2)\equiv(2,4),\ (5,7),\ \text{ou }(8,1)\pmod9. \tag{8.2}
\]
Não há aqui qualquer afirmação de que cada uma dessas classes contenha infinitos pares de primos gêmeos; (8.2) é apenas uma condição necessária para cada par existente.

## 12. Teorema dos Ciclos Gêmeos

**Teorema 12.1 (Ciclos Gêmeos).** Seja \((p,p+2)\) um par de primos gêmeos com \(p>3\). Então:

1. se \(p\equiv2\) ou \(5\pmod9\), as órbitas de \(p\) e de \(p+2\) terminam no ciclo \((13,16)\); além disso, existem \(N\) e, para todo \(k\ge N\), os valores \(f^k(p)\) e \(f^k(p+2)\) são os dois elementos distintos desse ciclo;
2. se \(p\equiv8\pmod9\), ambas as órbitas terminam no ponto fixo \(1\).

Em particular, nenhuma dessas duas órbitas termina em \(9\).

## 13. Demonstração rigorosa

**Demonstração do Teorema 12.1.** Pela análise anterior, \(p\) satisfaz (8.1), e portanto ocorre exatamente um dos três casos de (8.2).

Se \(p\equiv2\pmod9\), então \(p+2\equiv4\pmod9\). Pelo Teorema 10.1, ambas as órbitas terminam em \((13,16)\). Mais precisamente, para \(k\ge1\), a dinâmica residual dá
\[
 f^k(p)\equiv\begin{cases}4,&k\text{ ímpar},\\7,&k\text{ par},\end{cases}\qquad
 f^k(p+2)\equiv\begin{cases}7,&k\text{ ímpar},\\4,&k\text{ par}.
\]
Após o máximo dos tempos de entrada das duas órbitas no ciclo, cada iterado pertence a \(\{13,16\}\). Como \(13\equiv4\) e \(16\equiv7\pmod9\), as congruências acima impõem que eles sejam distintos e estejam em fases opostas.

Se \(p\equiv5\pmod9\), então \(p+2\equiv7\pmod9\). Novamente o Teorema 10.1 fornece o ciclo \((13,16)\) para ambas as órbitas. Para \(k\ge1\), os resíduos são respectivamente \(7,4,7,4,\ldots\) e \(4,7,4,7,\ldots\); o mesmo argumento usando \(13\equiv4\) e \(16\equiv7\pmod9\) prova a oposição de fases a partir de algum instante comum.

Por fim, se \(p\equiv8\pmod9\), então \(p+2\equiv1\pmod9\). O Teorema 10.1 mostra que ambas as órbitas terminam em \((1)\). Os três casos esgotam as possibilidades por (8.2). Nenhum deles pertence à primeira linha da tabela do Teorema 10.1; logo o ciclo \((9)\) é impossível para as duas órbitas consideradas. \(\square\)

## 14. Discussão

O mecanismo do resultado é inteiramente aritmético. A soma dos algarismos preserva o resíduo módulo \(9\), e a elevação ao quadrado induz a pequena dinâmica \(r\mapsto r^2\) nesse módulo. Todavia, a congruência, isoladamente, não determina valores inteiros: ela determina apenas uma trajetória de classes. A passagem legítima de trajetórias residuais a ciclos terminais depende crucialmente de dois fatos já provados: toda órbita entra em \(A\), e os únicos ciclos inteiros são os da Proposição 9.1. É essa combinação que justifica a tabela do Teorema 10.1.

O caso \(p>3\) é essencial para a dedução \(p\equiv2\pmod3\). O par excepcional \((3,5)\) não satisfaz essa conclusão para a primeira coordenada e não faz parte do Teorema 12.1. A conclusão para pares gêmeos é, portanto, uma classificação dinâmica condicional e exata, não uma estimativa de frequência de tais pares.

## 15. Limitações do resultado

Meu teorema não prova a Conjectura dos Primos Gêmeos, nem fornece uma contagem assintótica de pares gêmeos em qualquer classe módulo \(9\). Também não afirma que cada uma das alternativas \(p\equiv2,5,8\pmod9\) ocorra infinitamente muitas vezes. A demonstração classifica o destino sob \(f\) de todo par que já seja primo gêmeo e satisfaça \(p>3\).

A classificação global dos ciclos depende da base decimal: a identidade modular usada é específica da congruência \(10\equiv1\pmod9\). Uma mudança de base altera tanto o análogo do módulo \(9\) quanto a função soma dos algarismos, e requer análise própria.

## 16. Conclusão

Demonstrei que a função \(f(n)=S(n^2)\) possui exatamente dois pontos fixos, \(1\) e \(9\), e um único ciclo não trivial, \((13,16)\). Demonstrei ainda que a classe de \(n\) módulo \(9\) determina rigorosamente qual desses ciclos é terminal. Para pares de primos gêmeos \((p,p+2)\), com \(p>3\), a condição de primalidade elimina as classes que conduziriam a \(9\): resta o ponto fixo \(1\) quando \(p\equiv8\pmod9\), ou o ciclo \((13,16)\), com fases opostas, quando \(p\equiv2\) ou \(5\pmod9\). Assim, a relação entre primos gêmeos e ciclos nesta dinâmica é uma consequência demonstrada de congruências e da classificação finita dos ciclos, sem qualquer uso indevido de conjecturas não resolvidas.

## 17. Referências

1. G. H. Hardy e E. M. Wright, *An Introduction to the Theory of Numbers*, 6. ed., Oxford University Press, 2008.
2. T. M. Apostol, *Introduction to Analytic Number Theory*, Springer, 1976.
3. Material matemático do projeto *Ciclos Gêmeos*, consultado como fonte temática; as demonstrações e as limitações explicitadas neste artigo são apresentadas de forma autônoma.
