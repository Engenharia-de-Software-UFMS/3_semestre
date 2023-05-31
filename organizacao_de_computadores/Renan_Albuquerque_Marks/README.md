# Organização de Computadores






# Trabalho Prático

Um programa "disassembler" é responsável por fazer o inverso de um programa "assembler".

Em um "assembler", um programa escrito em linguagem de montagem(texto) é convertido para binário (linguagem de máquina) para ser executado na CPU. Em um "disassembler", o processo inverso é feito: o código binário do programa em linguagem de máquina é convertido novamente para linguagem de montagem.

Nesta avaliação deverá ser implementado um disassembler (desmontador) de programas binários para a ISA MARIE. A linguagem de programação utilizada para a avaliação será a linguagem Python na versão 3.

Cada aluno deverá implementar um "disassembler" que recebe via linha de comando o nome do arquivo binário que deve ser aberto e convertido em linguagem de montagem. Isto é, cada instrução em binário deve ser lida e convertida para seu mnemônico e parâmetro correspondentes.

Devem ser suportadas todas as instruções da ISA MARIE.

Cada instrução deve ser impressa em uma linha. Primero, imprime-se o mnemônico da instrução. Se a instrução precisar do operando de endereço, ele deverá ser impresso em base hexadecimal e separado do mnemônico da instrução com um espaço.

Por exemplo: lê-se do arquivo o valor "0xDA00" (2 bytes), equivalente a uma instrução MARIE. Em seguida, decodifica-se a instrução separando o campo "opcode" e o campo "endereço" dessa instrução. O campo opcode tem o valor "0xD" e o campo endereço tem o valor "0xA00". Após isso, deve-se imprimir na tela "loadi A00".

Caso a instrução não utilize o campo de endereço, deve-se imprimir somente o mnemônico equivalente ao opcode.

Por exemplo: lê-se do arquivo o valor "0x7000" (2 bytes), equivalente a uma instrução MARIE. Em seguida, decodifica-se a instrução separando o campo "opcode" e o campo "endereço" dessa instrução. O campo opcode tem o valor "0x7" e o campo endereço tem o valor "0x000". Após isso, deve-se imprimir na tela "halt", pois essa instrução não faz uso do parâmetro de endereço.

Como Testar
Para testar seu desmontador, é necessário criar arquivos com conteúdo binário que serão abertos e lidos pelo "disassembler". Esses arquivos podem ser criados de diferentes maneiras. Uma forma prática e criá-los usando editores hexadecimais, como o Okteta(Linux) ou o Hexed(Serviço web).

De acordo com a ISA MARIE, cada instrução possui 2 bytes (16 bits). Um arquivo binário MARIE possui várias instruções, uma após a outra. Se o programa binário MARIE possui 2 instruções, ele terá 4 bytes no total. Se um programa binário MARIE possui 10 instruções, ele terá 20 bytes no total.

Após criar o arquivo com as instruções codificadas em binário, seu software "disassembler" deve abrir esse arquivo e ir buscando, de 2 em 2 bytes, cada uma das intruções. Cada instrução deve ser decodificada e impressa na tela utilizando a função "print()" de Python, com uma instrução por linha.

Por exemplo, um arquivo binário com a seguinte sequência de bytes (valores retratados aqui em base hexadecimal) "11 11 21 12 11 13 41 16 21 15 11 14 B1 12 21 14" deverá ser decodificado como:

load 111
store 112
load 113
subt 116
store 115
load 114
addi 112
store 114