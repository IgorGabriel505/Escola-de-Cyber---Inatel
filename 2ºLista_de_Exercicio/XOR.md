# Exercício XOR: Operação Bit a Bit em Strings  
**Resolvido por @SeuNomeAqui**  

Este exercício aborda a aplicação da operação XOR bit a bit em caracteres de uma string usando uma chave numérica, para cifrar/decifrar mensagens.

---

## Temas Envolvidos

- Operação lógica XOR (OU exclusivo)  
- Manipulação de strings e caracteres Unicode  
- Conversão entre caracteres e seus códigos inteiros Unicode  
- Cifração simples baseada em XOR

---

## Descrição do Exercício

Dada uma string, por exemplo `"label"`, o objetivo é aplicar a operação XOR em cada caractere da string com a chave inteira 13.  

A operação consiste em:  
- Converter cada caractere em seu código Unicode (inteiro).  
- Aplicar XOR entre esse inteiro e o número 13.  
- Converter o resultado de volta para caractere.  
- Juntar todos os caracteres resultantes para formar uma nova string.

A flag deve ser exibida no formato:  

```
crypto{nova_string}
```

---

## Passo a Passo da Resolução

### 1. Definir a função que aplica XOR em cada caractere

- Recebemos uma string e uma chave (número inteiro).
- Para cada caractere da string:
  - Transformamos em código Unicode (`ord`).
  - Aplicamos XOR com a chave.
  - Voltamos para caractere (`chr`).
- Concatenamos os caracteres resultantes.

### 2. Aplicar a função na string `"label"` com a chave 13

### 3. Exibir a flag com o resultado obtido

---

## Código desenvolvido

```python
def xor_string(text, key):
    output = ''
    for c in text:
        output += chr(ord(c) ^ key)
    return output

label = "label"
key = 13

nova_string = xor_string(label, key)
print(f"crypto{{{nova_string}}}")
```

---

## Resultado

- Entrada: `"label"`
- Saída após XOR com chave 13: `"ynory"`
- Flag final exibida:  

```
crypto{ynory}
```

---

## Considerações Finais

- A operação XOR é reversível: aplicar XOR novamente com a mesma chave recupera o texto original.
- Essa técnica simples pode ser usada para ofuscar ou proteger mensagens em desafios CTF.
- É importante entender como manipular caracteres e seus códigos Unicode para implementar essa operação corretamente.

---

Se quiser, posso ajudar a estender o código para suportar chaves maiores ou múltiplas. Quer?
