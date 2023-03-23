
# Liturgia Diária

API que fornece as orações e leituras do dia da Santa Missa (liturgia dária).



## Documentação da API

#### Para retornar a liturgia do dia

```http
  GET https://liturgia.up.railway.app/
```

Resultado:

```json
{
  "data": "23/03/2023",
  "liturgia": "5ª feira da 4ª Semana da Quaresma",
  "cor": "Roxo",
  "dia": "Nós vos pedimos, ó Deus de bondade, que, corrigidos pela penitência e renovados pelas boas obras, possamos perseverar nos vossos mandamentos e chegar purificados às festas pascais. Por Nosso Senhor Jesus Cristo, Vosso Filho, na unidade do Espírito Santo.",
  "oferendas": "Concedei, ó Deus todo-poderoso, que as oferendas deste sacrifício protejam nossa fraqueza, livrando-nos de todo mal. Por Cristo, nosso Senhor.",
  "comunhao": "Fazei, ó Deus, que esta comunhão nos purifique e liberte de toda culpa. Se a consciência do pecado nos aflige, o socorro celeste nos alegre. Por Cristo, nosso Senhor.",
  "primeiraLeitura": {
    "titulo": "Leitura do Livro do Êxodo",
    "texto": "Naqueles dias, 7o Senhor falou a Moisés: “Vai, desce, pois corrompeu-se o teu povo, que tiraste da terra do Egito. 8Bem depressa desviaram-se do caminho que lhes prescrevi. Fizeram para si um bezerro de metal fundido, inclinaram-se em adoração diante dele e ofereceram-lhe sacrifícios, dizendo: ‘Estes são os teus deuses, Israel, que te fizeram sair do Egito!’”,9E o Senhor disse ainda a Moisés: “Vejo que este é um povo de cabeça dura. 10Deixa que minha cólera se inflame contra eles e que eu os extermine. Mas de ti farei uma grande nação”. 11Moisés, porém, suplicava ao Senhor seu Deus, dizendo: “Por que, ó Senhor, se inflama a tua cólera contra o teu povo, que fizeste sair do Egito com grande poder e mão forte? 12Não permitas, te peço, que os egípcios digam: ‘Foi com má intenção que ele os tirou, para fazê-los perecer nas montanhas e exterminá-los da face da terra’. Aplaque-se a tua ira e perdoa a iniquidade do teu povo.,13Lembra-te de teus servos Abraão, Isaac e Israel, com os quais te comprometeste por juramento, dizendo: ‘Tornarei os vossos descendentes tão numerosos como as estrelas do céu; e toda esta terra de que vos falei, eu a darei aos vossos descendentes como herança para sempre”’. 14E o Senhor desistiu do mal que havia ameaçado fazer ao seu povo."
  },
  "segundaLeitura": "Não há segunda leitura hoje!",
  "salmo": "Lembrai-vos de nós, ó Senhor, segundo o amor para com vosso povo!\n— Construíram um bezerro no Horeb e adoraram uma estátua de metal; eles trocaram o seu Deus, que é sua glória, pela imagem de um boi que come feno. \n— Esqueceram-se do Deus que os salvara, que fizera maravilhas no Egito; no país de Cam fez tantas obras admiráveis, no Mar Vermelho, tantas coisas assombrosas. \n— Até pensava em acabar com sua raça, se não tivesse Moisés, o seu eleito, interposto, intercedendo junto a ele, para impedir que sua ira os destruísse. ",
  "evangelho": {
    "titulo": "Proclamação do Evangelho de Jesus Cristo ✠ segundo João",
    "texto": "Naquele tempo, disse Jesus aos judeus: 31“Se eu der testemunho de mim mesmo, meu testemunho não vale. 32Mas há um outro que dá testemunho de mim, e eu sei que o testemunho que ele dá de mim é verdadeiro. 33Vós mandastes mensageiros a João, e ele deu testemunho da verdade. 34Eu, porém, não dependo do testemunho de um ser humano. Mas falo assim para a vossa salvação. 35João era uma lâmpada que estava acesa e a brilhar, e vós com prazer vos alegrastes por um tempo com a sua luz.36Mas eu tenho um testemunho maior que o de João; as obras que o Pai me concedeu realizar. As obras que eu faço dão testemunho de mim, mostrando que o Pai me enviou. 37E também o Pai que me enviou dá testemunho a meu favor. Vós nunca ouvistes sua voz, nem vistes sua face, 38e sua palavra não encontrou morada em vós, pois não acreditais naquele que ele enviou. 39Vós examinais as Escrituras, pensando que nelas possuís a vida eterna. No entanto, as Escrituras dão testemunho de mim, 40mas não quereis vir a mim para ter a vida eterna! 41Eu não recebo a glória que vem dos homens. 42Mas eu sei que não tendes em vós o amor de Deus. 43Eu vim em nome do meu Pai, e vós não me recebeis. Mas, se um outro viesse em seu próprio nome, a este vós o receberíeis.44Como podereis acreditar, vós que recebeis glória uns dos outros e não buscais a glória que vem do único Deus? 45Não penseis que eu vos acusarei diante do Pai. Há alguém que vos acusa: Moisés, no qual colocais a vossa esperança. 46Se acreditásseis em Moisés, também acreditaríeis em mim, pois foi a respeito de mim que ele escreveu. 47Mas se não acreditais nos seus escritos, como acreditareis então nas minhas palavras?”"
  }
}
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
  GET /${dia}-${mes}
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

![Resultado](https://raw.githubusercontent.com/Dancrf/liturgia-diaria/main/resultado.png)


## Últimas atualizações

Foram corrigidos erros que impediam a visualização da Liturgia do dia, bem como a atualização dos dados e refatoramento do código.
