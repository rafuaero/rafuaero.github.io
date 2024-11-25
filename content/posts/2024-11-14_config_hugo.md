+++
title = 'configurando o Hugo CMS'
date = 2024-11-14T20:18:34-03:00
tags = ['hugo']
categorias = ['tech nerd']
+++

## configurando um site em Hugo

Este post é para documentar o processo de configurar este sítio usando o gerenciador de sites estáticos [hugo](https://gohugo.io/)  e hospedá-lo no github.

Vamos ver como as coisas saem.

Escolhi hospedar no github porque eles oferecem uma versão gratuita de hospedagem já integrada a um repositório.

Escolhi o Hugo, porque me interessei pelo desafio, coisa de nerd, de configurar e aprender a usar mais um sistema, porque não?  


### da escolha do repositório
Da ultima vez que eu tentei fazer algo parecido, com Jekyll, eu li que para hospedar o site no github , com domínio próprio, o site de deveria estar direcionado para a pagina principal do usuário, o USUARIO.github.io

No pouco que li sobre o Hugo, não achei nada a respeito, mas vou testar primeiro nesse domínio para garantir o sucesso.

##### update
Parece que esse é um padrão para todo serviço hospedado no github.

## documentação
 vou começar por aqui:
 https://gohugo.io/getting-started/quick-start/

#### primeiro dia
1. eu clonei o diretório USUARIO.github.io para meu computador
2. depois teste o comando Hugo new site USUARIO.github.io
	1. deu erro, pois esse comando não aceita criar site sobre um diretório que já existe
	2. a mensagem de erro deu a opção de --force, vou testar
	3. deu certo, aparentemente
3. dei aqueles -- `git add commit push` -- de sempre, sem nem saber se era pra fazer isso agora.
4. A próxima etapa é definir o tema
	1. são vários no site, e provavelmente qualquer um que eu escolher vai deixar meu site com cara de template. 
		1. Mas aprender a configurar um tema vai ficar para bem depois
	2. de qualquer maneira, a página de [temas](https://themes.gohugo.io/) tem muita coisa legal e bonita, parabéns aos envolvidos
	3. fiquei na duvida entre o tema [mini](https://themes.gohugo.io/themes/hugo-theme-cactus-plus/) e o [pickles](https://themes.gohugo.io/themes/hugo_theme_pickles/),  e [cactus](https://themes.gohugo.io/themes/hugo-theme-cactus/)minimalistas no talo. 
	4. **Espero que seja fácil mudar de tema no futuro**
	5. Acabei decidindo por um chamado [Hugo Wiston](https://themes.gohugo.io/themes/hugo-winston-theme/) 
5. Testando as configurações
	1. instalei o tema
	2. criei o primeiro post
	3. Mas no apareceu na página inicial :-/
	4. vou ter que ler novamente sobre a instalação do tema

#### segundo dia
1. eu não segui as instruções de instalação do tema, para variar, e achei que a parte que pedia para copiar o site de exemplo era opcional, mas logo descobri que não era.
2. depois de copiado o site de exemplo, o post que eu havia criado apareceu.
	1. Começando a entender o funcionamento da pasta `content/` , aparentemente cada tema exige que o conteúdo fique em pastas específicas, sendo que `blog/` é padrão para vários temas que segue esse padrão de blog.
3. TODO: descobrir onde fica essas configurações no tema
4. Agora vou começar a mudar o site de exemplo para o meu conteúdo, vou lá e volta já

##### mudança de configuração
1.   quando eu rodo o servidor local hugo recebo a seguinte mensagem: `.Site.IsServer was deprecated in Hugo v0.120.0 and will be removed in a future release. Use hugo.IsServer instead.`
2. tenho que descobrir onde está essa config
3. usei o comando `grep -r 'Server' *` para achar as configurações (esse `-r` , de recursivo, que busca em pastas e subpastas, salva a vida em vários comandos bash) 
	1. estavam em themes/hugo-winston-theme/layouts/partials/google-analytics.html e hugo-winston-theme/layouts/partials/plausible-analytics.html
	2. corrigi e deu certo

#### terceiro dia
1. hoje vou continuar alterando o site de exemplo para meu gosto
2. As imagens ficam armazenadas na pasta `public/images`, pelo menos para esse tema
	1. na pagina about: está configurado da seguinte maneira:
		1. `url: "/about/"`
		2.  `image: images/about.jpg/
3. apanhando para descobrir como mudar a foto do autor
	1. achei um arquivo json, mas mudei a foto no pasta publica e nao foi, será que é outra pasta?
	2. aparentemente eu estava colocando as fotos na pasta `public/images`, eu acho que tenho que colocar na pasta `static/images` 
	3. ok, deu certo, estava colocando na pasta errada.
4. por hoje deu


#### quarto dia
1. decidi que não gostei do tema que escolhi, vou com outro
2. mas antes quero colocar o site no ar logo :-)
	1. vamos às pesquisas
		1. vou seguir a [documentação oficial](https://gohugo.io/hosting-and-deployment/hosting-on-github/)
		2. segui os passos da documentação
		3. deu certo
	2. meu site está no ar :-)
		1. [https://rafuaero.github.io/](https://rafuaero.github.io)/
	3. tem que fazer muito ajuste ainda

depois de começar a configurar o tema, [Hugo Wiston](https://themes.gohugo.io/themes/hugo-winston-theme/), percebi que não gostei dele, muito modernoso, não consegui achar fotos legais para colocar no lugar, e resolvi mudar para o tema "mini". 

1.  Mudei o tema localmente, só que esqueci de dar um git pull antes de fazer essas mudanças todas, pois quando se configura a hospedagem Hugo no github cria-se um arquivo de configuração no servidor, agora deu conflito nos commits
2. oh disgrama
3. mudei o tema e quebrou o host no github, vou ter que ver isso depois
4. tenho que terminar de configurar adequadamente o novo tema
	1. não é tão simples como parece
5. fim por hoje

#### quinto dia
1.  comecei tudo de novo
2.  apaguei o repositorio no github
3.  tive que refazer todos os procedimentos novamente de criar o repositório, configurar localmente o site e depois configurar no github
    1.  não vou mudar de tema tão cedo, prometo

e é isso por enquanto. Não vou mexer e nada muito complexo por agora, a idéia é começar a escrever logo.


