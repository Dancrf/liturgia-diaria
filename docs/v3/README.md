# Documentação — v3

**Endpoint base:** `https://liturgia.up.railway.app/v3/` ou `https://liturgia.up.railway.app/api/`

---

## Formas de consulta

### Liturgia do dia atual

```
GET https://liturgia.up.railway.app/v3/
```

### Por query string

```
GET https://liturgia.up.railway.app/v3/?dia={dia}&mes={mes}&ano={ano}
```

| Parâmetro | Tipo | Obrigatório | Descrição |
|-----------|------|-------------|-----------|
| `dia` | `string` | sim | Dia do mês |
| `mes` | `string` | não | Mês *(padrão: mês atual)* |
| `ano` | `string` | não | Ano *(padrão: ano atual)* |

Exemplos:
```
https://liturgia.up.railway.app/v3/?dia=20&mes=03
https://liturgia.up.railway.app/v3/?dia=20&mes=03&ano=2024
```

### Por parâmetros de rota

```
GET https://liturgia.up.railway.app/v3/{dia}-{mes}-{ano}
```

Exemplo:
```
https://liturgia.up.railway.app/v3/20-03
```

### Por período

```
GET https://liturgia.up.railway.app/v3/?periodo={dias}
```

Retorna múltiplas liturgias a partir da data atual, incluindo o dia de hoje.

> ⚠️ O valor máximo permitido para `periodo` é 7.  
> Caso `periodo` seja utilizado junto com `dia`, `mes` ou `ano`, ele será ignorado.

---

## Estrutura da resposta

```json
{
  "data": "string",
  "celebracoes": [ Celebracao ]
}
```

---

### `Celebracao`

```json
{
  "id": "string",
  "liturgia": "string",
  "cor": "string",
  "principal": true,
  "oracoes": Oracoes,
  "antifonas": Antifonas,
  "leituras": [ Leitura ]
}
```

**`cor`** pode retornar os seguintes valores:

| Valor |
|-------|
| `Verde` |
| `Vermelho` |
| `Roxo` |
| `Rosa` |
| `Branco` |

**`principal`** indica qual é a celebração recomendada para o dia:

| Valor | Descrição |
|-------|-----------|
| `true` | Celebração principal do dia |
| `false` | Celebração secundária (ex: memória facultativa) |

> **Sobre múltiplas celebrações:**  
> Em dias com mais de uma celebração no array `celebracoes`, apenas uma terá `principal: true`.  
> As demais terão `principal: false` e representam opções que o celebrante pode escolher, como uma memória facultativa de um santo.

---

### `Oracoes`

```json
{
  "coleta": "string",
  "oferendas": "string",
  "comunhao": "string",
  "extras": [ Extra ]
}
```

---

### `Extra`

```json
{
  "titulo": "string",
  "texto": "string"
}
```

---

### `Antifonas`

```json
{
  "entrada": "string",
  "comunhao": "string"
}
```

---

### `Leitura`

```json
{
  "ordem": 1,
  "tipo": "string",
  "rotulo": "string",
  "opcoes": [ Opcao ]
}
```

> **`rotulo`** é o nome da leitura na sequência da Missa.
> Exemplos: `"Primeira Leitura"`, `"Salmo Responsorial"`, `"Evangelho"`, `"Proclamação da Páscoa"`

> **`opcoes`** sempre é um array, mesmo quando há apenas uma opção. Representa versões alternativas da mesma leitura. A utilização de uma ou outra opção depende do leitor.

**`tipo`** pode retornar os seguintes valores:

| Valor | Descrição |
|-------|-----------|
| `leitura` | Leitura comum (1ª ou 2ª leitura) |
| `salmo` | Salmo responsorial |
| `evangelho` | Evangelho |
| `extra` | Sequências litúrgicas utilizadas em solenidades ou outros textos a serem lidos |

---

### `Opcao`

```json
{
  "referencia": "string (opcional)",
  "titulo": "string (opcional)",
  "refrao": "string (opcional)",
  "texto": "string"
}
```

| Campo | Descrição |
|-------|-----------|
| `referencia` | Referência bíblica (ex: `"Mt 21, 1-11"`) |
| `titulo` | O que é proclamado antes do texto (ex: `"Leitura do Livro do profeta Isaías"`). Ausente em `salmo` e em `extra`. |
| `refrao` | Exclusivo de `salmo`. |
| `texto` | Texto completo da leitura. |

---

## Liturgia não encontrada

Quando não houver liturgia disponível para a data informada, a API retornará status `404`:

```json
{
  "erro": "Não encontramos nenhuma liturgia para esta data",
  "data": "01/02/2080"
}
```

---

## Exemplo completo de um dia com memória facultativa

```json
{
    "data": "03/01/2024",
    "celebracoes": [
      {
        "id": "4-feira-do-tempo-do-natal-antes-da-epifania",
        "liturgia": "4ª feira do Tempo do Natal antes da Epifania",
        "cor": "Branco",
        "principal": true,
        "oracoes": {
          "coleta": "Concedei, Deus todo-poderoso, que a vossa salvação, qual nova luz dos céus para a redenção do mundo, surja para renovar sempre os nossos corações. Por Nosso Senhor Jesus Cristo, vosso Filho, que é Deus, e convosco vive e reina, na unidade do Espírito Santo, por todos os séculos dos séculos.",
          "oferendas": "Ó Deus, fonte da verdadeira devoção e da paz, concedei que vos honremos dignamente com esta oferenda e, pela fiel participação nos sagrados mistérios, sejam reforçados os laços que nos unem. Por Cristo, nosso Senhor.",
          "comunhao": "Senhor, que o vosso povo, sustentado com tantas graças, possa receber hoje e sempre os dons do vosso amor para que, confortado pelos bens transitórios, busque com mais confiança os bens eternos. Por Cristo, nosso Senhor.",
          "extras": []
        },
        "antifonas": {
          "entrada": "O povo que andava na escuridão viu uma grande luz; para os que habitavam nas sombras da morte, uma luz resplandeceu. (Cf. Is 9,1)",
          "comunhao": "A vida, que estava no Pai, manifestou-se e apareceu a nós. (Cf. 1Jo 1,2)"
        },
        "leituras": [
          {
            "ordem": 1,
            "tipo": "leitura",
            "rotulo": "Primeira Leitura",
            "opcoes": [
              {
                "referencia": "1Jo 2, 29–3, 6",
                "titulo": "Leitura da Primeira Carta de São João",
                "texto": "Caríssimos: 29Já que sabeis que ele é justo, sabei também que todo aquele que pratica a justiça nasceu dele. 3, 1Vede que grande presente de amor o Pai nos deu: de sermos chamados filhos de Deus! E nós o somos! Se o mundo não nos conhece, é porque não conheceu o Pai. 2Caríssimos, desde já somos filhos de Deus, mas nem sequer se manifestou o que seremos! Sabemos que, quando Jesus se manifestar, seremos semelhantes a ele, porque o veremos tal como ele é. 3Todo o que espera nele, purifica-se a si mesmo, como também ele é puro. 4Todo o que comete pecado, comete também a iniquidade, porque o pecado é a iniquidade. 5Vós sabeis que ele se manifestou para tirar os pecados e que nele não há pecado. 6Todo aquele que peca mostra que não o viu, nem o conheceu."
              }
            ]
          },
          {
            "ordem": 2,
            "tipo": "salmo",
            "rotulo": "Salmo Responsorial",
            "opcoes": [
              {
                "referencia": "Sl 97",
                "refrao": "Os confins do universo contemplaram a salvação do nosso Deus.",
                "texto": "— Cantai ao Senhor Deus um canto novo, porque ele fez prodígios! Sua mão e seu braço forte e santo alcançaram-lhe a vitória.\n— Os confins do universo contemplaram a salvação do nosso Deus. Aclamai o Senhor Deus, ó terra inteira, alegrai-vos e exultai!\n— Cantai salmos ao Senhor ao som da harpa e da cítara suave! Aclamai, com os clarins e as trombetas, ao Senhor, o nosso Rei"
              }
            ]
          },
          {
            "ordem": 3,
            "tipo": "evangelho",
            "rotulo": "Evangelho",
            "opcoes": [
              {
                "referencia": "Jo 1, 29-34",
                "titulo": "Proclamação do Evangelho de Jesus Cristo ✠ segundo João",
                "texto": "29No dia seguinte, João viu Jesus aproximar-se dele e disse: “Eis o Cordeiro de Deus, que tira o pecado do mundo. 30Dele é que eu disse: Depois de mim vem um homem que passou à minha frente, porque existia antes de mim. 31Também eu não o conhecia, mas se eu vim batizar com água, foi para que ele fosse manifestado a Israel”.32E João deu testemunho, dizendo: “Eu vi o Espírito descer, como uma pomba do céu, e permanecer sobre ele. 2Também eu não o conhecia, mas aquele que me enviou a batizar com água me disse: ‘Aquele sobre quem vires o Espírito descer e permanecer, este é quem batiza com o Espírito Santo’. 34Eu vi e dou testemunho: Este é o Filho de Deus!”"
              }
            ]
          }
        ]
      },
      {
        "id": "santissimo-nome-de-jesus-memoria-facultativa",
        "liturgia": "Santíssimo Nome de Jesus. Memória Facultativa",
        "cor": "Branco",
        "principal": false,
        "oracoes": {
          "coleta": "Senhor, ao venerarmos o Santíssimo Nome de Jesus, concedei-nos. benigno, que saboreando nesta vida a sua doçura, sejamos repletos de felicidade eterna na pátria celeste. Por nosso Senhor Jesus Cristo, vosso Filho, gue é Deus, e convosco vive e reina, na unidade do Espírito Santo, por todos os séculos dos séculos.",
          "oferendas": "Ó Pai todo-poderoso, dignai-vos aceitar as nossas oferendas apresentadas em Nome de Jesus. Nele confiamos, na certeza de receber tudo o que pedirmos, como prometeu em sua imensa bondade. Por Cristo, nosso Senhor.",
          "comunhao": "Ó Pai, em vossa misericórdia, concedei-nos venerar dignamente, nestes sagrados mistérios, o Senhor Jesus pois quisestes que a seu Nome todo joelho se dobre e os seres humanos encontrem nele a salvação. Por Cristo, nosso Senhor.",
          "extras": []
        },
        "antifonas": {
          "entrada": "Ao nome de Jesus, todo joelho se dobre, no céu, na terra e nos abismos, e toda língua confesse, para a glória de Deus Pai, que Jesus Cristo é o Senhor! (Cf. Fl 2, 10-11)",
          "comunhao": "Não existe debaixo do céu outro nome dado à humanidade, pelo qual possamos ser salvos. (Cf. At 4, 12)"
        },
        "leituras": [
          {
            "ordem": 1,
            "tipo": "leitura",
            "rotulo": "Primeira Leitura",
            "opcoes": [
              {
                "referencia": "1Jo 2, 29–3, 6",
                "titulo": "Leitura da Primeira Carta de São João",
                "texto": "Caríssimos: 29Já que sabeis que ele é justo, sabei também que todo aquele que pratica a justiça nasceu dele. 3, 1Vede que grande presente de amor o Pai nos deu: de sermos chamados filhos de Deus! E nós o somos! Se o mundo não nos conhece, é porque não conheceu o Pai. 2Caríssimos, desde já somos filhos de Deus, mas nem sequer se manifestou o que seremos! Sabemos que, quando Jesus se manifestar, seremos semelhantes a ele, porque o veremos tal como ele é. 3Todo o que espera nele, purifica-se a si mesmo, como também ele é puro. 4Todo o que comete pecado, comete também a iniquidade, porque o pecado é a iniquidade. 5Vós sabeis que ele se manifestou para tirar os pecados e que nele não há pecado. 6Todo aquele que peca mostra que não o viu, nem o conheceu."
              }
            ]
          },
          {
            "ordem": 2,
            "tipo": "salmo",
            "rotulo": "Salmo Responsorial",
            "opcoes": [
              {
                "referencia": "Sl 97",
                "refrao": "Os confins do universo contemplaram a salvação do nosso Deus.",
                "texto": "— Cantai ao Senhor Deus um canto novo, porque ele fez prodígios! Sua mão e seu braço forte e santo alcançaram-lhe a vitória.\n— Os confins do universo contemplaram a salvação do nosso Deus. Aclamai o Senhor Deus, ó terra inteira, alegrai-vos e exultai!\n— Cantai salmos ao Senhor ao som da harpa e da cítara suave! Aclamai, com os clarins e as trombetas, ao Senhor, o nosso Rei"
              }
            ]
          },
          {
            "ordem": 3,
            "tipo": "evangelho",
            "rotulo": "Evangelho",
            "opcoes": [
              {
                "referencia": "Jo 1, 29-34",
                "titulo": "Proclamação do Evangelho de Jesus Cristo ✠ segundo João",
                "texto": "29No dia seguinte, João viu Jesus aproximar-se dele e disse: “Eis o Cordeiro de Deus, que tira o pecado do mundo. 30Dele é que eu disse: Depois de mim vem um homem que passou à minha frente, porque existia antes de mim. 31Também eu não o conhecia, mas se eu vim batizar com água, foi para que ele fosse manifestado a Israel”.32E João deu testemunho, dizendo: “Eu vi o Espírito descer, como uma pomba do céu, e permanecer sobre ele. 2Também eu não o conhecia, mas aquele que me enviou a batizar com água me disse: ‘Aquele sobre quem vires o Espírito descer e permanecer, este é quem batiza com o Espírito Santo’. 34Eu vi e dou testemunho: Este é o Filho de Deus!”"
              }
            ]
          }
        ]
      }
    ]
  }
```

---