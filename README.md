# Kotlin-7DaysOfCode
Repositorio destinado para o desafio de 7 dias para codificação de um projeto Kotlin

## Dia 1

Chegou a hora, Handerson Alves da Costa! Você vai começar a sua jornada no #7DaysOfCode ;)

Este primeiro dia é super importante! Ao final dele, você terá um novo conhecimento que é essencial para os próximos desafios.

Muita gente na nossa área de tecnologia é fanática por cinema, séries e filmes. Por isso mesmo, o tema geral do nosso desafio vai ter tudo a ver com isso.

Você conhece o IMDB? É provavelmente a plataforma mais famosa que agrupa basicamente todos os filmes, séries, programas de TV, atores, etc., do mundo. Você pode imaginar que o banco de dados deles deve ser colossal!

No desafio de hoje, você vai fazer o seu código Kotlin rodar e apresentar uma tela com informações de um filme. O seu objetivo será criar um App Desktop que mostre as seguintes informações de um filme qualquer:
```
Título
Imagem do pôster
Nota
Ano
```
Como resultado, você deve apresentar uma aplicação similar a esta:

O filme escolhido acima é só um exemplo aleatório, você pode baixar uma imagem de pôster qualquer, apenas para desenvolver esse primeiro desafio.

Explicando melhor, você vai criar um projeto em Kotlin com o ambiente necessário para desenvolver uma aplicação desktop com interface gráfica.

Para isso, você pode usar o Compose Multiplatform, uma toolkit focada em desenhar telas.
(Se você ainda não souber muito bem, vou te explicar na seção 'Extra' como criar o projeto com o IntelliJ)

Após finalizar a criação, rode o projeto e confira se é apresentada uma janela em execução (o conteúdo da tela pode variar com a versão do IntelliJ que você utilizar). Se sim, você já será capaz de modificar o código de tela.

O código inicial está dentro da função main() em uma estrutura similar a esta:
```
@Composable
@Preview
fun App() {
    MaterialTheme {
        Column {
            Text(...)
            Image(
                ...
            )
            Text(...)
        }
    }
}

fun main() = application {
    Window(
        onCloseRequest = ::exitApplication
    ) {
        App()
    }
}
```

A função App() anotada com @Composable é a responsável por desenhar os componentes visuais, portanto, é dentro dela que você vai trabalhar!

Se for a sua primeira vez com o Compose, ele pode parecer complexo e de outro mundo, mas acredite, ele veio para simplificar a forma como você escreve telas em suas aplicações, e tenho certeza que você vai gostar dele 😄

Para esse primeiro desafio, faça tudo no arquivo Main.kt mesmo! Mais pra frente, você irá focar em outras tarefas para evoluir e organizar melhor o código.

Mais do que isso, divirta-se 😉

### DICA

Para desenhar um layout esperado, o Compose oferece alguns componentes básicos, como o Column e o Row. Boa parte dos layouts podem ser desenhados usando esses componentes básicos, você pode conferir alguns exemplos nesta página.

Para apresentar uma imagem, você pode usar o composable (funções do Compose que desenham a tela) chamado de Image. Para encontrar a imagem, você precisa salvá-la no diretório resources do seu código fonte: src/main/resources. Você pode utilizar este guia de apoio para adicionar uma imagem no seu projeto com Compose Desktop.

Composables possuem propriedades padrões para determinar altura e largura e você pode fazer essa modificação alterando a propriedade modifier via argumento. Nela, você pode enviar uma nova referência de Modifier, que permite realizar diversos ajustes no componente visual. Você pode conferir mais detalhes do Modifier nesta página.


### EXTRA
Para criar um projeto com suporte do Compose Desktop, você pode seguir este guia que ensina a criar o projeto com o IntelliJ a partir da versão 2020.3.

O Compose é uma ferramenta bastante adotada no mundo Android (conhecido como Jetpack Compose), ou seja, você pode usar boa parte do material da documentação do Android como apoio durante as suas pesquisas, como por exemplo, essa página focada para textos.

Por fim, se você quiser uma introdução maior do Compose, você pode conferir este Alura+ que explica o que é o Jetpack Compose, mesmo focando no Android, muitos dos conceitos são reaproveitados. Também, o Jetpack Compose Playground armazena diversos conteúdos com exemplos de implementação.
Ah, e não se esqueça de compartilhar o seu código no seu GitHub e marcar a gente nas suas redes sociais com a hashtag #7DaysOfCode, e também com #feedback7DoC caso você queira alguma ajuda.

Bom trabalho!

Alex Felipe
Tech Lead e instrutor na Alura
