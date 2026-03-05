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
```

Exemplo de saída:
<img width="1536" height="1024" alt="lsblk img" src="https://github.com/user-attachments/assets/9a770fff-d631-4253-ad85-37dd35102404" />

Esse comando mostra:

- Discos disponíveis
- Partições existentes
- Pontos de montagem

## Criando partições

Uma das ferramentas clássicas para criar partições no Linux é o **fdisk**.

Exemplo de uso:

```bash
sudo fdisk /dev/sdb
```
Exemplo de saída:
<img width="1536" height="1024" alt="particao img" src="https://github.com/user-attachments/assets/140ade3c-2493-40f6-9f23-eab4e3260014" />

Esse comando mostra:

- Criar novas partições
- Excluir partições
- Alterar tipos de partição
- Salvar alterações no disco

## Conclusão

As partições são fundamentais para a organização do armazenamento no Linux.  
Elas permitem dividir um disco físico em múltiplas áreas lógicas, facilitando o gerenciamento do sistema e dos dados.
Sempre verifique com `lsblk` antes de utilizar o `fdisk`, garantindo que o disco correto esteja sendo manipulado.
