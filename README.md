# web-scraping-python
Como fazer web scraping python de maneira fácil e rápida.

O que é web scraping Python? Você vai conhecer as infinitas possibilidades que você consegue fazer com essa aplicação!


#O que é web scraping?
Web scraping é uma coleta de dados da web, de sites, onde são usados scripts e programas para “raspar” informações destes sites e que poderão ser usadas para futuras análises.

Por exemplo, comparar preços, monitorar o tempo, pesquisar o que está em alta no mercado, entre muitas outras coisas.

O tipo mais básico de web scraping é o download de alguma página web, que pode ser feito apenas apertando Ctrl+S ou Command+S em alguma página, assim ele faz a coleta dos dados da página e trata como um arquivo.

Não é a melhor forma de se fazer web scraping, por exemplo, pois você precisará entrar na página toda vez que quiser coletar as informações e isso demanda um pouco de tempo, não acha?

É aí que o web scraping Python entra, para automatizar esta tarefa!


Onde web scraping é usado?
O web scraping é usado em vários lugares e contextos, alguns deles estão na tarefa de algumas empresas.Como coletar preços e dados sobre o comércio eletrônico de uma concorrente para ajustar qual produto colocar em promoção e promover o marketing.

Os advogados também usam para ver relatórios e arquivos de julgamentos passados para estudar, visualizar ou até tratar esses dados da forma que eles precisarem.

Empresas de marketing também usam para coletar dados de perfis de pessoa para filtrar o público-alvo.

Empresas de mídia, como o Twitter, Facebook e Instagram, usam o web scraping Python para ver tópicos e os assuntos que estão em alta no momento.

Além de jornalistas que recolhem informações de alguma notícia, entrevista, relatório, reportagem.

O que é preciso para fazer um web scraping Python?
Para fazer um web scraping Python, obviamente vamos precisar do Python, mais especificamente a versão 3.

Iremos usar o pip para baixar as bibliotecas que iremos usar para fazer o web scraping Python, que serão elas: a Beautiful Soup, a biblioteca requests, e um editor de texto de sua preferência.

Python 3
Você pode encontrar o instalador do Python de acordo com o seu sistema operacional.

Pip
O pip vai servir para instalarmos as bibliotecas que iremos usar de uma forma fácil e rápida!

Requests
Para instalar a biblioteca que iremos usar para fazermos nossas requisições é a requests, você pode instalar-la facilmente com o pip com os seguintes comandos:

No Linux:

sudo pip install requests

No Windows:

Você tem que executar o cmd como administrador e usar o comando “pip install requests”.

Beautifulsoup
Por último, iremos instalar a biblioteca que iremos usar para fazer o web scraping Python, você pode instalar-la com o seguinte comando:

No Linux:

sudo pip install beautifulsoup 4

No Windows:

Execute o prompt de comando como administrador e instale-a com o comando pip install beautifulsoup 4 e, se tudo der certo, vai retornar algo parecido com a imagem a seguir:

O que você pode fazer com web scraping Python?
Você pode fazer muitas coisas com web scraping Python, neste artigo irei desenvolver um script bem simples que coleta dados e previsões do site do Climatempo como um exemplo prático.

Iremos tratar esses dados e ver qual a temperatura mínima e máxima de sua cidade, é bem simples e introdutório.

Ao longo do seu aprendizado, você pode adicionar mais e mais dados a este script para completar-lo. É interessante dispor de um tempo para o script ser executado periodicamente e também pegar dados todos os dias, por exemplo.

Depois de um mês executando diariamente, podemos tratar esses dados como: em qual semana choveu mais, em qual semana fez mais sol para depois fazer um gráfico.

Também é legal fazer um script com o web scraping Python que raspa o preço de produtos em promoção em um dia específico, ou até pegar preço de X produtos antes da Black Friday e ver os preços deles novamente para ver os descontos.

Você pode fazer isso e muito mais com o web scraping Python, é uma combinação poderosa com infinitas possibilidades.

Criando um web scraper do zero
Prontinho, já instalamos tudo o que iremos precisar e agora vamos criar um web scraper do zero usando o Python.

Primeiro, crie um arquivo com o nome que você preferir e com a extensão .py, abra-o com o seu editor de texto e cole o seguinte código:

from bs4 import BeautifulSoup

import requests

html = requests.get("https://www.climatempo.com.br/").content

soup = BeautifulSoup(html, 'html.parser')

print(soup.prettify())

Nestas linhas de código, estamos importanto as bibliotecas BeautifulSoup e requests nas duas primeiras linhas.

Na terceira estamos pegando todo o conteúdo de um requisição get na url do Clima tempo.

Na quarta e quinta linha é criado um objeto chamado soup que está interpretando o documento HTML.

Agora, execute-o no seu terminal ou prompt de comando com python nome-do-seu-arquivo.py e podemos ver que ele retornará todo o HTML da página.

Vai ser trabalhoso ler todo esse HTML até acharmos a informação que estamos procurando, nós vamos tratar e filtrar toda essa informação até o script retornar o que precisamos que, nesse caso, será a temperatura máxima e mínima.

temperatura = soup.find("span", class_="_block _margin-b-5 -gray")

print(temperatura.string)

Adicione estas duas últimas linhas ao final do arquivo e execute-o novamente.

Verá que vai retornar a temperatura máxima e mínima, o que está acontecendo neste código é que na primeira linha estamos procurando dentro do objeto do beautifulsoup definido mais acima, a temperatura mínima e máxima, “span “é a tag html, e “class_=” é a classe atribuída ao elemento.

Você pode ver a classe e o elemento apertando Ctrl+Shift+C ou Command+Shift+C em uma página HTML e selecionando com o mouse o elemento que quer raspar.

Em seguida, ele irá abrir ou na esquerda ou na direita um painel destacando o elemento selecionado, alguma coisa parecida com a imagem a seguir:

Após selecionar o texto que quer raspar basta achar o elemento pela identificação dele, seja id ou class, se for por id você pode encontrá-lo deste jeito: soup.find(id=”link3″), e na última linha de código estou mostrando na tela o texto cru deste elemento HTML, fácil né?
