---
title: Mesa de canto arredondado em documento PDF
linktitle: Mesa de canto arredondado em documento PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a criar uma tabela de cantos arredondados em um documento PDF usando o Aspose.PDF para .NET.
type: docs
weight: 190
url: /pt/net/programming-with-tables/rounded-corner-table/
---
Neste tutorial, nós o guiaremos passo a passo para criar uma tabela de canto arredondado em um documento PDF usando Aspose.PDF para .NET. Explicaremos o código-fonte C# fornecido e mostraremos como implementá-lo.

## Etapa 1: Criando a tabela
Primeiro, criaremos a tabela usando o seguinte código:

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Etapa 2: Configuração do estilo de canto arredondado
Em seguida, configuraremos o estilo de canto arredondado da tabela:

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## Etapa 3: Configuração da borda da tabela
Para dar à tabela uma borda de canto arredondada, precisamos criar um objeto BorderInfo e configurá-lo com os parâmetros apropriados:

```csharp
// Crie um objeto GraphInfo para definir a cor da borda
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

// Crie um objeto BorderInfo vazio
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

// Defina o raio da borda arredondada para 15
bInfo.RoundedBorderRadius = 15;

// Aplicar informações de borda à tabela
tab1.Border = bInfo;
```

### Exemplo de código-fonte para Rounded Corner Table usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
// Crie um objeto BorderInfo em branco
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
// Defina a borda como uma borda mais arredondada onde o raio do arredondamento seja 15
bInfo.RoundedBorderRadius = 15;
// Defina o estilo de canto da tabela como Redondo.
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// Defina as informações da borda da tabela
tab1.Border = bInfo;
```

## Conclusão
Parabéns! Agora você aprendeu como criar uma tabela de canto arredondado em um documento PDF usando o Aspose.PDF para .NET. Este guia passo a passo mostrou como configurar o estilo de canto arredondado e a borda da tabela. Agora você pode aplicar esse conhecimento aos seus próprios projetos.

### Perguntas frequentes sobre mesa de canto arredondado em documento PDF

#### P: Posso personalizar o raio dos cantos arredondados da mesa?

R: Sim, você pode personalizar o raio dos cantos arredondados da tabela modificando o valor do`bInfo.RoundedBorderRadius` propriedade no código-fonte C# fornecido. Basta definir o valor do raio desejado (em pontos) para obter a aparência de canto arredondado desejada.

#### P: Posso aplicar cantos arredondados a células individuais dentro da tabela?

R: Não, o estilo de canto arredondado é aplicado à tabela inteira como um todo. O Aspose.PDF para .NET atualmente não fornece suporte integrado para aplicar cantos arredondados a células individuais dentro da tabela.

#### P: Posso alterar a cor da borda do canto arredondado?

 R: Sim, você pode alterar a cor da borda do canto arredondado modificando o valor do`graph.Color` propriedade no código-fonte C#. Basta fornecer a cor desejada, como`Aspose.Pdf.Color.Red` ou qualquer outra representação de cor válida.

#### P: É possível aplicar diferentes estilos de canto (por exemplo, quadrado e arredondado) a diferentes tabelas no mesmo documento PDF?

R: Sim, é possível aplicar diferentes estilos de canto a diferentes tabelas dentro do mesmo documento PDF. Você pode criar várias tabelas e configurar seus estilos de canto individualmente com base em seus requisitos.

#### P: Posso ajustar a espessura da borda do canto arredondado?

 R: Sim, você pode ajustar a espessura da borda do canto arredondado modificando o`BorderInfo` propriedades do objeto no código-fonte C#. Por exemplo, você pode definir o`bInfo.Width` propriedade para ajustar a espessura da borda.