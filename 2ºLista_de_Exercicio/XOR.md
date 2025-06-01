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

Após ter baixado o codigo do projeto do github eu abri um site que copila códigos em python e colei o programa nele.
site utilizado: [https://www.mycompiler.io/pt/new/python](https://www.mycompiler.io/pt/new/python)

![](Imagens_label/2.png)


### 2. Aplicar a função na string `"label"` com a chave 13

Para aplicar a função que executa a operação XOR eu deveria colocar os valores da string label e da chave 13 (key) como variaveis para eles serão executadadas dentro da função.

- Criei as variaveis label e key com os respectivos valores (label, 13)
- Executei a função XOR com os valores das variaveis que criei
- Executei um comando em que imprimia na tela o resultado da criptografia

![](Imagens_label/3.0.png)

### 3. Exibir a flag com o resultado obtido

```

## Flag:
crypto{aloha}
```
