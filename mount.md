# Montagem de Sistemas de Arquivos no Linux

## O que é montar um sistema de arquivos?

No Linux, para acessar uma partição ou dispositivo de armazenamento, primeiro precisamos **montá-lo**.

Montar significa **conectar o sistema de arquivos de um dispositivo a um diretório do sistema**.

Depois que o dispositivo é montado, podemos acessar seus arquivos normalmente.

---

## Como funciona a montagem no Linux

No Linux, todos os diretórios fazem parte de uma única estrutura que começa na raiz:

```
/
```

Quando um dispositivo é montado, ele passa a fazer parte dessa estrutura.

Exemplo:

```
/
├── home
├── etc
├── var
└── mnt
```

Se montarmos um disco no diretório `/mnt`, os arquivos desse disco aparecerão dentro dele.

---

## Diretórios comuns para montar dispositivos

### /mnt

O diretório `/mnt` é normalmente usado para **montagens temporárias feitas manualmente**.

Exemplo:

```bash
sudo mount /dev/sdb1 /mnt
```

---

### /media

O diretório `/media` é usado principalmente para **dispositivos removíveis**, como:

- pendrives
- HDs externos
- cartões de memória

Muitas distribuições Linux montam esses dispositivos automaticamente nesse diretório.

Exemplo:

```
/media/usuario/pendrive
```

---

## Comando mount

O comando `mount` é usado para montar um sistema de arquivos.

Sintaxe básica:

```bash
mount dispositivo diretorio
```

Exemplo:

```bash
sudo mount /dev/sdb1 /mnt
```

Nesse exemplo:

- `/dev/sdb1` é a partição
- `/mnt` é o diretório onde ela será montada

Depois disso, os arquivos da partição estarão disponíveis dentro de `/mnt`.

---

## Verificando sistemas montados

Podemos verificar quais sistemas de arquivos estão montados usando comandos como:

```bash
lsblk
```

ou

```bash
df -h
```

Esses comandos mostram:

- dispositivos
- pontos de montagem
- espaço disponível em disco

---

## Desmontando um sistema de arquivos

Para desmontar um sistema de arquivos usamos o comando `umount`.

Exemplo:

```bash
sudo umount /mnt
```

Depois de desmontar, o dispositivo não estará mais acessível naquele diretório.

---

## Montagem automática com /etc/fstab

Se quisermos que um disco seja montado automaticamente quando o sistema iniciar, usamos o arquivo:

```
/etc/fstab
```

Esse arquivo guarda as configurações de montagem automática.

Exemplo de configuração:

```
/dev/sdb1   /dados   ext4   defaults   0   2
```

Significado básico:

- `/dev/sdb1` → partição
- `/dados` → diretório onde será montada
- `ext4` → sistema de arquivos

---

## Exemplo prático

Criando um diretório para montagem:

```bash
sudo mkdir /dados
```

Montando a partição:

```bash
sudo mount /dev/sdb1 /dados
```

Verificando se foi montada:

```bash
df -h
```

Agora os arquivos da partição estarão disponíveis no diretório `/dados`.

---

## Conclusão

No Linux, dispositivos de armazenamento precisam ser montados para que seus arquivos possam ser acessados.

Os comandos principais são:

- `mount` → montar um sistema de arquivos
- `umount` → desmontar um sistema de arquivos

Também podemos configurar montagens automáticas usando o arquivo `/etc/fstab`.
