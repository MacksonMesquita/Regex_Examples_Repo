# Regexes

Este repositório tem como foco, armazenar exemplos de regex a serem usadas e implementadas, afim de facilitar utilizações futuras. 
<br />

### Alguns alertas:

> OBS: This repo don't have language support, because the regexes can be changed by the language or country 😢

<br />

* A utilização de todo o conteúdo encontrado aqui, é livre, e pode ser copiada sem nenhuma intervenção.
* Algumas regexes, dependendo do local onde você se encontra (paises ou continentes diferentes) podem ou não, precisarem de alterações.
**As regexes foram baseadas no método de comunicação brasileiros,** portando em suas presenças normas e instruções comunicativas.

  ![](https://i.imgur.com/waxVImv.png)

  <br />
  
  ## Oque são regexes? 🤔

  Regex ou RE -> regular expressions -> expressões regulares.
  Nada mais são do que um conjunto de instruções que invalidam a entrada de dados que não sejam adeptos a determinadas circunstâncias. Ou seja, nada mais é, do que um padrão que limita certas entradas de dados.

  <br/>

  * Você pode estar se perguntando, para que servem as expressões regulares, ou porque eu deveria usa-las em meus códigos.

    Imagine que um sistema de cadastro bancário está sendo feito pela sua empresa. Você, um back-end, é encarregado de realizar a lógica por trás das validações.
    Um dos requisitos para que o usuário consiga se registrar, é o **CPF**.
    <br />
    Mas sabendo como os usuários são, e por questões de segurança, é desejável limitar a entrada de certos dados.
    <br />
    Por exemplo:
    <br />
    Em um **CPF** são permitidos apenas números e pontuações básica, entretanto, se você deixar livre a utilização de qualquer caractere, muito provavelmente os usuários vão inserir caracteres especiais, como "#" ou "!".

 **Uma regex serve justamente para invalidar e não permitir estas entradas.
<br />
 Temos inúmeros tipos de regex. 
 <br />
 Para a senhas, e-mails, CPF, strings e muito mais. Cada uma, com suas respectivas aparências.**

<br />

  ## Regexes: 💻

  ##### Validação de email.
      '^(\w*)@([\w-]+\.)+[\w-]{2,4}'

  ##### Validação de cpf.
      '^\d{3}\.\d{3}\.\d{3}\-\d{2}$'

  ##### Validação de número de telefone (celular).
      '(\(?\d{2}\)?\s)?(\d{4,5}\-\d{4})'

  ##### Validação de datas.
        '\d{1,2}\/\d{1,2}\/\d{2,4}'

  ##### Validação de RG.
        '(^\d{1,2}).?(\d{3}).?(\d{3})-?(\d{1}|X|x$)'

  ##### Validação de CEP.
        '(^[0-9]{5})-?([0-9]{3}$)'

  ##### Validação de strings sem caracteres especiais.
        '^[ 0-9a-zA-Z\b]+$'

  ##### Validação de hora.
        '^([0-9]{1,2}):([0-5][0-9])\s?([aApP][mM])?$'

  ##### Validação de senha -> Senha de no mínimo 6 caracteres, pelo menos uma letra maiúscula, pelo menos uma letra minúscula, pelo menos um número, pelo menos um caractere especial.
        '(?=^.{6,}$)((?=.*\w)(?=.*[A-Z])(?=.*[a-z])(?=.*[0-9])(?=.*[|!"$%&#\/\(\)\?\^\'\\\+\-\*]))^.*'
        
<br />

## Onde posso validar minhas regexes? ☣️

#### para a validação de sua regex, utilize o site 
     https://regex101.com/  

<br />

 ![](https://i.imgur.com/waxVImv.png)

### ⚠️DETALHE: Vale lembrar que, as regex não validam de fato algo, apenas limitam que caracteres errados entrem. Em outras palavras, validam o formato, não o documento!

 <br />

## Processo de formação de uma regex 🏗️

Eu sei que é muito legal você simplesmente pegar uma regex pronta, colocar no seu código e vê-la funcionar, sem se preocupar com mais nada.
Entretanto se quiser aprender como montar a sua regex, segue abaixo alguns breves tutoriais, pois como pode ver, as regex podem ser altamente customizáveis!

<br />

### Classes 🏛️

As regexes são expressadas por classes, compostas por números, letras ou simbolos, as classes são representadas por colchetes -> [ ]
<br />
dentro de uma classe, você pode colocar as letras, números ou simbolos que você deseja banir ou aceitar.

#### 
     [0123456789]

<br />

Oque está sendo representado na classe acima, nada mais é do que uma ordem.
<br />
A qual diz que você quer permitir os números " 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 ".
<br />
entretanto, você pode perceber que isso ficaria enorme se por acaso fosse aceito os números de o a 100 em um determinado local. 
<br /> 
Para evitar isso, utilizamos o ifen.

#### Deste modo, você está dizendo a mesma coisa da classe acima, porém com um aspecto muito mais *clean*.
     [0-9]

Vale lembrar que fora da classe, o hífen é avaliado como um hífen (valor semântico), mas como dito anteriormente, dentro ele é avaliado como um range.

<br />

### Case sensitive 💌

Com certeza você já deve ter ouvido falar deste termo, mas caso contrário, não se preocupe.
<br />
*Case sensitive* é o termo utilizado para se referir a diferença de sentido entre cases (maiúsculo e mínusculo), ou seja, de acordo com a case da letra (o jeito a qual ela se apresenta)
o sentido dela é alterado, logo -> **A** -> é diferente de -> **a**.

No caso de criação de classes usando a case sensitive, é necessário colocar ambas funções para que sejam validadas.

#### 
     [A-Za-z]

Como pode perceber, estou dizendo que na case maiúscula eu quero as letras de A a Z, enquanto na case minúscula as letars de a a z.

<br />

### Alterador de sentido 🥶

Quando fazemos uma regex, existem oque chamamos de alterador de sentido, um deles é a barra invertida.
<br />
Esta barra nos diz que tudo oque vir depois dela, o seu sentido natural será alterado. Em um exemplo, 
o "d" sozinho, é interpretado como uma letra, mas quando colocamos a barra invertida antes, ele se transforma em um "pegador de caracteres alfanuméricos".

#### 
     [d]
     [\d]

* Aqui vai algumas caracteres além do "d", que com a barra invertida tem o seu sentido alterado:

#### 
     [\s]
     [\w]
     [\.]
     [\S]
     [\W]

Eles representam respectivamente:

#### 
     Considera espaços em branco como parte dos elementos requisitados.
     Representa world characters, ou seja, libera todas as letras, números e underlines.
     Permite TUDO, literalmente tudo.
     Não permite espaços em branco como parte dos elemntos requisitados.
     Não permite worldcharacters como parte dos elementos requisitados.

* Isso mesmo, para fazer uma negação no mundo das regexes, basta apenas colocar a letra desejada como maiúscula, desde que seja seguida por uma barra invertida.

<br />

### Contadores 🤑

Os contadores servem para mostar quantas vezes uma determinada coisa pode aparecer em um determinado local, vamos supor:

Você esta validando um cep CPF, ao invés de colocar

#### 
     \ddd\.-\ddd\.-\ddd\-\dd

Você pode usar números dentro de chaves para mostrar quantas vezes uma coisa aparece, neste caso: 

#### 
     \d{3}\.\d{3}\.\d{3}\-\d{2}

<br/>

* Legal, mas e quando você não sabe quantas vezes os números apareceram? Não se preocupe, para isso use o {n,}
  <br />
  o qual significa que determinado número pode aparcer "n" vezes em sua regex.
  <br />
  *Vale lembrar que será no lugar do "n", que você colocará a quantidade de vezes que o elemento poderá aparecer.*

**Dentro deste caso, você pode colocar que determinada coisa aparecerá no mínimo {5,}.** 


Todavia, se existe um limite de caracteres para determinada coisa, você deverá colocar o limite destes caracteres, obviamnete.
<br />
Para isso, existe a equação {n, m} ou {5, 12} -> onde n = mínimo; e m = máximo, ou seja:
<br />
**mínimo 5 vezes com máximo de 12.**

<br/>

#### 
     \d{5,12} -> exemplo  

<br/>

Mas calma que ainda não acaba ai, ainda no sistema dos contadores, temos o "+".

Imagine que você esta validando um nome completo de uma pessoa, em um nome completo, em sua composição você tem letra maiúsculas e minúsculas, além de espaços em branco. 
Você pode pensar que é muito simples, e surante o processo fazer isso: 

###
    [A-Za-z\s]

<br/>

Todavia se fizer isto, será selecionada cada letra e espaço individualmente. 
<br />
No fim, queremos que seja selecionado os blocos inteiros que corresponderão aos nomes, correto? Então é aqui que entra o "+".

#### Oque ele irá fazer, é agrupar um determinada classe. 
    [A-Za-z\s]+

<br />

### Âncoras ⚓

Por fim, para montar uma regex, você precisará de âncoras, as quais servem para que você delimite um começo e um fim em uma expressão regular, Ambas seguem um padrão
e raramente sairam do padrão, tal como: 

###
    âncora no inicio + expressão + âncora ao final 
    
<br/>

As âncoras responsáveis por delimitar um inicio e um fim, são os simbolos "^" e "$"

####
    ^<minha-expressão>$

<br/>

 ![](https://i.imgur.com/waxVImv.png)

 ### Como você pode ver, não é tão dificil de entender como uma regex é formada, obviamnete não coloquei tudo sobre as mesmas, pois exixtem milhares de simbolos e combinações possíveis a serem feitas. Mas o processo a qual uma regex é formada, e suas principais características foram mostradas no arquivo.
