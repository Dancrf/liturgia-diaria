
# Liturgia Diária

API que fornece as orações e leituras do dia da Santa Missa (liturgia dária).

🛑 **ATENÇÃO:**
*Infelizmente o serviço da railway.app no qual hospedava a aplicação deixou de fornecer um plano gratuito. Por isso, não tenho como manter a API até achar alguma alternativa. Se alguém tiver alguma sugestão, pode abrir uma issue!*

## Documentação da API

#### Para retornar a liturgia do dia

```http
  GET https://liturgia.up.railway.app/
```

Resultado:

```json
{
    "data": "23/04/2023",
    "liturgia": "3º Domingo de Páscoa",
    "cor": "Branco",
    "dia": "Ó Deus, que o vosso povo sempre exulte pela sua renovação espiritual, para que, tendo recuperado agora com alegria a condição de filhos de Deus, espere com plena confiança o dia da ressurreição. Por nosso Senhor Jesus Cristo, vosso Filho, na unidade do Espírito Santo.",
    "oferendas": "Acolhei, ó Deus, as oferendas da vossa Igreja em festa. Vós que sois a causa de tão grande júbilo, concedei-lhe também a eterna alegria. Por Cristo, nosso Senhor.",
    "comunhao": "Ó Deus, olhai com bondade o vosso povo e concedei aos que renovastes pelos vossos sacramentos a graça de chegar um dia à glória da ressurreição da carne. Por Cristo, nosso Senhor.",
    "primeiraLeitura": {
      "referencia": "At 2, 14. 22-33",
      "titulo": "Leitura dos Atos dos Apóstolos",
      "texto": "No dia de Pentecostes, 14Pedro de pé, junto com os onze apóstolos, levantou a voz e falou à multidão: 22“Homens de Israel, escutai estas palavras: Jesus de Nazaré foi um homem aprovado por Deus, junto de vós, pelos milagres, prodígios e sinais que Deus realizou, por meio dele, entre vós. Tudo isto vós bem o sabeis. 23Deus, em seu desígnio e previsão, determinou que Jesus fosse entregue pelas mãos dos ímpios, e vós o matastes, pregando-o numa cruz. 24Mas Deus ressuscitou a Jesus, libertando-o das angústias da morte, porque não era possível que ela o dominasse. 25Pois Davi dele diz: ‘Eu via sempre o Senhor diante de mim, pois está à minha direita para eu não vacilar. 26Alegrou-se por isso meu coração e exultou minha língua e até minha carne repousará na esperança. 27Porque não deixarás minha alma na região dos mortos nem permitirás que teu Santo experimente corrupção. 28Deste-me a conhecer os caminhos da vida e a tua presença me encherá de alegria’.,29Irmãos, seja-me permitido dizer com franqueza que o patriarca Davi morreu e foi sepultado e seu sepulcro está entre nós até hoje. 30Mas, sendo profeta, sabia que Deus lhe jurara solenemente que um de seus descendentes ocuparia o trono.,31É, portanto, a ressurreição de Cristo que previu e anunciou com as palavras: ‘Ele não foi abandonado na região dos mortos e sua carne não conheceu a corrupção’. 32Com efeito, Deus ressuscitou este mesmo Jesus e disto todos nós somos testemunhas. 33E agora, exaltado pela direita de Deus, Jesus recebeu o Espírito Santo que fora prometido pelo Pai, e o derramou, como estais vendo e ouvindo”."
    },
    "segundaLeitura": {
      "referencia": "1Pd 1, 17-21",
      "titulo": "Leitura da Primeira Carta de São Pedro",
      "texto": "Caríssimos: 17Se invocais como Pai aquele que sem discriminação julga a cada um de acordo com as suas obras, vivei então respeitando a Deus durante o tempo de vossa migração neste mundo.,18Sabeis que fostes resgatados da vida fútil herdada de vossos pais, não por meio de coisas perecíveis, como a prata ou o ouro, 19mas pelo precioso sangue de Cristo, como de um cordeiro sem mancha nem defeito. 20Antes da criação do mundo, ele foi destinado para isso, e neste final dos tempos, ele apareceu, por amor de vós. 21Por ele é que alcançastes a fé em Deus. Deus o ressuscitou dos mortos e lhe deu a glória, e assim, a vossa fé e esperança estão em Deus."
    },
    "salmo": {
      "referencia": "Sl 15",
      "refrao": "Vós me ensinais vosso caminho para a vida; junto de vós felicidade sem limites!",
      "texto": "— Guardai-me, ó Deus, porque em vós me refugio! Digo ao Senhor: “Somente vós sois meu Senhor: nenhum bem eu posso achar fora de vós!” Ó Senhor, sois minha herança e minha taça, meu destino está seguro em vossas mãos! \n— Eu bendigo o Senhor, que me aconselha, e até de noite me adverte o coração. Tenho sempre o Senhor ante meus olhos, pois se o tenho a meu lado não vacilo. \n— Eis por que meu coração está em festa, minha alma rejubila de alegria, e até meu corpo no repouso está tranquilo; pois não haveis de me deixar entregue à morte, nem vosso amigo conhecer a corrupção. \n— Vós me ensinais vosso caminho para a vida; junto a vós, felicidade sem limites, delícia eterna e alegria ao vosso lado"
    },
    "evangelho": {
      "referencia": "Lc 24, 13-35",
      "titulo": "Proclamação do Evangelho de Jesus Cristo ✠ segundo Lucas",
      "texto": "Naquele mesmo dia, o primeiro da semana, dois dos discípulos de Jesus iam para um povoado, chamado Emaús, distante onze quilômetros de Jerusalém. 14Conversavam sobre todas as coisas que tinham acontecido. 15Enquanto conversavam e discutiam, o próprio Jesus se aproximou e começou a caminhar com eles. 16Os discípulos, porém, estavam como que cegos, e não o reconheceram. 17Então Jesus perguntou: “O que ides conversando pelo caminho?” Eles pararam, com o rosto triste, 18e um deles, chamado Cléofas, lhe disse: “Tu és o único peregrino em Jerusalém que não sabe o que lá aconteceu nestes últimos dias?”19Ele perguntou: “O que foi?” Os discípulos responderam: “O que aconteceu com Jesus, o Nazareno, que foi um profeta poderoso em obras e palavras, diante de Deus e diante de todo o povo. 20Nossos sumos sacerdotes e nossos chefes o entregaram para ser condenado à morte e o crucificaram. 21Nós esperávamos que ele fosse libertar Israel, mas, apesar de tudo isso, já faz três dias que todas essas coisas aconteceram! 22É verdade que algumas mulheres do nosso grupo nos deram um susto. Elas foram de madrugada ao túmulo 23e não encontraram o corpo dele. Então voltaram, dizendo que tinham visto anjos e que estes afirmaram que Jesus está vivo. 24Alguns dos nossos foram ao túmulo e encontraram as coisas como as mulheres tinham dito. A ele, porém, ninguém o viu”.25Então Jesus lhes disse: “Como sois sem inteligência e lentos para crer em tudo o que os profetas falaram! 26Será que o Cristo não devia sofrer tudo isso para entrar na sua glória?”27E, começando por Moisés e passando pelos Profetas, explicava aos discípulos todas as passagens da Escritura que falavam a respeito dele. 28Quando chegaram perto do povoado para onde iam, Jesus fez de conta que ia mais adiante. 29Eles, porém, insistiram com Jesus, dizendo: “Fica conosco, pois já é tarde e a noite vem chegando!” Jesus entrou para ficar com eles. 30Quando se sentou à mesa com eles, tomou o pão, abençoou-o, partiu-o e lhes distribuía. 31Nisso os olhos dos discípulos se abriram e eles reconheceram Jesus. Jesus, porém, desapareceu da frente deles. 32Então um disse ao outro: “Não estava ardendo o nosso coração quando ele nos falava pelo caminho, e nos explicava as Escrituras?” 33Naquela mesma hora, eles se levantaram e voltaram para Jerusalém onde encontraram os Onze reunidos com os outros. 34E estes confirmaram: “Realmente, o Senhor ressuscitou e apareceu a Simão!” 35Então os dois contaram o que tinha acontecido no caminho, e como tinham reconhecido Jesus ao partir o pão."
    }
  },
```

#

#### Para retornar a liturgia de um dia específico através de query

```http
  GET https://liturgia.up.railway.app/?dia=[dia]&mes=[mes]
```

| Query   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `dia` | `string` | **Obrigatório**. O dia da liturgia |
| `mes` | `string` | O mês que deseja *(por padrão o mês atual)* |

Exemplo:

```http
https://liturgia.up.railway.app/?dia=20&mes=03
```
Retornará a Liturgia do dia 20 do mês de março.


#


#### Para retornar a liturgia de um dia específico através de parâmetros

```http
  GET https://liturgia.up.railway.app/${dia}-${mes}
```

| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `dia` | `string` | **Obrigatório**. O dia da liturgia |
| `mes` | `string` | O mês que deseja *(por padrão o mês atual)* |

Exemplo:

```http
https://liturgia.up.railway.app/20-03
```
Também retornará a Liturgia do dia 20 do mês de março.

## Resultado:

![Resultado](https://raw.githubusercontent.com/Dancrf/liturgia-diaria/main/resultado.jpg)


## Últimas atualizações

Foram corrigidos erros que impediam a visualização da Liturgia do dia, bem como a atualização dos dados e refatoramento do código.
