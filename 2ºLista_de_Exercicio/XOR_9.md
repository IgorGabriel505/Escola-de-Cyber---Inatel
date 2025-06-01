# XOR_9  
**Resolvido por @IgorGabriel505**  

Este exercício aborda a aplicação da operação *XOR bit a bit em caracteres de uma string* e *codificação* e *decodificação hexadecimal*.

---

## Temas Envolvidos

- Operação lógica XOR  
- Manipulação de strings e caracteres Unicode  
- Conversão entre caracteres e seus códigos inteiros Unicode  
- Cifração baseada em XOR

---

## Descrição do Exercício

<!-- Coloque aqui o enunciado completo do desafio -->

---

## Resolução do Desafio

### Passo 1 — 

<!-- Descreva a primeira etapa da resolução -->

---

### Passo 2 — 

<!-- Descreva a segunda etapa da resolução -->

---

### Passo 3 — 

<!-- Descreva a terceira etapa da resolução -->

```python
# Exemplo de código para XOR (coloque aqui seu código usado)
def decrypt_xor_bytes(data: bytes, key: int) -> str:
    output = bytes([b ^ key for b in data])
    return output.decode('utf-8', errors='ignore')

encrypted_hex = "73626960647f6b206821204f21254f7d694f7624662065622127234f726927756d"
encrypted_bytes = bytes.fromhex(encrypted_hex)
key = 16

decrypted = decrypt_xor_bytes(encrypted_bytes, key)
print("Texto decodificado:", decrypted)
```

---

## Flag:

```
crypto{aloha}
```
