 Documentação da V1

#### Para retornar a liturgia do dia

```
  GET https://liturgia.up.railway.app/
```

Resultado:

```json
{
  "data": "11/08/2024",
  "liturgia": "19º Domingo do Tempo Comum",
  "cor": "Verde",
  "dia": "Deus eterno e todo-poderoso, a quem, inspirados pelo Espírito Santo, ousamos chamar de Pai, fazei crescer em nossos corações o espírito de adoção filial, para merecermos entrar um dia na posse da herança prometida. Por nosso Senhor Jesus Cristo, vosso Filho, que é Deus, e convosco vive e reina, na unidade do Espírito Santo, por todos os séculos dos séculos.",
  "oferendas": "Senhor, acolhei com misericórdia os dons que concedestes à vossa Igreja e ela agora vos apresenta. Transformai-os por vosso poder em sacramento da nossa salvação. Por Cristo, nosso Senhor.",
  "comunhao": "Ó Senhor, a comunhão do vosso sacramento, que acabamos de receber, nos salve e nos confirme na luz da vossa verdade. Por Cristo, nosso Senhor.",
  "primeiraLeitura": {
    "referencia": "1Rs 19, 4-8",
    "titulo": "Leitura do Primeiro Livro dos Reis",
    "texto": "Naqueles dias, 4Elias entrou deserto adentro e caminhou o dia todo. Sentou-se finalmente debaixo de um junípero e pediu para si a morte, dizendo: “Agora basta, Senhor! Tira a minha vida, pois não sou melhor que meus pais”. 5E, deitando-se no chão, adormeceu à sombra do junípero. De repente, um anjo tocou-o e disse: “Levanta-te e come!”,6Ele abriu os olhos e viu junto à sua cabeça um pão assado debaixo da cinza e um jarro de água. Comeu, bebeu e tornou a dormir. 7Mas o anjo do Senhor veio pela segunda vez, tocou-o e disse: “Levanta-te e come! Ainda tens um caminho longo a percorrer”. 8Elias levantou-se, comeu e bebeu, e, com a força desse alimento, andou quarenta dias e quarenta noites, até chegar ao Horeb, o monte de Deus."
  },
  "segundaLeitura": { // Caso não haja segunda Leitura (dia de semana), retornará a string "Não há segunda leitura hoje!"
    "referencia": "Ef 4, 30-5, 2",
    "titulo": "Leitura da Carta de São Paulo aos Efésios",
    "texto": "Irmãos: 30Não contristeis o Espírito Santo com o qual Deus vos marcou como com um selo para o dia da libertação. 31Toda a amargura, irritação, cólera, gritaria, injúrias, tudo isso deve desaparecer do meio de vós, como toda espécie de maldade. 32Sede bons uns para com os outros, sede compassivos; perdoai-vos mutuamente, como Deus vos perdoou por meio de Cristo. 5, 1Sede imitadores de Deus, como filhos que ele ama. 2Vivei no amor, como Cristo nos amou e se entregou a si mesmo a Deus por nós, em oblação e sacrifício de suave odor."
  },
  "salmo": {
    "referencia": "Sl 33",
    "refrao": "Provai e vede quão suave é o Senhor!",
    "texto": "— Bendirei o Senhor Deus em todo o tempo, seu louvor estará sempre em minha boca. Minha alma se gloria no Senhor; que ouçam os humildes e se alegrem! \n— Comigo engrandecei ao Senhor Deus, exaltemos todos juntos o seu nome! Todas as vezes que o busquei, ele me ouviu, e de todos os temores me livrou. \n— Contemplai a sua face e alegrai-vos, e vosso rosto não se cubra de vergonha! Este infeliz gritou a Deus, e foi ouvido, e o Senhor o libertou de toda angústia. \n— O anjo do Senhor vem acampar ao redor dos que o temem, e os salva. Provai e vede quão suave é o Senhor! Feliz o homem que tem nele o seu refúgio"
  },
  "evangelho": {
    "referencia": "Jo 6, 41-51",
    "titulo": "Proclamação do Evangelho de Jesus Cristo ✠ segundo João",
    "texto": "Naquele tempo, 41os judeus começaram a murmurar a respeito de Jesus, porque havia dito: “Eu sou o pão que desceu do céu”. 42Eles comentavam: “Não é este Jesus, o filho de José? Não conhecemos seu pai e sua mãe? Como então pode dizer que desceu do céu?”43Jesus respondeu: “Não murmureis entre vós. 44Ninguém pode vir a mim, se o Pai que me enviou não o atrai. E eu o ressuscitarei no último dia. 45Está escrito nos Profetas: ‘Todos serão discípulos de Deus’. Ora, todo aquele que escutou o Pai e por ele foi instruído, vem a mim. 46Não que alguém já tenha visto o Pai. Só aquele que vem de junto de Deus viu o Pai. 47Em verdade, em verdade vos digo, quem crê, possui a vida eterna.48Eu sou o pão da vida. 49Os vossos pais comeram o maná no deserto e, no entanto, morreram. 50Eis aqui o pão que desce do céu: quem dele comer, nunca morrerá. 51Eu sou o pão vivo descido do céu. Quem comer deste pão viverá eternamente. E o pão que eu darei é a minha carne dada para a vida do mundo”."
  },
  "antifonas": {
    "entrada": "Lembrai-vos, Senhor, da vossa aliança, e nunca esqueçais a vida dos vossos pobres. Levantai-vos Senhor, e julgai vossa causa, e não fecheis o ouvido ao clamor dos que vos procuram. (Cf. Sl 73, 20. 19. 22. 23)",
    "comunhao": "Glorifica o Senhor, Jerusalém, ele te dá como alimento a flor do trigo. (Cf. SI 147, 12. 14)"
  }
}
```

A propriedade cor pode retornar as seguintes strings:
 - Verde
 - Vermelho
 - Roxo
 - Rosa
 - Branco


#

#### Para retornar a liturgia de um dia específico através de query

```
  GET https://liturgia.up.railway.app/?dia=[dia]&mes=[mes]
```

| Query   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `dia` | `string` | **Obrigatório**. O dia da liturgia |
| `mes` | `string` | O mês que deseja *(por padrão o mês atual)* |
| `ano` | `string` | O ano que deseja *(por padrão o ano atual)* |

Exemplo:

```
https://liturgia.up.railway.app/?dia=20&mes=03
```
Retornará a Liturgia do dia 20 do mês de março deste ano.

---

```
https://liturgia.up.railway.app/?dia=20&mes=03&ano=2024
```
Retornará a Liturgia do dia 20 do mês de março de 2024.

#


#### Para retornar a liturgia de um dia específico através de parâmetros

```
  GET https://liturgia.up.railway.app/{dia}-{mes}
```

| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `dia` | `string` | **Obrigatório**. O dia da liturgia |
| `mes` | `string` | O mês que deseja *(por padrão o mês atual)* |
| `ano` | `string` | O ano que deseja *(por padrão o ano atual)* |

Exemplo:

```
https://liturgia.up.railway.app/20-03
```
Também retornará a Liturgia do dia 20 do mês de março.
