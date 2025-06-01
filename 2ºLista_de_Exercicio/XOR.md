# XOR  
**Resolvido por @IgorGabriel505**  

Este exercício aborda a aplicação da operação *XOR bit a bit em caracteres de uma string*.

---

## Temas Envolvidos

- Operação lógica XOR (OU exclusivo)  
- Manipulação de strings e caracteres Unicode  
- Conversão entre caracteres e seus códigos inteiros Unicode  
- Cifração baseada em XOR

---

## Descrição do Exercício

O desafio me forneceu uma string chamada **label** onde eu deveria utilizando a aplicação **XOR** com a chave 13 para encontrar uma nova string *(sendo a flag do desafio)*.  

![](Imagens_label/1.png)

---

## Resolução do Desafio

### Passo 1 — Definir a função que aplica XOR em cada caractere
Para resolver esse desafio eu fui atras de algum programa onde eu poderia inserir uma string e a chave (key) e rescrevese em XOR.
Procurando na web pelo navegador Google Crome eu encontrei um projeto no github (em Python) onde ele justamente faz essa operação XOR.

Projeto do github:   [https://cryptools.github.io/XORCipher/](https://cryptools.github.io/XORCipher/)  

Após ter baixado o codigo do projeto do github eu abri um site que copila codigos em python e colei ele por lá.
site utilizado: [https://www.mycompiler.io/pt/new/python](https://www.mycompiler.io/pt/new/python)


### 2. Aplicar a função na string `"label"` com a chave 13

### 3. Exibir a flag com o resultado obtido

---

## Flag:
crypto{aloha}
```
