# Partições, Sistemas de Arquivos e LVM no Linux

Este projeto apresenta conceitos fundamentais sobre gerenciamento de armazenamento no Linux, incluindo particionamento de discos, criação de sistemas de arquivos e utilização do LVM (Logical Volume Manager).

O objetivo é demonstrar, de forma prática e teórica, como o Linux organiza e gerencia dispositivos de armazenamento.

## Conteúdos abordados

- Conceito de partições de disco
- Criação e gerenciamento de partições
- Tipos de sistemas de arquivos no Linux
- Formatação de partições
- Montagem de sistemas de arquivos
- Introdução ao LVM (Logical Volume Manager)

## Estrutura do Projeto

- `partitions.md` — Conceitos e criação de partições
- `filesystems.md` — Sistemas de arquivos no Linux
- `mount.md` — Montagem de sistemas de arquivos
- `lvm.md` — Gerenciamento de volumes com LVM

## Ferramentas utilizadas

- `lsblk`
- `fdisk`
- `mkfs`
- `mount`
- `umount`
- `pvcreate`
- `vgcreate`
- `lvcreate`

## Ambiente de Teste

- Máquina Virtual (VirtualBox / VMware)
- Distribuição Linux: Ubuntu / Debian / Rocky
- Disco virtual dedicado para testes
