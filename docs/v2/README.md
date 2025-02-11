# Documentação da V2


### Principais mudanças:

  - Nesta versão, as orações e leituras foram agrupadas e cada leitura é retornada como um Array. Essa mudança foi implementada para suportar dias com mais de uma leitura ou evangelho (como na Vigília Pascal).
  - A Oração do Dia agora é chamada de Coleta.
  - Orações extras como a Benção do Fogo no Sábado Santo estarão na propriedade "extras" que retorna um Array.


#### Para retornar a liturgia do dia

```
  GET https://liturgia.up.railway.app/v2/
```


Resultado:

```json
{
        "data": "12/04/2025",
        "liturgia": "Sábado da 5ª Semana da Quaresma",
        "cor": "Roxo",
        "oracoes": {
            "coleta": "Deus, que fizestes de todos os renascidos em Cristo uma nação santa e um sacerdócio régio, concedei-nos a vontade e a força de fazer o que ordenais, para que o povo chamado à eternidade seja concorde na fé e justo nas ações. Por nosso Senhor Jesus Cristo, vosso Filho, que é Deus, e convosco vive e reina, na unidade do Espírito Santo, por todos os séculos dos séculos.",
            "oferendas": "Acolhei, Senhor nós vos pedimos, as oferendas do nosso jejum; elas nos tornem dignos da graça do vosso perdão e nos conduzam às promessas eternas. Por Cristo, nosso Senhor.",
            "comunhao": "Senhor, nós vos pedimos humildemente: assim como nos alimentais com o sacramento do Corpo e Sangue de Cristo, dai-nos participar da natureza divina. Por Cristo, nosso Senhor.",
            "extras:" []
        },
        "leituras": {
            "primeiraLeitura": [
                {
                    "referencia": "Ez 37, 21-28",
                    "titulo": "Leitura da Profecia de Ezequiel",
                    "texto": "21Assim diz o Senhor Deus: “Eu mesmo vou tomar os israelitas do meio das nações para onde foram, vou recolhê-los de toda parte e reconduzi-los para a sua terra. 22Farei deles uma nação única no país, nos montes de Israel, e apenas um rei reinará sobre todos eles. Nunca mais formarão duas nações, nem tornarão a dividir-se em dois reinos. 23Não se mancharão mais com os seus ídolos e nunca mais cometerão infames abominações. Eu os libertarei de todo o pecado que cometeram em sua infidelidade, e os purificarei. Eles serão o meu povo e eu serei o seu Deus. 24Meu servo Davi reinará sobre eles, e haverá para todos eles um único pastor. Viverão segundo meus preceitos e guardarão minhas leis, pondo-as em prática. 25Habitarão no país que dei a meu servo Jacó, onde moraram vossos pais; ali habitarão para sempre, também eles, com seus filhos e netos, e o meu servo Davi será o seu príncipe para sempre. 26Farei com eles uma aliança de paz, será uma aliança eterna. Eu os estabelecerei e multiplicarei, e no meio deles porei meu santuário para sempre. 27Minha morada estará junto deles. Eu serei o seu Deus e eles serão o meu povo. 28Assim as nações saberão que eu, o Senhor, santifico Israel, por estar o meu santuário no meio deles para sempre”."
                }
            ],
            "salmo": [
                {
                "referencia": "Jr 31, 10-13",
                "refrao": "O Senhor nos guardará qual pastor a seu rebanho.",
                "texto": "— Ouvi, nações, a palavra do Senhor e anunciai-a nas ilhas mais distantes: “Quem dispersou Israel, vai congregá-lo, e o guardará qual pastor a seu rebanho!” \n— Pois, na verdade, o Senhor remiu Jacó e o libertou do poder do prepotente. Voltarão para o monte de Sião, entre brados e cantos de alegria afluirão para as bênçãos do Senhor: \n— Então a virgem dançará alegremente, também o jovem e o velho exultarão; mudarei em alegria o seu luto, serei consolo e conforto após a guerra."
                },
            ],
            "segundaLeitura": [],
            "evangelho": [
                {
                    "referencia": "Jo 11, 45-56",
                    "titulo": "Proclamação do Evangelho de Jesus Cristo ✠ segundo João",
                    "texto": "Naquele tempo, 45muitos dos judeus que tinham ido à casa de Maria e viram o que Jesus fizera, creram nele. 46Alguns, porém, foram ter com os fariseus e contaram o que Jesus tinha feito. 47Então os sumos sacerdotes e os fariseus reuniram o Conselho e disseram: “O que faremos? Este homem realiza muitos sinais. 48Se deixamos que ele continue assim, todos vão acreditar nele, e virão os romanos e destruirão o nosso Lugar Santo e a nossa nação”.\n49Um deles, chamado Caifás, sumo sacerdote em função naquele ano, disse: “Vós não entendeis nada. 50Não percebeis que é melhor um só morrer pelo povo do que perecer a nação inteira?” 51Caifás não falou isso por si mesmo. Sendo sumo sacerdote em função naquele ano, profetizou que Jesus iria morrer pela nação. 52E não só pela nação, mas também para reunir os filhos de Deus dispersos. 53A partir desse dia, as autoridades judaicas tomaram a decisão de matar Jesus.\n54Por isso, Jesus não andava mais em público no meio dos judeus. Retirou-se para uma região perto do deserto, para a cidade chamada Efraim. Ali permaneceu com os seus discípulos. 55A Páscoa dos judeus estava próxima. Muita gente do campo tinha subido a Jerusalém para se purificar antes da Páscoa. 56Procuravam Jesus e, ao reunirem-se no Templo, comentavam entre si: “O que vos parece? Será que ele não vem para a festa?”"
                }
            ]
        },
        "antifonas": {
            "entrada": "Senhor, não afasteis de mim o vosso auxílio; olhai para mim em minha defesa, pois sou um verme e não um homem, vergonha dos homens e desprezo do povo. (Cf. Sl 21, 20. 7)",
            "comunhao": "O Cristo foi entregue para congregar na unidade os filhos de Deus, que estavam dispersos. (Cf. Jo 11, 52)"
        }
    }
```

Exemplo para orações extras:
```json
            "extras": [
                {
                    "titulo": "Benção do fogo",
                    "texto": "Ó Deus, que pelo vosso Filho trouxestes o clarão da vossa luz àqueles que creem, santificai ✠ este fogo novo. Concedei que a festa da Páscoa acenda em nós tal desejo do céu, que possamos chegar purificados à festa da luz eterna. Por Cristo, nosso Senhor."
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
  GET https://liturgia.up.railway.app/v2/?dia=[dia]&mes=[mes]
```

| Query   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `dia` | `string` | **Obrigatório**. O dia da liturgia |
| `mes` | `string` | O mês que deseja *(por padrão o mês atual)* |
| `ano` | `string` | O ano que deseja *(por padrão o ano atual)* |

Exemplo:

```
https://liturgia.up.railway.app/v2/?dia=20&mes=03
```
Retornará a Liturgia do dia 20 do mês de março deste ano.



```
https://liturgia.up.railway.app/v2/?dia=20&mes=03&ano=2024
```
Retornará a Liturgia do dia 20 do mês de março de 2024.

#


#### Para retornar a liturgia de um dia específico através de parâmetros

```
  GET https://liturgia.up.railway.app/v2/{dia}-{mes}
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

#

### Caso a liturgia não seja encontrada

Quando não houver liturgia disponível para a data informada, a API retornará um erro com status 404 e um JSON informando que a liturgia não foi encontrada. Por exemplo:

```json
{
  "erro": "Não encontramos nenhuma liturgia para esta data",
  "data": "01/02/2080"
}
```
