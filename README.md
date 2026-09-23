# timothy
AI-powered audio recognition and identification and fingerprinting

# timothy

Identificação de músicas tocadas ao vivo.

## O problema

Aplicativos de reconhecimento musical como o Shazam identificam gravações, não músicas.
Eles constroem uma impressão digital a partir da geometria dos picos de energia no
espectrograma e procuram essa mesma geometria em um banco de gravações conhecidas.
O método é robusto a ruído de ambiente e por isso funciona bem em um bar com o rádio
ligado.

Ele falha quando a música está sendo tocada ao vivo. Uma execução ao vivo tem outro
andamento, muitas vezes outro tom, outro arranjo e improviso. A geometria dos picos
muda por inteiro, e aquela execução específica não está no banco. O aplicativo não
reconhece, não porque a música seja desconhecida, mas porque a pergunta que ele sabe
responder é outra.

## A proposta

Tratar o problema como identificação de versão, e não como busca por igualdade.
A pergunta deixa de ser "qual gravação é esta" e passa a ser "de qual obra esta
execução é uma versão".

Direção técnica em avaliação:

- Representação por conteúdo harmônico, com cromagrama ou HPCP, que descreve como as
  classes de altura se distribuem ao longo do tempo e é insensível ao timbre dos
  instrumentos.
- Invariância a tom por transposição da representação antes da comparação.
- Tolerância a variação de andamento por alinhamento de sequências, com DTW ou
  medidas de recorrência cruzada.
- Busca em escala por aproximação de vizinhos mais próximos sobre representações
  vetoriais aprendidas.

## Estado do projeto

Em concepção. Este repositório documenta o problema e a direção técnica antes da
implementação. Não há código funcional publicado.

Próximo passo: extrair cromagramas de um conjunto pequeno de obras com múltiplas
execuções e medir se o alinhamento por DTW separa versões da mesma obra de obras
diferentes.

## Contexto

Projeto de estudo, conduzido em paralelo ao CS50 de Harvard.

## Licença

MIT
