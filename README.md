# Kotlin-7DaysOfCode
Repositorio destinado para o desafio de 7 dias para codificação de um projeto Kotlin

No segundo dia do desafio é habilitar o carregamento de uma imagem via protoloco HTTP



## Dia 2
E aí, Handerson Alves da Costa, conseguiu desenvolver o desafio do primeiro dia e já está tudo pronto para o próximo?

Só pra garantir, vou deixar sempre a minha resolução lá no final deste e-mail, beleza? Assim você pode comparar com a sua, mas não esqueça de compartilhar comigo as suas resoluções, quero ver também!
Hoje é o segundo dia do seu desafio #7DaysOfCode com Kotlin, bora praticar?

No primeiro dia, você criou a primeira tela do App que apresenta as informações de um filme. O resultado deve ter sido algo similar a este:

Para essa primeira amostra, você apresentou a imagem que era carregada diretamente do seu projeto. Porém, ao implementar uma aplicação que consome uma web API (nesse caso, com informações gerais dos filmes), você terá acesso às imagens dos pôsteres de cada filme a partir de um endereço HTTP!

Ou seja, o seu desafio hoje será carregar a imagem da capa do filme a partir de uma URL.

Existe mais de uma maneira de fazer isso, sendo que para a maioria delas será necessário baixar os bytes da imagem e converter para um tipo suportado, como é o caso do Bitmap. Em resumo, será necessário fazer o seguinte:

Usar um cliente HTTP para baixar a imagem;
Converter os dados recebidos em um InputStream;
Ler o InputStream e escrever em OutputStream, geralmente um array de bytes;
Codificar os bytes lidos para um tipo suportado para imagens;
Converter o tipo suportado para imagem em um tipo suportado pelo Compose, por exemplo, o Bitmap.

Ou seja, a sua tarefa será criar uma função que seja capaz de receber o endereço da imagem em String e devolver, por exemplo, um Bitmap compatível com o Compose. Daí, quando  o App for executado com o endereço da imagem, a mesma deverá ser carregada. Se preferir, você pode escrever essa implementação como uma extensão de String.

Ela vai ter uma cara mais ou menos assim:
```
@Composable
fun App() {
val image = "url da imagem"
MaterialTheme {
Column {
Text(...)
Image(
bitmap = image.loadImageBitmap(),
...
)
Text(...)
}
}
}

fun String.loadImageBitmap(): ImageBitmap {
val inputStream = ...
val bufferedImage = ...

     val stream = ...
     val byteArray = ...

     return Image.makeFromEncoded(byteArray).toComposeImageBitmap()
}
```
### DICA
Após obter o array de bytes a partir da leitura e escrita do buffer, você pode utilizar o método estático makeFromEncoded() da classe Image do pacote org.jetbrains.skia para codificar os bytes em um tipo de imagem suportado e, então, convertê-la para ImageBitmap, que é um tipo compatível com o Compose, a partir do método de extensão toComposeImageBitmap().

### EXTRA
Se preferir, você pode usar bibliotecas externas, seja para fazer o papel do cliente HTTP, ou então para fazer todo o processo, desde criar a conexão e baixar a imagem, como também para fazer o processo de leitura e escrita de buffer. Daí, depois, você pode simplesmente fazer a conversão para ImageBitmap, por exemplo.

Aqui vão algumas bibliotecas comuns para cliente HTTP:
Retrofit
Ktor

No Jetpack Compose existem algumas bibliotecas que facilitam essa implementação, como a Coil, Glide, Fresco etc. Porém, ambas estão restritas ao Jetpack! Caso encontre alguma outra e queira testar, fique à vontade também.