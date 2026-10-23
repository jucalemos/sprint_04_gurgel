# Arquitetura do Gurgel — Sprint 4

## Componentes

### Protótipo Arduino/Tinkercad

O arquivo `tinkercad/prototipo.ino` descreve um circuito com Arduino Uno:

- **A0:** potenciômetro que representa a potência solar simulada;
- **A1:** potenciômetro que representa a demanda simulada;
- **Pino 7:** botão para iniciar ou encerrar a sessão;
- **Pinos 8 a 11:** LEDs de estado;
- **Serial Monitor:** apresenta valores e mensagens do programa.


### Scripts Python

- `python/gerenciamento.py`: recebe valores digitados no terminal e aplica a regra de limite de potência;
- `python/dados.csv`: contém oito sessões ilustrativas;
- `python/simulacao.py`: resume os dados do CSV;
- `python/dashboard.py`: calcula indicadores e apresenta gráficos.


## Regra de gerenciamento

O limite configurado é de **10 kW**:

1. A potência liberada corresponde à demanda, limitada a 10 kW.
2. A parcela solar utilizada é o menor valor entre a potência solar simulada e a potência liberada.
3. A parcela atribuída à rede é a diferença entre a potência liberada e a parcela solar utilizada.
4. O programa indica o estado por mensagens e LEDs.
