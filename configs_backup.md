## configuracao do menu

  1 [menus]
  2   [[menus.main]]
  3     name = 'Home'
  4     pageRef = '/'
  5     weight = 10
  6
  7   [[menus.main]]
  8     name = 'Posts'
  9     pageRef = '/posts'
 10     weight = 20
 11
 12   [[menus.main]]
 13     name = 'tags'
 14     pageRef = '/tags'
 15     weight = 30
 16
 17 [[menus.main]]
 18     name = 'listas'
 19     pageref = '/listas'
 20     weight = 40


## configurando um menu

Se colocarmos esse codigo no head.html ele vai criar o menu baseado nos paramentros que eu passei
{{ partial "nav.html" . }}

para mais info ver aqui: https://harrycresswell.com/writing/menus-in-hugo/
