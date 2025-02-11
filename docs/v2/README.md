# Documentação da V2


### Principais mudanças:

  - Nesta versão, as orações e leituras foram agrupadas e cada leitura é retornada como um Array. Essa mudança foi implementada para suportar dias com mais de uma possibilidade para a leitura ou evangelho ou quando há mais leituras do que apenas a primeira e a segunda, como na Vigília Pascal.
  - A Oração do Dia agora é chamada de Coleta.
  - Orações extras como a Benção do Fogo no Sábado Santo estarão na propriedade "extras" que retorna um Array. O mesmo serve para as leituras.


#### Para retornar a liturgia do dia

```
  GET https://liturgia.up.railway.app/v2/
```


Resultado:

```json
// http://liturgia.up.railway.app/v2/?dia=19&mes=04

{
  "data": "19/04/2025",
  "liturgia": "Sábado Santo - Vigília Pascal",
  "cor": "Branco",
  "oracoes": {
    "coleta": "Não há Oração da Coleta. A Liturgia da Palavra inicia-se com estas palavras:\nMeus irmãos e minhas irmãs, tendo iniciado solenemente esta vigília, ouçamos no recolhimento desta noite a Palavra de Deus. Vejamos como ele salvou outrora o seu povo e nestes últimos tempos enviou seu Filho como Redentor. Peçamos que o nosso Deus leve à plenitude a salvação inaugurada na Páscoa.",
    "oferendas": "Acolhei, Senhor, com estas oferenda, as preces do vosso povo e fazei que o sacrifício inaugurado no mistério pascal nos sirva, por vossa graça, de remédio para a vida eterna. Por Cristo, nosso Senhor.",
    "comunhao": "Derramai em nós, Senhor, o Espírito do vosso amor, e fazei que vivam concordes na piedade os que saciastes com os sacramentos pascais. Por Cristo, nosso Senhor.",
    "extras": [
      {
        "titulo": "Benção do fogo",
        "texto": "Ó Deus, que pelo vosso Filho trouxestes o clarão da vossa luz àqueles que creem, santificai ✠ este fogo novo. Concedei que a festa da Páscoa acenda em nós tal desejo do céu, que possamos chegar purificados à festa da luz eterna. Por Cristo, nosso Senhor."
      },
      {
        "titulo": "Depois da primeira leitura",
        "texto": "Deus eterno e todo-poderoso, que dispondes de modo admirável todas as vossas obras, dai aos que foram resgatados pelo vosso Filho a graça de compreender que o sacrifício do Cristo, nossa Páscoa, na plenitude dos tempos, ultrapassa em grandeza a criação do mundo, realizada no princípio. Por Cristo, nosso Senhor."
      },
      {
        "titulo": "Depois da segunda leitura",
        "texto": "Ó Deus, Pai de todos os fiéis, vós multiplicais por toda a terra os filhos da vossa promessa derramando sobre eles a graça da adoção e, pelo sacramento pascal, tornais o vosso servo Abraão pai de todas as nações, como lhe tínheis prometido. Concedei, portanto, a todos os povos a graça de responder ao vosso chamado. Por Cristo, nosso Senhor."
      },
      {
        "titulo": "Depois da terceira leitura",
        "texto": "Ó Deus, vemos brilhar ainda em nossos dias as vossas antigas maravilhas. Como manifestastes outrora o vosso poder, libertando um só povo da perseguição do Faraó, realizais agora a salvação de todas as nações nas águas do batismo. Concedei a todos os povos da terra tornarem-se filhos de Abraão e participantes da dignidade do povo eleito. Por Cristo, nosso Senhor."
      },
      {
        "titulo": "Depois da quarta leitura",
        "texto": "Deus eterno e todo-poderoso, para a glória do vosso nome,multiplicai o que prometestes aos nossos pais por causa da sua fé e aumentai pela adoção divina os filhos da promessa. Possa a Igreja reconhecer que já se realizou em grande parte a promessa da qual os santos Patriarcas jamais duvidaram. Por Cristo, nosso Senhor."
      },
      {
        "titulo": "Depois da quinta leitura",
        "texto": "Deus eterno e todo-poderoso, única esperança do mundo, pela voz dos profetas anunciastes os mistérios que hoje se realizam. Aumentai benigno o fervor do vosso povo, pois nenhum dos vossos filhos poderá progredir na virtude sem o auxílio da vossa graça. Por Cristo, nosso Senhor."
      },
      {
        "titulo": "Depois da sexta leitura",
        "texto": "Ó Deus, que fazeis a vossa Igreja crescer sempre mais chamando para ela todos os povos, guardai sob a vossa contínua proteção os que purificais na água do Batismo. Por Cristo, nosso Senhor."
      },
      {
        "titulo": "Depois da sétima leitura",
        "texto": "Ó Deus, força imutável e luz que não se apaga, olhai com bondade o mistério de toda a vossa Igreja e conduzi pelos caminhos da paz a obra da salvação, que concebestes desde toda a eternidade. O mundo todo veja e experimente que se levanta o que estava caído, que o velho se torna novo e que tudo volta à integridade primitiva, por Cristo, princípio de todas as coisas. Ele, que vive e reina pelos séculos dos séculos."
      }
    ]
  },
  "leituras": {
    "primeiraLeitura": [
      { // Duas formas para a 1ª Leitura
        "referencia": "Gn 1, 1-2, 2 (Forma Longa)",
        "titulo": "Leitura do Livro do Gênesis",
        "texto": "No princípio Deus criou o céu e a terra. 2A terra estava deserta e vazia, as trevas cobriam a face do abismo e o Espírito de Deus pairava sobre as águas. 3Deus disse: “Faça-se a luz!” E a luz se fez. 4Deus viu que a luz era boa e separou a luz das trevas. 5E à luz Deus chamou “dia” e às trevas, “noite”. Houve uma tarde e uma manhã: primeiro dia. 6Deus disse: “Faça-se um firmamento entre as águas, separando umas das outras”. 7E Deus fez o firmamento, e separou as águas que estavam embaixo das que estavam em cima do firmamento. E assim se fez. 8Ao firmamento Deus chamou “céu”. Houve uma tarde e uma manhã: segundo dia. 9Deus disse: “Juntem-se as águas que estão debaixo do céu num só lugar e apareça o solo enxuto!” E assim se fez. 10Ao solo enxuto Deus chamou “terra” e ao ajuntamento das águas, “mar”. E Deus viu que era bom. 11Deus disse: “A terra faça brotar vegetação e plantas que deem semente, e árvores frutíferas que deem fruto segundo a sua espécie, que tenham nele a sua semente sobre a terra”. E assim se fez. 12E a terra produziu vegetação e plantas que trazem semente segundo a sua espécie, e árvores que dão fruto tendo nele a semente da sua espécie. E Deus viu que era bom. 13Houve uma tarde e uma manhã: terceiro dia. 14Deus disse: “Façam-se luzeiros no firmamento do céu, para separar o dia da noite. Que sirvam de sinais para marcar as festas, os dias e os anos, 15e que resplandeçam no firmamento do céu e iluminem a terra”. E assim se fez. 16Deus fez os dois grandes luzeiros: o luzeiro maior para presidir o dia, e o luzeiro menor para presidir à noite, e as estrelas. 17Deus colocou-os no firmamento do céu para alumiar a terra, 18para presidir ao dia e à noite e separar a luz das trevas. E Deus viu que era bom. 19E houve uma tarde e uma manhã: quarto dia. 20Deus disse: “Fervilhem as águas de seres animados de vida e voem pássaros sobre a terra, debaixo do firmamento do céu”. 21Deus criou os grandes monstros marinhos e todos os seres vivos que nadam, em multidão, nas águas, segundo as suas espécies, e todas as aves, segundo as suas espécies. E Deus viu que era bom. 22E Deus os abençoou, dizendo: “Sede fecundos e multiplicai-vos e enchei as águas do mar, e que as aves se multipliquem sobre a terra”. 23Houve uma tarde e uma manhã: quinto dia. 24Deus disse: “Produza a terra seres vivos segundo as suas espécies, animais domésticos, répteis e animais selvagens, segundo as suas espécies”. E assim se fez. 25Deus fez os animais selvagens, segundo as suas espécies, os animais domésticos, segundo as suas espécies e todos os répteis do solo, segundo as suas espécies. E Deus viu que era bom. 26Deus disse: “Façamos o homem à nossa imagem e segundo a nossa semelhança, para que domine sobre os peixes do mar, sobre as aves do céu, sobre os animais de toda a terra, e sobre todos os répteis que rastejam sobre a terra”. 27E Deus criou o homem à sua imagem, à imagem de Deus ele o criou: homem e mulher os criou. 28E Deus os abençoou e lhes disse: “Sede fecundos e multiplicai-vos, enchei a terra e submetei-a! Dominai sobre os peixes do mar, sobre os pássaros do céu e sobre todos os animais que se movem sobre a terra”. 29E Deus disse: “Eis que vos entrego todas as plantas que dão semente sobre a terra, e todas as árvores que produzem fruto com sua semente, para vos servirem de alimento. 30E a todos os animais da terra, e a todas as aves do céu, e a tudo o que rasteja sobre a terra e que é animado de vida, eu dou todos os vegetais para alimento”. E assim se fez. 31E Deus viu tudo quanto havia feito, e eis que tudo era muito bom. Houve uma tarde e uma manhã: sexto dia. 2, 1E assim foram concluídos o céu e a terra com todo o seu exército. 2No sétimo dia, Deus considerou acabada toda a obra que tinha feito; e no sétimo dia descansou de toda a obra que fizera."
      },
      {
        "referencia": "Gn 1, 1. 26-31a (Forma Breve)",
        "titulo": "Leitura do Livro do Gênesis",
        "texto": "No princípio, Deus criou o céu e a terra. 26Deus disse: “Façamos o homem à nossa imagem e segundo a nossa semelhança, para que domine sobre os peixes do mar, sobre as aves do céu, sobre os animais de toda a terra, e sobre todos os répteis que rastejam sobre a terra”. 27E Deus criou o homem à sua imagem, à imagem de Deus ele o criou: homem e mulher os criou. 28E Deus os abençoou e lhes disse: “Sede fecundos e multiplicai-vos, enchei a terra e submetei-a! Dominai sobre os peixes do mar, sobre os pássaros do céu e sobre todos os animais que se movem sobre a terra”. 29E Deus disse: “Eis que vos entrego todas as plantas que dão semente sobre a terra, e todas as árvores que produzem fruto com sua semente, para vos servirem de alimento. 30E a todos os animais da terra, e a todas as aves do céu, e a tudo o que rasteja sobre a terra e que é animado de vida, eu dou todos os vegetais para alimento”. E assim se fez. 31E Deus viu tudo quanto havia feito, e eis que tudo era muito bom. Houve uma tarde e uma manhã: sexto dia."
      }
    ],
    "salmo": [
      {
        "referencia": "Sl 103",
        "refrao": "Enviai o vosso Espírito, Senhor, e da terra toda a face renovai.",
        "texto": "— Bendize, ó minha alma, ao Senhor! Ó meu Deus e meu Senhor, como sois grande! De majestade e esplendor vos revestis e de luz vos envolveis como num manto.\n— A terra vós firmastes em suas bases, ficará firme pelos séculos sem fim; os mares a cobriam como um manto, e as águas envolviam as montanhas.\n— Fazeis brotar em meio aos vales as nascentes que passam serpeando entre as montanhas; às suas margens vêm morar os passarinhos, entre os ramos eles erguem o seu canto.\n— De vossa casa as montanhas irrigais, com vossos frutos saciais a terra inteira; fazeis crescer os verdes pastos para o gado e as plantas que são úteis para o homem.\n— Quão numerosas, ó Senhor, são vossas obras, e que sabedoria em todas elas! Encheu-se a terra com as vossas criaturas! Bendize, ó minha alma, ao Senhor!"
      },
      {
        "referencia": "Ex 15, 1-6. 17-18",
        "refrao": "Cantemos ao Senhor que fez brilhar a sua glória!",
        "texto": "— Ao Senhor quero cantar, pois fez brilhar a sua glória: precipitou no mar Vermelho o cavalo e o cavaleiro! O Senhor é minha força, é a razão do meu cantar, pois foi ele neste dia para mim libertação!\n— Ele é meu Deus e o louvarei, Deus de meu pai, e o honrarei. O Senhor é um Deus guerreiro; o seu nome é “Onipotente”: os soldados e os carros do Faraó jogou no mar, seus melhores capitães afogou no mar Vermelho,\n— Afundaram como pedras e as ondas os cobriram. Ó Senhor, o vosso braço é duma força insuperável! Ó Senhor, o vosso braço esmigalhou os inimigos!\n— Vosso povo levareis e o plantareis em vosso Monte, no lugar que preparastes para a vossa habitação, no Santuário construído pelas vossas próprias mãos. O Senhor há de reinar eternamente, pelos séculos!"
      },
      {
        "referencia": "Sl 29",
        "refrao": "Eu vos exalto, ó Senhor, porque vós me livrastes!",
        "texto": "— Eu vos exalto, ó Senhor, pois me livrastes, e não deixastes rir de mim meus inimigos! Vós tirastes minha alma dos abismos e me salvastes, quando estava já morrendo!\n— Cantai salmos ao Senhor, povo fiel, dai-lhe graças e invocai seu santo nome! Pois sua ira dura apenas um momento, mas sua bondade permanece a vida inteira; se à tarde vem o pranto visitar-nos, de manhã vem saudar-nos a alegria.\n— Escutai-me, Senhor Deus, tende piedade! Sede, Senhor, o meu abrigo protetor! Transformastes o meu pranto em uma festa, Senhor meu Deus, eternamente hei de louvar-vos!"
      },
      {
        "referencia": "Is 12, 2-6",
        "refrao": "Com alegria bebereis do manancial da salvação.",
        "texto": "— Eis o Deus, meu Salvador, eu confio e nada temo; o Senhor é minha força, meu louvor e salvação. Com alegria bebereis do manancial da salvação.\n— E direis naquele dia: “Dai louvores ao Senhor, invocai seu santo nome, anunciai suas maravilhas, entre os povos proclamai que seu nome é o mais sublime.\n— Louvai cantando ao nosso Deus, que fez prodígios e portentos, publicai em toda a terra suas grandes maravilhas! Exultai cantando alegres, habitantes de Sião, porque é grande em vosso meio o Deus Santo de Israel!”"
      },
      {
        "referencia": "Sl 18B",
        "refrao": "Senhor, tens palavras de vida eterna.",
        "texto": "— A lei do Senhor Deus é perfeita, conforto para a alma! O testemunho do Senhor é fiel, sabedoria dos humildes.\n— Os preceitos do Senhor são precisos, alegria ao coração. O mandamento do Senhor é brilhante, para os olhos é uma luz.\n— É puro o temor do Senhor, imutável para sempre. Os julgamentos do Senhor são corretos e justos igualmente.\n— Mais desejáveis do que o ouro são eles, do que o ouro refinado. Suas palavras são mais doces que o mel, que o mel que sai dos favos."
      },
      {
        "referencia": "Sl 41",
        "refrao": "A minh'alma tem sede de Deus.",
        "texto": "— A minh'alma tem sede de Deus, e deseja o Deus vivo. Quando terei a alegria de ver a face de Deus?\n— Peregrino e feliz caminhando para a casa de Deus, entre gritos, louvor e alegria da multidão jubilosa.\n— Enviai vossa luz, vossa verdade: elas serão o meu guia; que me levem ao vosso Monte santo, até a vossa morada!\n— Então irei aos altares do Senhor, Deus da minha alegria. Vosso louvor cantarei, ao som da harpa, meu Senhor e meu Deus!"
      },
      {
        "referencia": "Sl 117",
        "refrao": "Aleluia, Aleluia, Aleluia",
        "texto": "— Dai graças ao Senhor, porque ele é bom! Eterna é a sua misericórdia! A casa de Israel agora o diga: “Eterna é a sua misericórdia!”\n— A mão direita do Senhor fez maravilhas, a mão direita do Senhor me levantou, a mão direita do Senhor fez maravilhas! Não morrerei, mas ao contrário, viverei para cantar as grandes obras do Senhor!\n— A pedra que os pedreiros rejeitaram, tornou-se agora a pedra angular. Pelo Senhor é que foi feito tudo isso: Que maravilhas ele fez a nossos olhos!"
      }
    ],
    "segundaLeitura": [
      {
        "referencia": "Gn 22, 1-2. 9a. 10-13. 15-18 (Forma Longa)",
        "titulo": "Leitura do Livro do Gênesis",
        "texto": "Naqueles dias, 1Deus pôs Abraão à prova. Chamando-o, disse: “Abraão!” E ele respondeu: “Aqui estou”. 2E Deus disse: “Toma teu filho único, Isaac, a quem tanto amas, dirige-te à terra de Moriá, e oferece-o ali em holocausto sobre um monte que eu te indicar”. 9aChegados ao lugar indicado por Deus, Abraão ergueu um altar, colocou a lenha em cima, amarrou o filho e o pôs sobre a lenha em cima do altar. 10Depois, estendeu a mão, empunhando a faca para sacrificar o filho. 11E eis que o anjo do Senhor gritou do céu, dizendo: “Abraão! Abraão!” Ele respondeu: “Aqui estou!”. 12E o anjo lhe disse: “Não estendas a mão contra teu filho e não lhe faças nenhum mal! Agora sei que temes a Deus, pois não me recusaste teu filho único”. 13Abraão, erguendo os olhos, viu um carneiro preso num espinheiro pelos chifres; foi buscá-lo e ofereceu-o em holocausto no lugar do seu filho. 15O anjo do Senhor chamou Abraão, pela segunda vez, do céu, 16e lhe disse: “Juro por mim mesmo — oráculo do Senhor —, uma vez que agiste desse modo e não me recusaste teu filho único, 17eu te abençoarei e tornarei tão numerosa tua descendência como as estrelas do céu e como as areias da praia do mar. Teus descendentes conquistarão as cidades dos inimigos. 18Por tua descendência serão abençoadas todas as nações da terra, porque me obedeceste”."
      }
    ],
    "evangelho": [
      {
        "referencia": "Lc 24, 1-12",
        "titulo": "Proclamação do Evangelho de Jesus Cristo ✠ segundo Lucas",
        "texto": "1No primeiro dia da semana, bem de madrugada, as mulheres foram ao túmulo de Jesus, levando os perfumes que haviam preparado. 2Elas encontraram a pedra do túmulo removida. 3Mas, ao entrar, não encontraram o corpo do Senhor Jesus 4e ficaram sem saber o que estava acontecendo. Nisso, dois homens com roupas brilhantes pararam perto delas. 5Tomadas de medo, elas olhavam para o chão, mas os dois homens disseram: “Por que estais procurando entre os mortos aquele que está vivo? 6Ele não está aqui. Ressuscitou! Lembrai-vos do que ele vos falou quando ainda estava na Galileia: 7‘O Filho do homem deve ser entregue nas mãos dos pecadores, ser crucificado e ressuscitar ao terceiro dia’”. 8Então as mulheres se lembraram das palavras de Jesus. 9Voltaram do túmulo e anunciaram tudo isso aos onze e a todos os outros. 10Eram Maria Madalena, Joana e Maria, mãe de Tiago. Também as outras mulheres que estavam com elas contaram essas coisas aos apóstolos. 11Mas eles acharam que tudo isso era desvario e não acreditaram. 12Pedro, no entanto, levantou-se e correu ao túmulo. Olhou para dentro e viu apenas os lençóis. Então voltou para casa, admirado com o que havia acontecido."
      }
    ],
    "extras": [
      {
        "titulo": "Proclamação da Páscoa (Exulte)",
        "texto": "Exulte o céu, e os anjos triunfantes, mensageiros de Deus, desçam cantando; façam soar trombetas fulgurantes, A vitória de um Rei anunciando.\nAlegre-se também a terra amiga, que meia há tantas luzes resplandece; e, vendo dissipar-se a treva antiga, ao som do eterno Rei brilha e se aquece.\nQue a Mãe Igreja alegre-se igualmente, erguendo as velas deste fogo novo, e escute, reboando de repente, o júbilo cantado pelo povo.\nE vós, que estais aqui, irmãos queridos, em torno desta chama reluzente, erguei os corações e, assim unidos, invoquemos o Deus onipotente.\nEle, que por seus dons nada reclama, quis que entre os seus levitas me encontrasse: para cantar a glória desta chama, de sua luz um raio me traspasse!\n\n– O Senhor esteja convosco.\n– Ele está no meio de nós.\n– Corações ao alto.\n– O nosso coração está em Deus.\n– Demos graças ao Senhor, nosso Deus.\n– É nosso dever e nossa salvação.\n\nSim, verdadeiramente é bom e justo Cantar o Pai de todo o coração, e celebrar seu filho Jesus Cristo, tornado para nós um novo Adão.\nFoi ele quem pagou do outro a culpa, quando por nós à morte se entregou: para pagar o antigo documento, na cruz todo o seu sangue derramou.\nPois eis agora a Páscoa, nossa festa, em que o real Cordeiro se imolou: marcando nossas portas, nossas almas, com seu divino sangue nos salvou.\nEsta é, Senhor, a noite em que do Egito retirastes os filhos de Israel, transpondo o Mar Vermelho a pé enxuto, rumo a terra onde correm leite e mel.\nÓ noite em que a coluna luminosa as trevas do pecado dissipou, e aos que creem no Cristo em toda a terra em novo povo eleito congregou!\nÓ noite em que Jesus rompeu o inferno, ao ressurgir da morte vencedor: de que nos valeria ter nascido, se não nos resgatasse em seu amor?\nÓ Deus, quão estupenda caridade vemos no vosso gesto fulgurar: Não hesitais em dar o próprio Filho, para a culpa dos servos resgatar.\nÓ pecado de Adão indispensável, pois Cristo o dissolve em seu amor; ó culpa tão feliz, que há merecido a graça de um tão grande Redentor!\nSó tu, noite feliz, soubeste a hora em que o Cristo da morte ressurgia; e é por isso que de ti foi escrito: A noite será luz para o meu dia! Pois esta noitlava todo o crime, liberta o pecador do seus grilhões; dissipa o ódio e dobra os poderosos, enche de luz e paz os corações.\nÓ noite de alegria verdadeira, que prostra o Faraó e ergue os Hebreus, que une de novo ao céu a terra inteira, pondo treva humana a luz de Deus.\nNa graça desta noite o vosso povo acende um sacrifício de louvor; acolhei, ó Pai Santo, o fogo novo: não perde, ao dividir-se, o seu fulgor.\nO círio que acendeu as nossas velas possa esta noite toda fulgurar; misture sua luz à das estrelas, cintile quando o dia despontar.\nQue ele possa agradar-vos como o Filho, que triunfou da morte e vence o mal: Deus, que a todos acende no seu brilho, e um dia voltará, sol triunfal.\nAS: Amém"
      },
      {
        "tipo": "Terceira Leitura",
        "referencia": "Ex 14, 15–15, 1",
        "titulo": "Leitura do Livro do Êxodo",
        "texto": "Naqueles dias, 15o Senhor disse a Moisés: “Por que clamas a mim por socorro? Dize aos filhos de Israel que se ponham em marcha. 16Quanto a ti, ergue a vara, estende o braço sobre o mar e divide-o, para que os filhos de Israel caminhem em seco pelo meio do mar. 17De minha parte, endurecerei o coração dos egípcios, para que sigam atrás deles, e eu seja glorificado às custas do Faraó e de todo o seu exército, dos seus carros e cavaleiros. 18E os egípcios saberão que eu sou o Senhor, quando eu for glorificado às custas do Faraó, dos seus carros e cavaleiros”.\n19Então, o anjo do Senhor, que caminhava à frente do acampamento dos filhos de Israel, mudou de posição e foi para trás deles; e com ele, ao mesmo tempo, a coluna de nuvem, que estava na frente, colocou-se atrás, 20inserindo-se entre o acampamento dos egípcios e o acampamento dos filhos de Israel. Para aqueles a nuvem era tenebrosa, para estes, iluminava a noite. Assim, durante a noite inteira, uns não puderam aproximar-se dos outros. 21Moisés estendeu a mão sobre o mar, e durante toda a noite o Senhor fez soprar sobre o mar um vento leste muito forte; e as águas se dividiram. 22Então, os filhos de Israel entraram pelo meio do mar a pé enxuto, enquanto as águas formavam como que uma muralha à direita e à esquerda. 23Os egípcios puseram-se a persegui-los, e todos os cavalos do Faraó, carros e cavaleiros os seguiram mar adentro.\n24Ora, de madrugada, o Senhor lançou um olhar, desde a coluna de fogo e da nuvem, sobre as tropas egípcias e as pôs em pânico. 25Bloqueou as rodas dos seus carros, de modo que só a muito custo podiam avançar. Disseram, então, os egípcios: “Fujamos de Israel! Pois o Senhor combate a favor deles, contra nós”. 26O Senhor disse a Moisés: “Estende a mão sobre o mar, para que as águas se voltem contra os egípcios, seus carros e cavaleiros”.\n27Moisés estendeu a mão sobre o mar e, ao romper da manhã, o mar voltou ao seu leito normal, enquanto os egípcios, em fuga, corriam ao encontro das águas, e o Senhor os mergulhou no meio das ondas.\n28As águas voltaram e cobriram carros, cavaleiros e todo o exército do Faraó, que tinha entrado no mar em perseguição a Israel. Não escapou um só. 29Os filhos de Israel, ao contrário, tinham passado a pé enxuto pelo meio do mar, cujas águas lhes formavam uma muralha à direita e à esquerda. 30Naquele dia, o Senhor livrou Israel da mão dos egípcios, e Israel viu os egípcios mortos nas praias do mar, 31e a mão poderosa do Senhor agir contra eles. O povo temeu o Senhor, e teve fé no Senhor e em Moisés, seu servo. 15, 1Então, Moisés e os filhos de Israel cantaram ao Senhor este cântico:"
      },
      {
        "tipo": "Quarta Leitura",
        "referencia": "Is 54, 5-14",
        "titulo": "Leitura do Livro do Profeta Isaías",
        "texto": "Teu esposo é aquele que te criou, seu nome é Senhor dos exércitos; teu redentor, o Santo de Israel, chama-se Deus de toda a terra. 6O Senhor te chamou, como a mulher abandonada e de alma aflita; como a esposa repudiada na mocidade, falou o teu Deus. 7Por um breve instante eu te abandonei, mas com imensa compaixão volto a acolher-te. 8Num momento de indignação, por um pouco ocultei de ti minha face, mas com misericórdia eterna compadeci-me de ti, diz teu salvador, o Senhor. 9Como fiz nos dias de Noé, a quem jurei nunca mais inundar a terra, assim juro que não me irritarei contra ti nem te farei ameaças. 10Podem os montes recuar e as colinas abalar-se, mas minha misericórdia não se apartará de ti, nada fará mudar a aliança de minha paz, diz o teu misericordioso Senhor. 11Pobrezinha, batida por vendavais, sem nenhum consolo, eis que assentarei tuas pedras sobre rubis, e tuas bases sobre safiras; 12revestirei de jaspe tuas fortificações, e teus portões, de pedras preciosas, e todos os teus muros, de pedra escolhida. 13Todos os teus filhos serão discípulos do Senhor, teus filhos possuirão muita paz; 14terás a justiça por fundamento. Longe da opressão, nada terás a temer; serás livre do terror, porque ele não se aproximará de ti."
      },
      {
        "tipo": "Quinta Leitura",
        "referencia": "Is 55, 1-11",
        "titulo": "Leitura do Livro do Profeta Isaías",
        "texto": "Assim diz o Senhor: 1“Ó vós todos que estais com sede, vinde às águas; vós que não tendes dinheiro, apressai-vos, vinde e comei, vinde comprar sem dinheiro, tomar vinho e leite, sem nenhuma paga.\n2Por que gastar dinheiro com outra coisa que não o pão; desperdiçar o salário, senão com satisfação completa? Ouvi-me com atenção, e alimentai-vos bem, para deleite e revigoramento do vosso corpo.\n3Inclinai vosso ouvido e vinde a mim, ouvi e tereis vida; farei convosco um pacto eterno, manterei fielmente as graças concedidas a Davi. 4Eis que fiz dele uma testemunha para os povos, chefe e mestre para as nações. 5Eis que chamarás uma nação que não conhecias, e acorrerão a ti povos que não te conheciam, por causa do Senhor, teu Deus, e do Santo de Israel, que te glorificou. 6Buscai o Senhor, enquanto pode ser achado; invocai-o, enquanto ele está perto. 7Abandone o ímpio seu caminho, e o homem injusto, suas maquinações; volte para o Senhor, que terá piedade dele, volte para nosso Deus, que é generoso no perdão.\n8Meus pensamentos não são como os vossos pensamentos, e vossos caminhos não são como os meus caminhos, diz o Senhor. 9Estão meus caminhos tão acima dos vossos caminhos e meus pensamentos acima dos vossos pensamentos, quanto está o céu acima da terra.\n10Como a chuva e a neve descem do céu e para lá não voltam mais, mas vêm irrigar e fecundar a terra, e fazê-la germinar e dar semente, para o plantio e para a alimentação, 11assim a palavra que sair de minha boca: não voltará para mim vazia; antes, realizará tudo que for de minha vontade e produzirá os efeitos que pretendi, ao enviá-la”."
      },
      {
        "tipo": "Sexta Leitura",
        "referencia": "Br 3, 9-15. 32–4, 4",
        "titulo": "Leitura do Livro do Profeta Baruc",
        "texto": "Ouve, Israel, os preceitos da vida; presta atenção, para aprenderes a sabedoria. 10Que se passa, Israel? Como é que te encontras em terra inimiga? 11Envelheceste num país estrangeiro, e te contaminaste com os mortos, foste contado entre os que descem à mansão dos mortos. 12Abandonaste a fonte da sabedoria! 13Se tivesses continuado no caminho de Deus, viverias em paz para sempre. 14Aprende onde está a sabedoria, onde está a fortaleza e onde está a inteligência, e aprenderás também onde está a longevidade e a vida, onde está o brilho dos olhos e a paz.\n15Quem descobriu onde está a sabedoria? Quem penetrou em seus tesouros? 32Aquele que tudo sabe, conhece-a, descobriu-a com sua inteligência; aquele que criou a terra para sempre e a encheu de animais e quadrúpedes; 33aquele que manda a luz, e ela vai, chama-a de volta, e ela obedece tremendo. 34As estrelas cintilam em seus postos de guarda e alegram-se; 35ele chamou-as, e elas respondem: “Aqui estamos”; e alumiam com alegria o que as fez.\n36Este é o nosso Deus, e nenhum outro pode comparar-se com ele. 37Ele revelou todo o caminho da sabedoria a Jacó, seu servo, e a Israel, seu bem-amado. 38Depois, ela foi vista sobre a terra e habitou entre os homens. 4, 1A sabedoria é o livro dos mandamentos de Deus, é a lei que permanece para sempre. Todos os que a seguem, têm a vida, e os que a abandonam, têm a morte. 2Volta-te, Jacó, e abraça-a; marcha para o esplendor, à sua luz. 3Não dês a outro a tua glória nem cedas a uma nação estranha teus privilégios. 4Ó Israel, felizes somos nós, porque nos é dado conhecer o que agrada a Deus."
      },
      {
        "tipo": "Sétima Leitura",
        "referencia": "Ez 36, 16-17a. 18-28",
        "titulo": "Leitura da Profecia de Ezequiel",
        "texto": "A palavra do Senhor foi-me dirigida nestes termos:17a “Filho do homem, os da casa de Israel estavam morando em sua terra. Mancharam-na com sua conduta e suas más ações. 18Então derramei sobre eles a minha ira, por causa do sangue que derramaram no país e dos ídolos com os quais o mancharam. 19Eu dispersei-os entre as nações, e eles foram espalhados pelos países. Julguei-os de acordo com sua conduta e suas más ações. 20Quando eles chegaram às nações para onde foram, profanaram o meu santo nome; pois deles se comentava: ‘Esse é o povo do Senhor; mas tiveram de sair do seu país!ʼ\n21Então eu tive pena do meu santo nome que a casa de Israel estava profanando entre as nações para onde foi. 22Por isso, dize à casa de Israel: ‘Assim fala o Senhor Deus: Não é por causa de vós que eu vou agir, casa de Israel, mas por causa do meu santo nome, que profanastes entre as nações para onde fostes. 23Vou mostrar a santidade do meu grande nome, que profanastes no meio das nações. As nações saberão que eu sou o Senhor, – oráculo do Senhor Deus – quando eu manifestar minha santidade à vista delas por meio de vós. 24Eu vos tirarei do meio das nações, vos reunirei de todos os países, e vos conduzirei para a vossa terra. 25Derramarei sobre vós uma água pura, e sereis purificados. Eu vos purificarei de todas as impurezas e de todos os ídolos.\n26Eu vos darei um coração novo e porei um espírito novo dentro de vós. Arrancarei do vosso corpo o coração de pedra e vos darei um coração de carne; 27porei o meu espírito dentro de vós e farei com que sigais a minha lei e cuideis de observar os meus mandamentos. 28Habitareis no país que dei a vossos pais. Sereis o meu povo e eu serei o vosso Deusʼ”."
      },
      {
        "tipo": "Epístola",
        "referencia": "Rm 6, 3-11",
        "titulo": "Leitura da Carta de São Paulo aos Romanos",
        "texto": "Irmãos: 3Será que ignorais que todos nós, batizados em Jesus Cristo, é na sua morte que fomos batizados? 4Pelo batismo na sua morte, fomos sepultados com ele, para que, como Cristo ressuscitou dos mortos pela glória do Pai, assim também nós levemos uma vida nova.\n5Pois, se fomos de certo modo identificados a Jesus Cristo por uma morte semelhante à sua, seremos semelhantes a ele também pela ressurreição. 6Sabemos que o nosso velho homem foi crucificado com Cristo, para que seja destruído o corpo de pecado, de maneira a não mais servirmos ao pecado. 7Com efeito, aquele que morreu está livre do pecado.\n8Se, pois, morremos com Cristo, cremos que também viveremos com ele. 9Sabemos que Cristo ressuscitado dos mortos não morre mais; a morte já não tem poder sobre ele. 10Pois aquele que morreu, morreu para o pecado uma vez por todas; mas aquele que vive, é para Deus que vive. 11Assim, vós também considerai-vos mortos para o pecado e vivos para Deus, em Jesus Cristo."
      }
    ]
  },
  "antifonas": {
    "entrada": "(Não há Antífona de Entrada. É realizada o solene início da Vigília ou Celebração da Luz.)",
    "comunhao": "Nosso cordeiro pascal, Cristo, já está imolado. Celebremos a festa, não com velho fermento, mas com pães ázimos de pureza e de verdade, aleluia!"
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
