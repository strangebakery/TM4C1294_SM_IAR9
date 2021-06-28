# TM4C1294_SM_IAR9
Exemplos Assembly ARM Cortex-M (IDE IAR EWARM V9.10)

a) Como valores negativos são codificados?
ans.: Valores negativos são armazenados como complemento de 2.

b) É possível visualizar os estados individuais dos flags?
ans.: Sim, porém as flags só são triggadas se o sufixo S for adicionado às instruções.

c) Como o PC está relacionado à janela Disassembly?
ans.: Os possíveis valores que o PC pode assumir estão contidos na primeira coluna da janela de disassembly, e correspondem aos endereços de memória de cada instrução do código.

d) Quais instruções são de 16 bits e quais são de 32 bits?
ans.: As instruções MOV (sem sufixo S, equivalente a MOV.W), MVN e MVNS são instruções de 32 bits, enquanto a instrução MOVS é uma instrução de 16 bits.

e) Os mnemônicos do disassembly correspondem exatamente aos mnemônicos usados no programa?
ans.: Os mnemônicos são diferentes, geralmente seguidos de ".W" na janela de disassembly.

f) A construção da aplicação foi bem sucedida (ao permutar as instruções MOV por MVN)?
ans.: O build do projeto é bem sucedido ao trocar as instruções MOV por MVN.

g) Procure decifrar os resultados de cada operação.
ans.: A primeira instrução carrega o valor 0x55 no registrador zero. 
      A segunda instrução carrega do valor do R0 (0x55) deslocado 16 bits para a esquerda (0x550000) para R1.
      A 3.ª instrução carrega o valor de R1 (0x550000) deslocado 8 bits para a direita (0x5500) para R2.
      A 4.ª instrução carrega o valor de R2 (0x5500) dividido por 4 (equivalente ao deslocamento de 4 bits para a direita) para R3.
      A 5.ª instrução rotaciona os 2 LSB do R3 (0x550) da direita para esquerda (o valor é deslocado 2bits para a direita e os 2 LSB originais agora são os 2 MSB do novo valor := 0x154) e armazena o resultado em R4.
      A 6.ª instrução desloca o valor de R4 1 bit para a direita, armazena o resultado em R5 juntamente com o valor da flag C do APSR no 32.º bit do registrador de destino (R5).
