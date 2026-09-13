# Torre de Controle — rotas de equipes de campo

Painel de acompanhamento de equipes de rua em um único arquivo HTML: planejamento
do dia, divisão territorial, rotas, alertas e um mapa de rotas no nível da rua.
Não precisa de servidor, build nem dependência — abre direto no navegador.

> **Dados de demonstração.** A geometria (bairros, quadrantes, ruas, pontos) é
> baseada em mapas públicos. Contagens, equipes, horários e posições GPS são
> fictícios ou simulados, e servem apenas para mostrar o funcionamento do painel.

## Como abrir

Baixe o repositório e dê dois cliques em `index.html`.

## O que tem

- **Dashboard** — mapa vetorial em canvas com camadas (equipes, rotas, trajeto
  realizado, quadrantes, bairros, ruas e pontos), KPIs e alertas em tempo real.
- **Programação** — ciclo do dia: proposta → confirmado → liberado, com versões.
- **Divisão das equipes, Rotas, Equipes, Quadrantes, Ruas, Pontos** — o plano
  em tabelas, com edição de itinerário e folha de rua para impressão (A4).
- **Mapa de Rotas** — uma rota por vez, em pele clara de mapa de rua:
  - paradas numeradas na ordem, com distância até a anterior e total acumulado;
  - cartão da parada com miniatura no nível da rua e coordenada;
  - atalhos que abrem o Google Maps numa nova guia (ver ponto, Street View,
    como chegar e a rota inteira, dividida em trechos de até 10 pontos).
- **Alertas** — fora da rota, fora do quadrante, GPS offline, equipe parada,
  atraso e proximidade entre equipes, medidos a partir da posição simulada.

## Como funciona

- Tudo em JavaScript puro, sem biblioteca: projeção equiretangular local,
  desenho em `<canvas>`, hit-test para tooltip e clique.
- A simulação de GPS é determinística por equipe e data — o mesmo dia sempre
  reproduz o mesmo cenário.
- Edições de itinerário ficam no `localStorage` do navegador.
