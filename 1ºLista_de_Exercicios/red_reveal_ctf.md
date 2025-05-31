
# RED
**Resolvido por @IgorGabriel505**  
 Este é um CTF sobre Forensics

---

## Temas Envolvidos

- Esteganografia em imagens  
- Extração de bits menos significativos (LSB)  
- Decodificação Base64  
- Manipulação de imagem (RGBA)

---

## Descrição do Desafio

Foi fornecida uma imagem chamada `red.png`, que ao abri-la aparentava ser apenas um quadrado totalmente vermelho. No entanto, o desafio sugeria que havia algo oculto, com dicas como:

![](Imagens_RED/red.png)

> “A imagem parece pura, mas é?”  
> “Verifique o nome do Facebook agora.”  

---

## Resolução do Desafio

A resolução foi feita usando análise programática da imagem para extrair dados escondidos nos **bits menos significativos** de cada canal de cor.

### 1. Inspeção da Imagem

- Abrindo a imagem `red.png` e verificando suas informações, percebemos que ela tinha dimensão `128x128` e continha **4 canais RGBA** (vermelho, verde, azul e alpha).

![](Imagens_RED/ima.png)

### 2. Extração dos Bits LSB

Cada canal (R, G, B, A) possui 8 bits por pixel. A técnica de esteganografia LSB utiliza o **último bit de cada canal** para armazenar dados ocultos.

Foi feito o seguinte:
- Extraíndo o **último bit de cada canal** (1 bit por canal, 4 bits por pixel).
- Esses bits foram agrupados a cada 8, formando bytes.
- Os bytes foram unidos em uma sequência binária completa.

### 3. Decodificação do Conteúdo

Com os bytes formados, convertemos para texto e encontramos o seguinte texto:

```
cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==
```

Esse conteúdo é claramente codificado em **Base64**. Decodificamos a string por meio do site **'Base64'** e apareceu:

```
picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}
```

---

## Flag

```text
picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}
```
