
# PicoCTF - Cookies

Solved by @[IgorGabriel505]  
This is a CTF about **Web Exploitation**, **Information Disclosure** and **Cookie Manipulation**.

---

## About the Challenge

O desafio apresenta um site acessível pelo seguinte link:

LinK: [http://verbal-sleep.picoctf.net:57968/](http://verbal-sleep.picoctf.net:57968/)

Ao acessar a página inicial, Se encontra um simples formulário solicitando um **nome de usuário** e uma **senha**.

Como nenhuma credencial da senha ou do usuario nos foi dado para a resolução do ctf, eu tente inserir valores aleatórios nas credenciais, nisso fui redirecionado para uma página que informa **"Access Denied"**.

Pelo nome do desafio já deixa a entender que ele terá haver com **"Cookies"**, sendo uma dica importante sobre onde deve ser procurado a Flag. 

---

## Solution :

### Passo 1 — Acessar e Inspecionar os Cookies:
No Google Crome, cliquei com o botão direito do mouse sobre a página e selecionei a opção "Inspecionar". Após isso eu fui atrás de encontrar os cookies da página (já que imaginei que o enredo da questão seria uma dica para isso):
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

---

## Flag:

```
picoCTF{c00k1e_m0nster_l0ves_c00kies_6E81FC1E}
```
