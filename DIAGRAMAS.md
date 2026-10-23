# Diagramas e telas — Gurgel Sprint 4

Este documento reúne o fluxo funcional documentado e imagens demonstrativas do projeto. As imagens de interface foram reutilizadas do repositório da Sprint 3 para preservar o material já produzido pela equipe.

## 1. Arquitetura conceitual do Gurgel

```mermaid
flowchart TD
    A[Demanda de recarga] --> D[Gerenciamento inteligente]
    B[Disponibilidade solar simulada] --> D
    C[Limite de potência: 10 kW] --> D
    D --> E[Potência liberada]
    E --> F[Estimativa de energia solar]
    E --> G[Estimativa de energia da rede]
    F --> H[Registro e análise de sessões]
    G --> H
    H --> I[Indicadores e gráficos]
    I --> J[Interface Gurgel / apoio ao usuário]
```

**Nota:** o diagrama é conceitual. Os arquivos atuais não demonstram integração automática entre o Arduino, os scripts Python e a interface. A energia solar é simulada no circuito com potenciômetro.

## 2. Fluxo do protótipo Arduino

```mermaid
flowchart TD
    A[Potenciômetro A0: solar simulada] --> C[Arduino Uno]
    B[Potenciômetro A1: demanda simulada] --> C
    D[Botão de sessão] --> C
    C --> E[Aplicar regra de limite de 10 kW]
    E --> F[Calcular potência liberada]
    F --> G[Estimar parcela solar e parcela da rede]
    G --> H[Serial Monitor]
    E --> I[LEDs de estado]
```

## 3. Fluxo de análise de dados

```mermaid
flowchart LR
    A[dados.csv: sessões ilustrativas] --> B[pandas]
    B --> C[Resumo de energia e custos]
    B --> D[Dashboard de gráficos]
    D --> E[Energia por sessão]
    D --> F[Custo por sessão]
    D --> G[Potência por sessão]
    D --> H[Solar versus rede]
```

## 4. Capturas de telas do projeto

### Protótipo de hardware

![Protótipo Arduino da Sprint 3](https://raw.githubusercontent.com/jucalemos/sprint_03_gurgel/main/imagens/prototipo.jpeg)

### Interface do GurAI

![Tela do GurAI](https://raw.githubusercontent.com/jucalemos/sprint_03_gurgel/main/imagens/gurai.jpeg)

### Conversa com GurAI

![Exemplo de conversa com GurAI](https://raw.githubusercontent.com/jucalemos/sprint_03_gurgel/main/imagens/conversa_gurai.jpeg)

### Mapa de carregadores

![Mapa de carregadores](https://raw.githubusercontent.com/jucalemos/sprint_03_gurgel/main/imagens/mapa.jpeg)

### Monitoramento e mapa

![Tela de monitoramento e mapa](https://raw.githubusercontent.com/jucalemos/sprint_03_gurgel/main/imagens/monitoramento_mapa.jpeg)

### Reserva de carregador

![Tela de reserva de carregador](https://raw.githubusercontent.com/jucalemos/sprint_03_gurgel/main/imagens/reserva_carregador.jpeg)

### Reservas

![Tela de reservas](https://raw.githubusercontent.com/jucalemos/sprint_03_gurgel/main/imagens/reservas.jpeg)

As imagens de interface registram telas já existentes no material da Sprint 3; não devem ser interpretadas como evidência de que pagamentos, reservas ou controle de hardware estejam integrados e operacionais, a menos que a equipe tenha demonstrado esses fluxos no vídeo final.
