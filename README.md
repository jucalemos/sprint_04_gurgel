# Gurgel — Sprint 4
## Solução final integrada | Challenge GoodWe

**Equipe:** Gurgel

### Integrantes
- Júlia Lemos Souza — RM 569089
- Erick Yu Xiang Li — RM 569305
- Erick Banhos de Castro — RM 572131
- Victor Henrique Nogueira Bezerra Azevedo de Souza — RM 570021
- Carlos Henrique — RM 573334
- Gustavo Araújo Ramos da Silva — RM 574156

**Vídeo da Sprint 4:** https://youtu.be/suJQKQ-y5pI

## Sobre o projeto

O Gurgel é uma proposta de gerenciamento inteligente da recarga de veículos elétricos. O projeto explora o limite de potência, a estimativa de uso de energia solar, a parcela de energia atribuída à rede e a visualização de dados de sessões de recarga.

## O que foi desenvolvido

- **Arduino/Tinkercad:** circuito com dois potenciômetros para simular potência solar e demanda, botão para controlar a sessão, LEDs de estado e mensagens no Serial Monitor.
- **Python:** regra de gerenciamento com limite de 10 kW e scripts para resumir e visualizar dados de sessões.
- **Dados:** arquivo CSV com oito sessões ilustrativas.
- **Interface:** capturas das telas do Gurgel e do GurAI estão reunidas em [Imagens/Telas](imagens/TELAS.md).

> **Importante:** os valores do circuito e do CSV são simulados/ilustrativos. Os arquivos deste repositório não demonstram integração em tempo real entre Arduino, Python e interface, nem conexão direta com equipamentos GoodWe ou realização de pagamentos reais.

## Tecnologias

- Arduino Uno R3 e simulação Tinkercad;
- C/C++ para Arduino;
- Python, pandas, NumPy, Matplotlib e Seaborn;
- CSV e GitHub.

## Executar os scripts Python

Abra um terminal dentro da pasta `python/` e instale as dependências:

```bash
python -m pip install pandas numpy matplotlib seaborn
```

Depois, execute os scripts a partir dessa mesma pasta:

```bash
python gerenciamento.py
python simulacao.py
python dashboard.py
```

## Documentação

- [Arquitetura e componentes](ARQUITETURA.md)
- [Diagramas do sistema](DIAGRAMAS.md)
- [Resultados, metodologia e limitações](RESULTADOS.md)
- [Referências técnicas](REFERENCIAS.md)
- [Dados da entrega](ENTREGA.txt)
- [Capturas de tela](imagens/TELAS.md)

## Repositório

https://github.com/jucalemos/sprint_04_gurgel
