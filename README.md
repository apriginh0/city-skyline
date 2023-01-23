# city-skyline
A city made entirely in CSS

PASSO A PASSO

No CSS, você pode selecionar tudo com um asterisco. Adicione uma borda a tudo usando o seletor * e dando a ela uma border de 1px solid black. Esse é um truque que ajuda a visualizar onde os elementos estão e seu tamanho. Você removerá isso mais tarde.

Também adicione um box-sizing de border-box para tudo. Isto fará com que a borda que você adicionou não adicione qualquer tamanho aos elementos.

Você pode ver o body (ele é a caixa mais interna na página); a caixa em torno dele é o elemento html. Faça o body preencher toda a viewport dando a ele uma height de 100vh. Remova a margin padrão do body definindo a margin como 0. Finalmente, defina a propriedade overflow como hidden para ocultar quaisquer barras de rolagem que aparecem quando algo se estende além da janela de visualização.

Crie um elemento div no body com a classe de background-buildings. Este será um recipiente para um grupo de edifícios.

Dê ao elemento .background-buildings uma width e uma height de 100% para torná-las a largura e a altura totais do elemento pai, o body.

Aninhe uma div com uma classe de bb1 no contêiner dos edifícios em segundo plano. Abra o arquivo styles.css e dê a .bb1 uma width de 10% e uma height de 70%. "bb" é a abreviação para "background building" (construção em segundo plano). Esse será o primeiro prédio.

Insira quatro elementos div dentro do container .bb1. Dê a eles as classes bb1a, bb1b, bb1c e bb1d, nessa ordem. Este edifício terá quatro seções.

Forneça às partes da construção as propriedades width e height com estes valores: 70% e 10% para .bb1a, 80% e 10% para .bb1b, 90% e 10% para .bb1c e 100% e 70% para .bb1d. Lembre-se de que essas porcentagens são relativas ao pai e observe que as alturas somarão 100% - enchendo verticalmente o contêiner.

Centralize as partes do seu edifício transformando o elemento .bb1 em um elemento pai do flexbox. Use as propriedades flex-direction e align-items para centralizar os elementos filhos.

Agora você tem algo que começa a se parecer com um edifício. Você está pronto para criar sua primeira variável. Declarações de variáveis começam com dois traços (-) e recebem um nome e um valor como este: --variable-name: value;. Na regra para a classe bb1, crie uma variável chamada --building-color1 e dê a ela um valor de #999.

Para usar uma variável, coloque o nome da variável entre parênteses precedidos pela palavra var desta forma: var(--variable-name). Não importa o valor que você forneceu à variável, ele será aplicado a qualquer propriedade que você usar.
Adicione a variável --building-color1 que você criou no passo anterior como o valor da propriedade background-color da classe .bb1a.

Use a mesma variável que você usou como valor de background-color nas classes .bb1b, .bb1c e .bb1d para preencher o restante do edifício.

Altere o valor da variável de #999 para #aa80ff e você poderá ver como ela é aplicada em todos os lugares em que você usou a variável. Esta é a principal vantagem do uso de variáveis, podendo alterar rapidamente muitos valores na folha de estilo apenas alterando o valor de uma variável.

Agora, o primeiro edifício parece bom. Aninhe três novos elementos div no contêiner .background-buildings e dê a eles as classes de bb2, bb3 e bb4, nessa ordem. Esses serão mais três edifícios para o fundo.

Dê aos novos edifícios as propriedades width e height de: 10% e 50% para .bb2, 10% e 55% para .bb3 e 11% e 58% para .bb4. Você usará quase todas as unidades baseadas em porcentagem e alguns flexbox para este projeto, então, tudo será completamente responsivo.

No momento, os edifícios estão empilhados uns em cima dos outros. Alinhe os edifícios, transformando o elemento .background-buildings em um flexbox anterior. Use as propriedades align-items e justify-content para espaçar igualmente os edifícios através da parte inferior do elemento.

Os prédios estão muito espaçados. Aproxime-os mais adicionando dois elementos div vazios no topo do elemento .background-buildings, mais dois na parte inferior dele e mais um entre .bb3 e .bb4. Esses elementos serão adicionados como elementos uniformemente espaçados pelo contêiner, efetivamente movendo os edifícios mais para perto do centro.

Crie outra variável abaixo da variável --building-color1. Dê à nova variável o nome de --building-color2 e dê a ela um valor de #66cc99. Em seguida, defina-a como a background-color de .bb2.

Isso não funcionou. Você deve adicionar um valor substituto para uma variável colocando-o como o segundo valor de onde você usa a variável desta maneira: var(--variable-name, fallback-value). A propriedade usará o valor substituto quando houver um problema com a variável. Adicione um valor substituto green à background-color de .bb2.

Crie uma variável abaixo das outras chamada --building-color3 e dê a ela um valor de #cc6699. Em seguida, use-a como background-color da classe .bb3 e dê a ela um valor substituto de pink.

Isso não funcionou, pois as variáveis que você declarou em .bb1 não são reproduzidas nos elementos irmãos .bb2 e .bb3. É assim que o CSS funciona. Por causa disso, as variáveis são frequentemente declaradas no seletor :root. Esse é o seletor de nível mais alto no CSS; colocar as variáveis lá as tornará utilizáveis em todos os lugares. Adicione o seletor :root ao topo da folha de estilos e mova todas as váriaveis declaráveis para lá.

Agora que você resolveu os erros e os prédios estão com a cor correta, você pode remover os valores alternativos (de fallback) nos dois lugares em que eles foram usados. Vá em frente e faça isso agora.

Crie outra variável chamada --building-color4 e dê a ela um valor de #538cc6. Certifique-se de que esteja no seletor :root dessa vez. Então use-o para preencher o último prédio.

Os prédios de fundo estão começando a ficar bons. Crie uma div abaixo do elemento .background-buildings e dê a ela uma classe de foreground-buildings. Esse será outro contêiner para mais prédios.

Você vai querer que o contêiner .foreground-buildings fique diretamente na parte superior do elemento .background-buildings. Dê a ele uma width e uma height de 100% e defina a position como absolute e o top como 0. Isso fará com que seja do mesmo tamanho que o corpo e que se mova seu início para o canto superior esquerdo.

Insira seis elementos div dentro de .foreground-buildings e dê a eles as classes de fb1 a fb6, nessa ordem. "fb" significa "construção em primeiro plano". Serão mais seis edifícios para o primeiro plano.

Dê aos seis novos elementos o width e height os valores: 10% e 60% até .fb1, 10% e 40% até .fb2, 10% e 35% até .fb3, 8% e 45% até .fb4, 10% e 33% até .fb5, e 9% e 38% Até .fb6.

Adicione a mesma propriedade display, align-items, e justify-content e valores para .foreground-buildings que você usou em .background-buildings. Assim, o Flexbox será usado novamente para espaçar uniformemente os edifícios na parte inferior do elemento.

Você deve otimizar o código. Mova as propriedades position e top e valores de .foreground-buildings para .background-buildings. Em seguida, selecione ambos .background-buildings e .foreground-buildings por lá, efetivamente aplicando esses estilos a ambos os elementos. Você pode usar uma vírgula (,) para separar seletores como este: selector1, selector2.

Agora que você fez isso, já pode excluir a antiga declaração de .foreground-buildings e todas as propriedades, já que elas não são mais necessárias.

O horizonte está quase pronto. Preencha a propriedade background-color dos edifícios em primeiro plano. Use a variável --building-color1 para preencher .fb3 e .fb4, --building-color2 para .fb5, --building-color3 para .fb2 e .fb6 e --building-color4 para .fb1.

Compacte os prédios novamente adicionando dois elementos div vazios dentro da parte superior e inferior do elemento .foreground-buildings e mais um entre .fb2 e .fb3.

Move a posição de .fb4 em relação a onde está agora adicionando uma position relative e left de 10% a ele. Faça o mesmo para .fb5, mas use right em vez de left. Isto encobrirá o espaço em branco restante entre os edifícios.

O código está começando a ficar bem longo. Adicionar um comentário acima da classe .fb1 que diz FOREGROUND BUILDINGS - "fb" stands for "foreground building" para ajudar as pessoas a entenderem o código. Acima da classe .bb1 adicione outro comentário que diz BACKGROUND BUILDINGS - "bb" stands for "background building". Se você não se lembra, comentários em CSS têm esta aparência: /* Comment here */.

Crie uma variável em :root chamada --window-color1 com o valor de black. Ela será usada como cor secundária para o prédio roxo.

Os gradientes em CSS são uma forma de transição entre as cores através da distância de um elemento. Eles são aplicados à propriedade background e a sintaxe tem essa aparência:
gradient-type(
  color1,
  color2
);
No exemplo, color1 é sólido no topo, color2 é sólido na parte inferior, e entre elas as transições acontecem igualmente de uma para a outra. Em .bb1a, adicione uma propriedade background abaixo da propriedade background-color. Defina-a como um gradiente do tipo linear-gradient, que usa --building-color1 como a primeira cor e --window-color1 como a segunda.

Você quer adicionar o mesmo gradiente às próximas duas seções. Em vez de fazer isso, crie um seletor de classe chamado bb1-window e mova as propriedades de valores de height e background de .bb1a para o novo seletor de classe.

Adicione a nova classe bb1-window aos elementos .bb1a, .bb1b e .bb1c. Isto aplicará o gradiente a eles.

Você não precisa mais das propriedades height ou background-color em .bb1a, .bb1b ou .bb1c, então vá em frente e remova essas propriedades.

Os gradientes podem usar quantas cores você quiser, assim:
gradient-type(
  color1,
  color2,
  color3
);
Adicione um linear-gradient a .bb1d com orange como a primeira cor, --building-color1 como a segunda e --window-color1 como a terceira. Lembre-se de usar o gradiente na propriedade background.

Está um pouco escondido atrás dos edifícios do primeiro plano, mas você pode ver as três cores do gradiente lá. Como você a está usando agora, remova a propriedade background-color de .bb1d.

Você pode especificar onde você deseja completar uma transição gradiente adicionando-a à cor como esta:
gradient-type(
  color1,
  color2 20%,
  color3
);
Aqui, ele mudará de color1 para color2 entre 0% e 20% do elemento e depois mudar para color3 para o resto. Adicione 80% à cor --building-color1 do gradiente .bb1d para que você possa vê-lo em ação.

Remova orange do gradiente de .bb1d e altere o valor de 80% para 50%. Isso fará com que --building-color1 seja sólida para a metade superior e depois mude para --window-color1 na metade inferior.

Insira dois novos elementos div dentro de .bb2 e dê a eles as classes bb2a e bb2b, nessa ordem. Serão as duas seções para esse edifício.

Dê .bb2b uma width e uma height de 100% para encher o recipiente do prédio. Você vai adicionar alguma coisa no topo um pouco mais tarde.

Crie uma variável em :root chamada window-color2 com o valor de #8cd9b3. Ela será usada como cor secundária para esse prédio.

As transições gradientes muitas vezes mudam gradualmente de uma cor para outra. Você pode fazer a alteração uma linha sólida como esta:
linear-gradient(
  var(--first-color) 0%,
  var(--first-color) 40%,
  var(--second-color) 40%,
  var(--second-color) 80%
);
No .bb2b, adicione um linear-gradient que usa --building-color2 de 0% a 6% e --window-color2 de 6% a 9%.

Você pode ver a cor mudar no topo da seção. Altere o tipo gradiente de linear-gradient para repeating-linear-gradient para esta seção. Isso fará com que as quatro cores do gradiente se repitam até chegar à parte inferior do elemento, dando-lhe algumas listras e evitando a necessidade de adicionar vários elementos para criá-las.

Nos próximos passos, você vai usar alguns truques com bordas de CSS para transformar a seção .bb2a em um triângulo no topo do edifício. Primeiro, remova o background-color de .bb2 já que você não precisa mais dele.

Adicione essas propriedades no .bb2a:
margin: auto;
width: 5vw;
height: 5vw;
border-top: 1vw solid #000;
border-bottom: 1vw solid #000;
border-left: 1vw solid #999;
border-right: 1vw solid #999;
Depois de adicioná-las, você pode ver como uma borda espessa em um elemento fornece alguns ângulos onde dois lados se encontram. Você usará essa borda inferior como o topo do edifício.

Em seguida, remova a width e a height de .bb2a e altere a border-left e a border-right para que usem 5vw em vez de 1vw. O elemento agora terá tamanho zero e as bordas ficarão reunidas no meio.

Em seguida, altere os dois #999 de .bb2a para transparent. Isto tornará as bordas da esquerda e da direita invisíveis.

Remover as propriedades e valores margin e border-top do elemento .bb2a para transformá-lo em um triângulo para o topo do edifício.

Por fim, na propriedade border-bottom de .bb2a, mude 1vw para 5vh e a cor #000 para a variável --building-color2. Aí está. Agora parece bom! A qualquer momento durante o projeto, você pode comentar ou remover a propriedade border que você adicionou a tudo no início para ver a aparência dos edifícios quando ela for removida no final.

Vamos passar para o próximo edifício! Crie uma variável chamada --window-color3 em :root e dê a ela um valor de #d98cb3. Ela será usada como cor secundária para o prédio cor de rosa.

Até agora, todos os gradientes que você criou foram de cima para baixo. Essa é a direção padrão. Você pode especificar outra direção, adicionando-a antes das cores, veja o exemplo:
gradient-type(
  direction,
  color1,
  color2
);
Preencha .bb3 com repeating-linear-gradient. Use 90deg para a direção, com building-color3 para as duas primeiras cores e window-color3 a 15% para a terceira. Quando você não especificar uma distância para uma cor, ela usará os valores que fazem sentido. Neste caso, as duas primeiras cores estarão por padrão entre 0% e 7.5%, porque começam em 0% e 7.5% é metade dos 15%.

Remova a propriedade background-color e o valor de .bb3, pois agora você usará o gradiente como fundo.

O próximo edifício terá três seções. Você deve adicionar três elementos div dentro de .bb4. Dê à eles as classes de bb4a, bb4b e bb4c, nessa ordem.

Dê aos novos elementos div uma width e uma height com estes valores: 3% e 10% para .bb4a, 80% e 5% para .bb4b e 100% e 85% para .bb4c.

Remova a propriedade e o valor de background-color de .bb4 e adicione-o as três novas seções .bb4a, .bb4b e .bb4c, então apenas as seções estão preenchidas.

Você quer que .bb4 compartilhe as propriedades de .bb1 que centralizam as seções. Em vez de duplicar esse código, crie uma classe acima do comentário do plano de fundo do prédio chamado building-wrap. Deixe-o em branco por enquanto. Esta classe será usada em alguns lugares para agilizar seu tempo.

Mova as propriedades e valores de display, flex-direction e align-items de .bb1 para a nova classe building-wrap.

Adicione a nova classe building-wrap aos elementos .bb1 e .bb4. Isto aplicará as propriedades de centralização aos prédios que precisam desse ajuste.

Crie uma variável chamada --window-color4 em :root e dê a ela um valor de #8cb3d9. Ela será usada como cor secundária para o último prédio de fundo.

Insira quatro novos elementos div em .bb4c e dê a eles a classe bb4-window. Essas serão as janelas deste edifício.

Dê à classe bb4-window uma width de 18%, uma height de 90% e adicione a variável --window-color4 como o valor de background-color.

As janelas estão empilhadas em cima umas das outras à esquerda da seção, atrás do edifício roxo. Adicione uma nova classe abaixo do .building-wrap chamado window-wrap. Faça .window-wrap um contêiner de flexbox, use as propriedades align-items e justify-content para centralizar os elementos filhos verticalmente, bem como espaçá-los igualmente em seus pais, respectivamente.

Adicione a nova classe window-wrap ao elemento .bb4c.

Parece bom! Vamos trabalhar agora o primeiro plano de construções! Transforme o edifício .fb1 em três seções, aninhando três novos elementos div dentro dele. Dê à eles as classes de fb1a, fb1b e fb1c, nessa ordem.

Dê a .fb1b uma width de 60% e uma height de 10%. Dê a .fb1c uma width de 100% e uma height de 80%.

Adicione a classe building-wrap ao elemento .fb1 para centralizar as seções.

Mova a propriedade e o valor de background-color de .fb1 para .fb1b.

Não se preocupe com o espaço no fundo. Tudo será movido para baixo mais tarde, quando você adicionar um pouco de altura ao elemento no topo do edifício.

Adicione um repeating-linear-gradient a .fb1c com um ângulo de 90deg. Use --building-color4 de 0% a 10% e transparent de 10% a 15%.

Você pode adicionar vários gradientes a um elemento separando-os com uma vírgula (,) assim:
gradient1(
  colors
),
gradient2(
  colors
);
Adicione um repeating-linear-gradient a .fb1c abaixo do que já está lá; use --building-color4 de 0% a 10% e --window-color4 de 10% a 90%. Isso preencherá atrás do gradiente que você adicionou por último.

Você vai usar mais alguns truques de borda para a seção superior. Adicione um border-bottom com um valor de 7vh solid var(--building-color4) to .fb1a. Isto colocará uma borda de 7vh de altura na parte inferior. Mas como o elemento tem tamanho zero, só aparece como uma linha de 2px de largura da borda de 1px que está em todos os elementos.

Quando se aumenta o tamanho das bordas da esquerda e da direita, a borda inferior vai expandir e ocupar a largura das larguras combinadas da esquerda e da direita. Adicione 2vw solid transparent como o valor das propriedades border-left e border-right de .fb1a. Eles serão invisíveis, mas deixarão a borda na parte inferior com 4vw de largura.

Vamos passar para o próximo edifício! Insira dois novos elementos div dentro de .fb2 e dê a eles as classes fb2a e fb2b, nessa ordem.

Dê a .fb2a um width de 100% e a .fb2b uma width de 100% e uma height de 75%.

Insira três elementos div em .fb2b e dê a eles a classe fb2-window. Essas serão as janelas desta seção do edifício.

Adicione a classe window-wrap a .fb2b para posicionar os novos elementos da janela.

Dê aos elementos .fb2-window uma width de 22%, uma height de 100% e um background-color com o valor da variável --window-color3.

Mova a propriedade background-color e o valor de .fb2 para .fb2b para colorir apenas a seção e não o contêiner.

Para .fb2a, adicione uma border-bottom de 10vh solid var(--building-color3), uma border-left e uma border-right de 1vw solid transparent. Desta vez, o truque de borda vai criar uma forma de trapezoides.

Para o próximo edifício, insira quatro elementos div dentro de .fb3 com classes de fb3a, fb3b, fb3a novamente e fb3b novamente, nessa ordem. Este edifício terá quatro seções. As duas seções superiores serão quase as mesmas que as duas inferiores.

Dê ao elemento .fb3a uma width de 80% e uma height de 15%. Agora, dê ao elemento .fb3b uma width de 100% e uma height de 35%.

Mova a propriedade e o valor de background-color de .fb3 e adicione-os em .fb3a e .fb3b.

Adicione a classe building-wrap ao elemento .fb3 para centralizar as seções.

Você deve aninhar 3 novos elementos div dentro do primeiro elemento .fb3a. Dê a cada um a classe de fb3-window. Essas serão as janelas dessa seção.

Dê aos elementos .fb3-window uma width de 25%, uma height de 80% e use a variável --window-color1 como o valor de background-color.

Adicione a classe window-wrap ao elemento .fb3a para centralizar e dar espaço às janelas.

Com as variáveis do CSS, você pode alterar valores sem pesquisar em todos os lugares da folha de estilos. Altere o valor de --window-color1 para #bb99ff.

Faltam apenas mais três edifícios. Insira dois novos elementos div dentro do elemento .fb4 e dê a eles as classes fb4a e fb4b, nessa ordem. Lembre-se de que você inverteu a localização de .fb4 e .fb5, então você está trabalhando agora no prédio roxo mais à direita.

Dê ao elemento .fb4b uma width de 100% e uma height de 89%.

Adicione a variável --building-color1 como valor da propriedade background-color de .fb4b. Depois, remova a background-color de .fb4.

Insira seis elementos div em .fb4b e dê a eles a classe fb4-window.

Dê aos elementos .fb4-window uma width de 30%, uma height de 10% e um border-radius de 50%. Isso criará algumas janelas circulares para esse prédio.

Preencha as janelas com a cor secundária para esse edifício. Também adicione uma margin de 10% para dar às janelas algum espaço.

As janelas estão empilhadas em cima umas das outras no prédio roxo mais à direita. Transforme o edifício em um elemento pai flexbox e use a propriedade flex-wrap para colocar as janelas lado a lado, empurrando-as para uma nova linha quando elas não se encaixarem.

Esse edifício terá outro triângulo no topo. Dê à seção superior um border-top de 5vh solid transparent e um border-left de 8vw, solid que use a variável da cor do edifício como cor.

Vamos passar para o próximo edifício! É o verde em primeiro plano. Dê a ele um repeating-linear-gradient com a cor do edifício de 0% a 5% e transparent de 5% a 10%.

Adicione outro repeating-linear-gradient abaixo daquele que você acabou de adicionar. Dê a ele uma direção de 90deg, use a cor do edifício de 0% a 12% e a cor da janela de 12% a 44%. Isso criará várias janelas retangulares.

Você não precisa mais da background-color para esse prédio, então você pode remover essa propriedade.

Finalmente! Você chegou no último prédio! Adiciona um gradiente recorrente a ele com a direção de 90deg. Use a cor do prédio de 0% para 10% e transparent de 10% para 30%.

Adicione outro gradiente repetitivo a esse prédio; Faça ele igual ao que você acabou de adicionar, exceto pelo fato de que você não deve adicionar a direção 90deg; Ao invés disso use a cor da janela de duas cores transparent.

Você pode remover a background-color para este prédio agora, já que ele não é necessário.

Ok, os prédios estão prontos. Volte para o seletor * e remova a border que você aplicou a tudo no início e os edifícios se unirão.

Adicione sky como uma segunda classe do elemento .background-buildings. Você vai fazer um plano de fundo para o céu.

Dê a classe sky um radial-gradient. Use #ffcf33 de 0% a 20%, #ffff66 a 21% e #bbeeff a 100%. Isso adicionará um gradiente circular ao fundo, que será o sol.

Na parte superior da lista de cores gradientes do céu, onde você colocaria uma direção para o gradiente, adicione circle closest-corner at 15% 15%,. Isso moverá o início do gradiente para 15% da parte superior e da esquerda. Ele o fará terminar no closest-corner e manterá uma forma circle. Estas são algumas palavras-chave embutidas em gradientes para descrever como ele se comporta.

Uma media query (ou consulta de mídia) pode ser usada para alterar estilos com base em certas condições. Elas têm essa aparência:
@media (condition) {

}
Adicione uma media query vazia na parte inferior da folha de estilo com a condição max-width: 1000px. Os estilos adicionados aqui terão efeito quando o tamanho do documento for de 1000px de largura ou menos.

Copie e cole toda a classe sky com todas as propriedades e valores na media query. Você vai criar outro esquema de cores para o horizonte que se altera do dia para noite.
Observação: você precisará rolar para além da região editável para copiar a classe.

Na classe sky media query, altere os dois valores de cor de #ffcf33 para #ccc, o valor de #ffff66 para #445 e o valor de #bbeeff para #223. Então você poderá redimensionar a janela para ver o plano de fundo mudar de cor.

Adicione um seletor :root ao topo da media query. Em seguida, redefina todas as quatro variáveis --building-color para que usem o valor #000 lá.

Por último, no seletor :root da media query, redefina todas as quatro variáveis de --window-color para que usem #777. Quando você terminar, redimensione a janela e observe-a passando de dia para noite.
As variáveis são usadas principalmente com cores. É assim que você as usa aqui. Elas, no entanto, podem receber qualquer valor e ser usadas em qualquer propriedade. O projeto parece ótimo!
