# Comandos Openssl Rand

**`Sintaxe Básica:`** openssl rand [opções] NUMERO_DE_BYTES

#### Gerar 16 bytes aleatórios em formato hexadecimal

~~~sh
Entrada:

openssl rand -hex 16

Saída:

4e3c5d8f9a2b1c6d4f7e8a9b0c1d2e3f
~~~

#### Gerar 32 bytes aleatórios e codificar em Base64

~~~
Entrada:

openssl rand -base64 32

Saída:

c2Nhg5Jb3E4aP9dKbWv0YqRfsXZT28xB
~~~

#### Gerar bytes aleatórios no formato binário e salvar em um arquivo

~~~
Entrada: 

openssl rand 32 > chave_secreta.bin
~~~

#### Gerar uma senha aleatória de 12 caracteres alfanuméricos

~~~
Entrada:

openssl rand -base64 12 | tr -dc 'A-Za-z0-9'
~~~

#### Gerar um UUID aleatório baseado em OpenSSL

~~~
Entrada:

openssl rand -hex 16 | awk '{print substr($0,1,8) "-" substr($0,9,4) "-4" substr($0,13,3) "-" substr($0,16,4) "-" substr($0,20,12)}'
~~~

#### Gerar e sobrescrever o mesmo arquivo

~~~
#!/bin/bash
openssl rand -hex 4 > numero.txt
echo "Número salvo em numero.txt: $(cat numero.txt)"
~~~

#### Gerar e adicionar novos números ao mesmo arquivo

~~~
#!/bin/bash
openssl rand -hex 4 >> numero.txt
echo "Número gerado e adicionado ao arquivo."
cat numero.txt
~~~
