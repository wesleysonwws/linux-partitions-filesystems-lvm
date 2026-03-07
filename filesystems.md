# Sistemas de Arquivos no Linux

## O que é um Sistema de Arquivos?

Um sistema de arquivos é a forma como o sistema operacional organiza e gerencia os dados dentro de uma partição.

Ele define:

- como os arquivos são armazenados
- como os diretórios são organizados
- como o sistema encontra os dados no disco

Sem um sistema de arquivos, o sistema operacional não consegue ler ou gravar dados na partição.

---

## Relação entre Disco, Partição e Sistema de Arquivos

A estrutura funciona da seguinte forma:

Disco → Partição → Sistema de Arquivos → Arquivos

Exemplo:

```
/dev/sda
├─ /dev/sda1 → ext4
├─ /dev/sda2 → swap
└─ /dev/sda3 → xfs
```

Cada partição pode utilizar um sistema de arquivos diferente.

---

## Sistemas de Arquivos mais comuns no Linux

### ext4

O **ext4 (Fourth Extended Filesystem)** é um dos sistemas de arquivos mais utilizados no Linux.

Características:

- estável
- rápido
- suporta arquivos grandes
- possui journaling (registro de operações para evitar perda de dados)

Distribuições que utilizam muito ext4:

- Ubuntu
- Debian
- Linux Mint

---

### XFS

O **XFS** é um sistema de arquivos de alto desempenho.

Características:

- excelente desempenho com arquivos grandes
- muito utilizado em servidores
- alta escalabilidade

Distribuições que utilizam XFS com frequência:

- Red Hat
- CentOS
- Rocky Linux

---

### Btrfs

O **Btrfs (B-tree File System)** é um sistema de arquivos moderno com recursos avançados.

Características:

- snapshots
- compressão
- verificação de integridade
- gerenciamento avançado de volumes

Distribuições que utilizam Btrfs:

- openSUSE
- algumas distribuições modernas

---

### Swap

O **swap** não é exatamente um sistema de arquivos tradicional.

Ele funciona como **memória virtual**, sendo utilizado quando a memória RAM está cheia.

---

## Criando um Sistema de Arquivos

Depois de criar uma partição, é necessário formatá-la com um sistema de arquivos.

Criando um sistema de arquivos ext4:

```bash
sudo mkfs.ext4 /dev/sdb1
```

Criando um sistema de arquivos XFS:

```bash
sudo mkfs.xfs /dev/sdb1
```

---

## Verificando Sistemas de Arquivos

Podemos verificar os sistemas de arquivos presentes no sistema com os comandos:

```bash
lsblk -f
```

ou

```bash
df -T
```

Esses comandos mostram:

- partições
- tipo de sistema de arquivos
- pontos de montagem

---

## Exemplo prático

Criando e utilizando um sistema de arquivos em uma nova partição.

Passos:

1. Criar a partição
2. Formatar a partição
3. Montar a partição

Exemplo:

```bash
sudo mkfs.ext4 /dev/sdb1
sudo mount /dev/sdb1 /mnt
```

Após isso, a partição já poderá ser utilizada para armazenar arquivos.

---

## Conclusão

Os sistemas de arquivos são responsáveis por organizar e gerenciar os dados dentro das partições.

No Linux existem diversos tipos de sistemas de arquivos, sendo os mais comuns:

- ext4
- XFS
- Btrfs

A escolha do sistema de arquivos depende das necessidades do sistema e do tipo de uso.
