---
title: Definir borda em PDF para tabela
linktitle: Definir borda em PDF para tabela
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como definir uma borda em PDF para tabela com Aspose.PDF para .NET.
type: docs
weight: 200
url: /pt/net/programming-with-tables/set-border/
---
Neste tutorial, nós o guiaremos passo a passo para definir uma borda em uma tabela de um documento PDF usando Aspose.PDF para .NET. Explicaremos o código-fonte C# fornecido e mostraremos como implementá-lo.

## Etapa 1: Instanciando o objeto Document
Primeiro, vamos instanciar um objeto Document:

```csharp
Document doc = new Document();
```

## Etapa 2: Adicionar uma página ao documento PDF
Em seguida, adicionaremos uma página ao documento PDF:

```csharp
Page page = doc.Pages.Add();
```

## Etapa 3: Criando o objeto BorderInfo
Agora criaremos um objeto BorderInfo para definir a borda da tabela:

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

## Etapa 4: Especificando bordas superior e inferior
Especificaremos que as bordas superior e inferior serão duplas:

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

## Etapa 5: Instanciando o objeto Table
Agora vamos instanciar um objeto Table:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Etapa 6: Especificando larguras de colunas
Especificaremos as larguras das colunas da tabela:

```csharp
table. ColumnWidths = "100";
```

## Etapa 7: Criando o objeto Row
Criaremos um objeto Row:

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

## Etapa 8: Adicionar uma célula à linha
Em seguida, adicionaremos uma célula à linha:

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## Etapa 9: Definindo a borda da célula
Vamos definir a borda da célula (borda dupla):

```csharp
cell. Border = border;
```

## Etapa 10: Adicionando a tabela à página
Agora vamos adicionar a tabela à página do documento:

```csharp
page.Paragraphs.Add(table);
```

## Etapa 11: Salvar documento PDF
Por fim, salvaremos o documento PDF:

```csharp
dataDir = dataDir + "TableBorderTest_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

### Exemplo de código-fonte para Definir Borda usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanciar objeto Document
Document doc = new Document();
// Adicionar página ao documento PDF
Page page = doc.Pages.Add();
// Criar objeto BorderInfo
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
//Especificar que a borda superior será dupla
border.Top.IsDoubled = true;
// Especificar que a borda inferior será dupla
border.Bottom.IsDoubled = true;
// Instanciar objeto Table
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Especificar informações de largura das colunas
table.ColumnWidths = "100";
// Criar objeto Row
Aspose.Pdf.Row row = table.Rows.Add();
// Adicionar uma célula de tabela à coleção de células de linha
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
// Definir a borda para o objeto de célula (borda dupla)
cell.Border = border;
// Adicionar tabela à coleção de parágrafos da página
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
// Salvar o documento PDF
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## Conclusão
Parabéns! Agora você aprendeu como definir uma borda em uma tabela de um documento PDF usando o Aspose.PDF para .NET. Este guia passo a passo mostrou como criar um documento, adicionar uma página, configurar a borda da tabela e salvar o documento PDF. Agora você pode aplicar esse conhecimento aos seus próprios projetos.

### Perguntas frequentes

#### P: Posso definir estilos de borda diferentes (por exemplo, tracejada ou pontilhada) para as bordas superior e inferior da tabela?

 R: Sim, você pode definir diferentes estilos de borda para as bordas superior e inferior da tabela modificando o`border.Top.Style` e`border.Bottom.Style`propriedades no código-fonte C# fornecido. O Aspose.PDF para .NET permite que você escolha entre vários estilos de borda, incluindo Sólido, Tracejado, Pontilhado, Duplo e muito mais.

#### P: Como posso definir a cor da borda da tabela?

 R: Você pode definir a cor da borda da tabela modificando o`border.Color` propriedade no código-fonte C#. Basta fornecer a cor desejada, como`Aspose.Pdf.Color.Red` ou qualquer outra representação de cor válida, para personalizar a cor da borda.

#### P: É possível aplicar bordas a células individuais dentro da tabela com configurações diferentes (por exemplo, cores ou estilos de borda diferentes)?

 R: Sim, você pode aplicar bordas a células individuais dentro da tabela com configurações diferentes, configurando o`cell.Border` propriedade para cada célula individualmente. Isso permite que você tenha estilos de borda e cores específicos para cada célula com base em seus requisitos.

#### P: Posso remover a borda de lados específicos da tabela (por exemplo, bordas esquerda e direita)?

 R: Sim, você pode remover a borda de lados específicos da tabela modificando o`border.Left`, `border.Right`, `border.Top` , e`border.Bottom`propriedades no código-fonte C#. Definir essas propriedades para`null` removerá a borda dos lados correspondentes da tabela.

#### P: Como posso ajustar a espessura da borda da tabela?

 R: Você pode ajustar a espessura da borda da tabela modificando a`border.Width` propriedade no código-fonte C#. Basta definir a largura da borda desejada (em pontos) para atingir a espessura desejada.