# Regex Examples

Este repositório tem como foco, armazenar exemplos de regex a serem usadas e implementadas, afim de facilitar utilizações futuras. 
<br />

### Alguns alertas:

* OBS: This repo don't have language support 😢
* A utilização de todo o conteúdo encontrado aqui, é livre, e pode ser copiada sem nenhuma intervenção.
* Algumas regexes, dependendo do local onde você se encontra (paises ou continentes diferentes) podem ou não, precisarem de alterações. -> **As regexes foram baseadas no método de comunicação brasileiros.,** portando em suas presenças normas e instruções comunicativas.

  ![](https://i.imgur.com/waxVImv.png)

  <br />
  
  ## Oque são regexes? 🤔

  Regex ou RE -> regular expressions -> expressões regulares.
  Nada mais são do que um conjunto de instruções que invalidam a entrada de dados que não sejam adeptos a determinadas circunstâncias. Ou seja, nada mais é, do que um padrão que limita certas entradas de dados.

  * Você pode estar se perguntando, para que servem as expressões regulares, ou porque eu deveria usa-las em meus códigos.

    Imagine que um sistema de cadastro bancário está sendo feito pela sua empresa. Você, um back-end, é encarregado de realizar a lógica por trás das validações.
    Um dos requisitos para que o usuário consiga se registrar, é o **CPF**. Mas, sabendo como os usuários são, e por questões de segurança, é desejável limitar a entrada de certos dados. Por exemplo:
    Em um **CPF** são permitidos apenas números e pontuações básica, entretanto, se você deixar livre a utilização de qualquer caractere, muito provavelmente os usuários vão inserir caracteres especiais, como "#" ou "!".

 **Uma regex serve justamente para invalidar e não permitir estas entradas.
 Temos inúmeros tipos de regex; para senhas, e-mails, CPF, strings. Cada uma, com suas respectivas aparências.**

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

### ⚠️DETALHE: Vale lembrar que, as regex não validam de fato algo, apenas limitam que caracteres errados entrem, em outras palavras, validam o formato, não o documento.
