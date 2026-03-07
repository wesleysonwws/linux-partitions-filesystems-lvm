# LVM no Linux (Logical Volume Manager)

## O que é LVM?

O **LVM (Logical Volume Manager)** é uma tecnologia usada no Linux para gerenciar discos e partições de forma mais flexível.

Com o LVM podemos:

- juntar vários discos
- aumentar ou diminuir volumes
- gerenciar melhor o espaço em disco

Isso é muito usado em **servidores Linux**.

---

## Por que usar LVM?

Com partições tradicionais, o tamanho do disco é fixo.

Exemplo:

Se criarmos uma partição de **20GB**, ela sempre terá esse tamanho.

Se o espaço acabar, normalmente precisamos:

- recriar a partição
- ou reorganizar o disco

Com **LVM**, podemos **aumentar ou ajustar volumes com mais facilidade**.

---

## Estrutura do LVM

O LVM funciona em três camadas principais:

```
Disco / Partição
      ↓
Physical Volume (PV)
      ↓
Volume Group (VG)
      ↓
Logical Volume (LV)
```

---

## Physical Volume (PV)

O **Physical Volume (PV)** é o disco ou partição que será usado pelo LVM.

Exemplo:

```
/dev/sdb
/dev/sdc
```

Esses discos podem ser transformados em volumes físicos.

Criando um PV:

```bash
sudo pvcreate /dev/sdb
```

---

## Volume Group (VG)

O **Volume Group (VG)** é um grupo formado por um ou mais Physical Volumes.

Ele funciona como um **pool de armazenamento**.

Exemplo:

```
VG_dados
```

Criando um Volume Group:

```bash
sudo vgcreate vg_dados /dev/sdb
```

Agora o grupo `vg_dados` possui o espaço do disco `/dev/sdb`.

---

## Logical Volume (LV)

O **Logical Volume (LV)** funciona como uma partição, mas é criado dentro do Volume Group.

Exemplo:

```
lv_backup
```

Criando um Logical Volume:

```bash
sudo lvcreate -L 10G -n lv_backup vg_dados
```

Significado:

- `-L 10G` → tamanho do volume
- `-n` → nome do volume
- `vg_dados` → grupo onde será criado

---

## Criando sistema de arquivos no volume lógico

Depois de criar o Logical Volume, precisamos criar um sistema de arquivos nele.

Exemplo:

```bash
sudo mkfs.ext4 /dev/vg_dados/lv_backup
```

---

## Montando o volume lógico

Agora podemos montar o volume lógico normalmente.

```bash
sudo mount /dev/vg_dados/lv_backup /mnt
```

Depois disso, o volume estará disponível no diretório `/mnt`.

---

## Verificando informações do LVM

Alguns comandos úteis para verificar o LVM:

Ver Physical Volumes:

```bash
pvs
```

Ver Volume Groups:

```bash
vgs
```

Ver Logical Volumes:

```bash
lvs
```

---

## Conclusão

O LVM permite gerenciar discos de forma mais flexível no Linux.

Com ele podemos:

- criar volumes lógicos
- juntar vários discos
- aumentar volumes facilmente

Por isso ele é muito utilizado em **servidores e ambientes corporativos**.
