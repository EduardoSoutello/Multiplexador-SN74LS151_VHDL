# Multiplexador SN74LS151 - VHDL

Implementação em VHDL de um multiplexador 8-para-1 SN74LS151 com sinal de controle (strobe).

## Descrição

Este projeto implementa um multiplexador digital 8-para-1 equivalente ao circuito integrado SN74LS151. O multiplexador seleciona uma de oito entradas de dados e a direciona para a saída baseado nos sinais de seleção.

## Características

- **Tipo:** Multiplexador 8-para-1
- **Entradas de Dados:** 8 linhas (I0 a I7)
- **Seleção:** 3 bits (S0, S1, S2)
- **Controle:** Strobe (ativo baixo)
- **Saídas:** Normal (Y) e Invertida (W)

## Arquitetura

### Portas

- **Entradas:**
  - I0 a I7: Entradas de dados (8 bits)
  - S0, S1, S2: Seleção de entrada (3 bits)
  - STB: Strobe (controle ativo baixo)

- **Saídas:**
  - Y: Saída normal
  - W: Saída invertida

### Lógica de Funcionamento

O multiplexador seleciona a entrada correspondente aos bits de seleção quando o strobe está ativo (baixo). Quando o strobe está inativo (alto), ambas as saídas são forçadas para '0'.

## Tabela Verdade

| STB | S2 | S1 | S0 | Entrada Selecionada |
|-----|----|----|----|--------------------|
| 1   | X  | X  | X  | Nenhuma (Y=0, W=0) |
| 0   | 0  | 0  | 0  | I0                 |
| 0   | 0  | 0  | 1  | I1                 |
| 0   | 0  | 1  | 0  | I2                 |
| 0   | 0  | 1  | 1  | I3                 |
| 0   | 1  | 0  | 0  | I4                 |
| 0   | 1  | 0  | 1  | I5                 |
| 0   | 1  | 1  | 0  | I6                 |
| 0   | 1  | 1  | 1  | I7                 |

## Como Usar

### Simulação

1. Abra o arquivo multiplex_SN74LS151.vhdl em seu ambiente de desenvolvimento VHDL
2. Compile o código
3. Configure os sinais de teste no testbench
4. Execute a simulação

### Síntese

1. Carregue o arquivo no software de síntese (Quartus, Vivado, etc.)
2. Configure as pinagens no arquivo de constraints
3. Sintetize e implemente o design
4. Programe o FPGA/CPLD

## Ferramentas Sugeridas

- **ModelSim/QuestaSim** - Simulação
- **Intel Quartus Prime** - Síntese para FPGAs Altera/Intel
- **Xilinx Vivado** - Síntese para FPGAs Xilinx
- **GHDL** - Simulador VHDL open-source

## Referências

- Datasheet SN74LS151 - Texas Instruments
- IEEE Std 1076-2008 (VHDL Language Reference Manual)
