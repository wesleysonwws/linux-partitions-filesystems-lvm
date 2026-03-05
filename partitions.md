# Partições de Disco no Linux

## O que é uma partição?

Uma partição é uma divisão lógica de um dispositivo de armazenamento, como um HD ou SSD.  
Ela permite que o sistema operacional organize e gerencie o espaço do disco de forma estruturada.

Cada partição pode conter um sistema de arquivos diferente e ser utilizada para armazenar dados, instalar sistemas operacionais ou separar diferentes tipos de informação.

## Por que usar partições?

O uso de partições traz diversas vantagens:

- Organização dos dados
- Separação entre sistema e arquivos do usuário
- Melhor gerenciamento de espaço em disco
- Possibilidade de utilizar diferentes sistemas de arquivos
- Facilidade de backup e recuperação

## Tipos de tabela de partição

Antes de criar partições, o disco precisa ter uma **tabela de partição**. As duas principais são:

### MBR (Master Boot Record)

Características:

- Suporta discos de até **2 TB**
- Máximo de **4 partições primárias**
- Tecnologia mais antiga
- Compatível com sistemas mais antigos

### GPT (GUID Partition Table)

Características:

- Suporta discos maiores que **2 TB**
- Permite muitas partições
- Mais seguro e moderno
- Utilizado em sistemas com **UEFI**

## Visualizando discos e partições

No Linux podemos visualizar os discos e suas partições com o comando:

```bash
lsblk
