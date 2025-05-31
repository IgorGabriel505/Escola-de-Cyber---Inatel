
# PicoCTF - Cookies

Solved by @[IgorGabriel505]  
This is a CTF about **Web Exploitation**, **Information Disclosure** and **Cookie Manipulation**.

---

## About the Challenge

O desafio apresenta um site acessível pelo seguinte link:

LinK: [http://verbal-sleep.picoctf.net:57968/](http://verbal-sleep.picoctf.net:57968/)

Ao acessar a página inicial, encontramos um simples formulário solicitando um **nome de usuário** e uma **senha**.

Como nenhuma credencial foi fornecida, o primeiro instinto é tentar inserir valores aleatórios, mas rapidamente somos redirecionados para uma página que informa **"Access Denied"**.

O nome do desafio, **"Cookies"**, já nos dá uma dica importante sobre onde devemos focar nossa atenção.

---

## Solution

### ✅ Passo 1 — Analisar o Comportamento da Página

- Acessei o site e inseri qualquer valor no campo de usuário e senha.
- Fui redirecionado para uma página de **"Access Denied"**.
- Como não havia nenhuma outra pista evidente, suspeitei que poderia haver alguma informação oculta no **cookie** de sessão.

---

### ✅ Passo 2 — Acessar e Inspecionar os Cookies

- Abri as **Ferramentas de Desenvolvedor** do navegador (F12).
- Fui até a aba **"Application"** (ou "Armazenamento" dependendo do navegador).
- Dentro da seção **Cookies**, localizei um cookie definido pelo site.

Exemplo visual:

```
Name: auth
Value: cGljb0NURntjMDBrMTNzXzRSM19uMHQyczNjdXIzfQ==
```

O valor do cookie parecia uma string codificada. Pelo padrão dos caracteres (letras maiúsculas, minúsculas, números e símbolos como `=` no final), desconfiei que fosse uma **codificação Base64**.

---

### ✅ Passo 3 — Decodificar o Cookie

- Copiei o valor do cookie.
- Acessei um site de decodificação Base64, como:  
  [https://www.base64decode.org/](https://www.base64decode.org/)  
  ou utilizei o comando `echo` no terminal:

```bash
echo cGljb0NURntjMDBrMTNzXzRSM19uMHQyczNjdXIzfQ== | base64 -d
```

- Ao decodificar, o resultado foi a seguinte string:

```
picoCTF{c00k13s_4r3_n0t_s3cur3}
```

**Pronto! A flag estava escondida dentro do cookie!**

---

### ✅ Passo 4 — Entendendo a Lógica do Desafio

Esse desafio explora a ideia de que muitas vezes informações sensíveis podem ser armazenadas em **cookies**, que são facilmente acessíveis no navegador do cliente. Mesmo que pareçam "escondidas" por estarem codificadas, codificações simples como Base64 não garantem segurança, apenas disfarçam os dados.

**Lições importantes:**

- Sempre desconfie de valores codificados em cookies.
- Codificação ≠ Criptografia.  
Base64, por exemplo, é **reversível facilmente**.
- Ferramentas do navegador são poderosas aliadas na exploração web.

---

## 🏁 Flag

```
picoCTF{c00k13s_4r3_n0t_s3cur3}
```

---

## ✅ Conclusão

Um desafio clássico de **Web Exploitation** que reforça a importância de entender como funcionam cookies, codificações e a necessidade de não confiar apenas na ocultação de dados para segurança.
