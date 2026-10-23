# Gurgel — Sprint 4
## Solução final integrada e inovadora | Challenge GoodWe

**Equipe:** Gurgel

### Integrantes
- Júlia Lemos Souza — RM 569089
- Erick Yu Xiang Li — RM 569305
- Erick Banhos de Castro — RM 572131
- Victor Henrique Nogueira Bezerra Azevedo de Souza — RM 570021
- Carlos Henrique — RM 573334
- Gustavo Araújo Ramos da Silva — RM 574156

**Vídeo da Sprint 4 (YouTube):** https://youtu.be/suJQKQ-y5pI

## 1. Sobre o projeto

O Gurgel é uma proposta de gerenciamento inteligente da recarga de veículos elétricos. O projeto reúne o conceito de monitoramento, gerenciamento de potência, estimativa de custos e consideração do uso de energia renovável, buscando tornar as informações de recarga mais claras para o usuário.

Esta documentação distingue o protótipo simulado, os dados ilustrativos e as possibilidades futuras. Essa distinção evita apresentar resultados simulados como medições reais.

## 2. O que o protótipo demonstra

- **Arduino/Tinkercad:** dois potenciômetros representam potência solar e demanda; um botão controla o estado da sessão; quatro LEDs indicam estados; o programa envia informações ao Serial Monitor.
- **Python:** regra de gerenciamento limita a potência liberada a 10 kW e estima a parcela solar e a parcela da rede.
- **Análise de dados:** scripts leem o CSV e calculam indicadores e gráficos de sessões.
- **Interface e GurAI:** as capturas de telas herdadas da Sprint 3 documentam a proposta de interface. Não se deve afirmar que a interface controla o hardware ou executa pagamentos reais sem evidência de implementação e teste.

## 3. Visão do circuito

O circuito acadêmico usa Arduino Uno R3, dois potenciômetros, botão, LEDs e resistores. Os potenciômetros simulam os valores de entrada: eles não são medidores de geração fotovoltaica nem de consumo de um carregador real.

![Protótipo Arduino usado como base](https://raw.githubusercontent.com/jucalemos/sprint_03_gurgel/main/imagens/prototipo.jpeg)

## 4. Gerenciamento de potência

O limite usado no código é de **10 kW**. Quando a demanda simulada supera esse valor, a potência liberada fica limitada. A parcela solar utilizada é estimada como o menor valor entre potência solar simulada e potência liberada; o restante é atribuído à rede.

Essa lógica é uma prova de conceito acadêmica e não substitui sistemas de proteção elétrica nem deve ser conectada diretamente a carregadores comerciais.

## 5. Resultados dos dados ilustrativos

O CSV de referência contém oito sessões ilustrativas.

| Indicador | Resultado do CSV |
|---|---:|
| Sessões | 8 |
| Energia total | 75,75 kWh |
| Energia solar simulada | 39,90 kWh |
| Energia da rede simulada | 35,85 kWh |
| Soma do custo informado nas sessões | R$ 88,86 |
| Potência média | 6,725 kW |
| Maior potência no conjunto | 9,0 kW |
| Menor potência no conjunto | 4,5 kW |

Os resultados são agregações de dados ilustrativos, não medições físicas, cobranças reais ou comprovação de economia de carbono. Consulte [RESULTADOS.md](RESULTADOS.md) para metodologia e limitações.

## 6. Relação com o desafio GoodWe

A proposta se relaciona conceitualmente ao gerenciamento de demanda, à consideração da energia solar e à visualização de consumo e custos. Os arquivos atuais não demonstram comunicação direta com inversores, baterias ou carregadores GoodWe. Portanto, a integração com equipamentos GoodWe deve ser apresentada como possibilidade futura, a menos que a equipe disponha de evidências adicionais de integração testada.

## 7. Sustentabilidade e impacto

A solução ilustra como acompanhar a demanda e considerar a disponibilidade de energia solar pode apoiar decisões energéticas mais conscientes. Ainda não foi comprovada uma redução percentual de emissões ou um ganho de eficiência medido. Esses efeitos devem ser descritos como benefícios potenciais, não como resultados experimentais.

## 8. Tecnologias

- Arduino Uno R3 e simulação Tinkercad;
- C/C++ para Arduino;
- Python;
- pandas, NumPy, Matplotlib e Seaborn;
- CSV;
- GitHub.

## 9. Executar os scripts Python

Abra um terminal na pasta `python/` e instale as dependências:

```bash
python -m pip install pandas numpy matplotlib seaborn
```

Execute os scripts a partir dessa pasta, pois eles leem `dados.csv` por caminho relativo:

```bash
python gerenciamento.py
python simulacao.py
python dashboard.py
```

## 10. Documentação, diagramas e imagens

- [Arquitetura e fluxo de dados](ARQUITETURA.md)
- [Resultados, metodologia e limitações](RESULTADOS.md)
- [Diagramas funcionais e capturas de telas](DIAGRAMAS.md)
- [Referências técnicas](REFERENCIAS.md)
- [Modelo do arquivo de entrega .txt](ENTREGA.txt)

### Capturas de tela da interface

Acesse também o [índice visual da pasta imagens/](imagens/README.md), com as capturas agrupadas em uma página.

As imagens a seguir são capturas já disponíveis no repositório da Sprint 3, reutilizadas como referência visual da plataforma:

- [Tela do GurAI](https://github.com/jucalemos/sprint_03_gurgel/blob/main/imagens/gurai.jpeg)
- [Conversa com GurAI](https://github.com/jucalemos/sprint_03_gurgel/blob/main/imagens/conversa_gurai.jpeg)
- [Mapa de carregadores](https://github.com/jucalemos/sprint_03_gurgel/blob/main/imagens/mapa.jpeg)
- [Monitoramento e mapa](https://github.com/jucalemos/sprint_03_gurgel/blob/main/imagens/monitoramento_mapa.jpeg)
- [Reserva de carregador](https://github.com/jucalemos/sprint_03_gurgel/blob/main/imagens/reserva_carregador.jpeg)
- [Tela de reservas](https://github.com/jucalemos/sprint_03_gurgel/blob/main/imagens/reservas.jpeg)

## 11. Limitações e próximos passos

1. As entradas de potência solar e demanda do circuito são simuladas.
2. O CSV contém dados ilustrativos.
3. Os arquivos não demonstram conexão em tempo real entre Arduino, Python e interface.
4. Não há evidência de integração direta com equipamento GoodWe, pagamento real ou controle de carregador comercial.
5. Não foi calculada uma redução comprovada de emissões.
6. A equipe deve conferir se o vídeo apresenta os mesmos comportamentos descritos na documentação.

## 12. Repositório

https://github.com/jucalemos/sprint_04_gurgel
