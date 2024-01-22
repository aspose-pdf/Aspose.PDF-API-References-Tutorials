---
title: Definir borda em PDF para tabela
linktitle: Definir borda em PDF para tabela
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como definir uma borda em PDF para tabela com Aspose.PDF for .NET.
type: docs
weight: 200
url: /pt/net/programming-with-tables/set-border/
---
Neste tutorial, iremos guiá-lo passo a passo para definir uma borda em uma tabela de um documento PDF usando Aspose.PDF for .NET. Explicaremos o código-fonte C# fornecido e mostraremos como implementá-lo.

## Etapa 1: Instanciando o objeto Document
Primeiro, instanciaremos um objeto Document:

```csharp
Document doc = new Document();
```

## Passo 2: Adicionar uma página ao documento PDF
seguir, adicionaremos uma página ao documento PDF:

```csharp
Page page = doc.Pages.Add();
```

## Etapa 3: Criando o objeto BorderInfo
Criaremos agora um objeto BorderInfo para definir a borda da tabela:

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

## Etapa 4: especificar as bordas superior e inferior
Especificaremos que as bordas superior e inferior serão duplas:

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

## Etapa 5: Instanciando o objeto Tabela
Agora vamos instanciar um objeto Table:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Etapa 6: Especificando as larguras das colunas
Especificaremos as larguras das colunas da tabela:

```csharp
table. ColumnWidths = "100";
```

## Etapa 7: Criando o Objeto Linha
Criaremos um objeto Row:

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

## Etapa 8: adicionar uma célula à linha
A seguir, adicionaremos uma célula à linha:

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## Etapa 9: definir a borda da célula
Vamos definir a borda da célula (borda dupla):

```csharp
cell. Border = border;
```

## Etapa 10: Adicionando a tabela à página
Agora vamos adicionar a tabela à página do documento:

```csharp
page.Paragraphs.Add(table);
```

## Passo 11: Salve o documento PDF
Por fim, salvaremos o documento PDF:

```csharp
dataDir = dataDir + "TableBorderTest_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

### Exemplo de código-fonte para Set Border usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanciar objeto Document
Document doc = new Document();
// Adicionar página ao documento PDF
Page page = doc.Pages.Add();
// Criar objeto BorderInfo
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
//Especifique que a borda superior será dupla
border.Top.IsDoubled = true;
// Especifique que a borda inferior será dupla
border.Bottom.IsDoubled = true;
// Instanciar objeto Table
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Especifique informações de largura das colunas
table.ColumnWidths = "100";
// Criar objeto Linha
Aspose.Pdf.Row row = table.Rows.Add();
// Adicione uma célula da tabela à coleção de células da linha
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
// Defina a borda do objeto da célula (borda dupla)
cell.Border = border;
// Adicionar tabela à coleção de parágrafos da página
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
// Salve o documento PDF
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## Conclusão
Parabéns! Agora você aprendeu como definir uma borda em uma tabela de um documento PDF usando Aspose.PDF for .NET. Este guia passo a passo mostrou como criar um documento, adicionar uma página, configurar a borda da tabela e salvar o documento PDF. Agora você pode aplicar esse conhecimento em seus próprios projetos.

### Perguntas frequentes

#### P: Posso definir estilos de borda diferentes (por exemplo, tracejado ou pontilhado) para as bordas superior e inferior da tabela?

 R: Sim, você pode definir diferentes estilos de borda para as bordas superior e inferior da tabela, modificando o`border.Top.Style` e`border.Bottom.Style`propriedades no código-fonte C# fornecido. Aspose.PDF for .NET permite escolher entre vários estilos de borda, incluindo Sólido, Tracejado, Pontilhado, Duplo e muito mais.

#### P: Como posso definir a cor da borda da tabela?

 R: Você pode definir a cor da borda da tabela modificando o`border.Color` propriedade no código-fonte C#. Basta fornecer a cor desejada, como`Aspose.Pdf.Color.Red` ou qualquer outra representação de cores válida, para personalizar a cor da borda.

#### P: É possível aplicar bordas a células individuais da tabela com configurações diferentes (por exemplo, cores ou estilos de borda diferentes)?

 R: Sim, você pode aplicar bordas a células individuais da tabela com configurações diferentes, configurando o`cell.Border` propriedade para cada célula individualmente. Isso permite que você tenha estilos e cores de borda específicos para células com base em seus requisitos.

#### P: Posso remover as bordas de lados específicos da mesa (por exemplo, bordas esquerda e direita)?

 R: Sim, você pode remover a borda de lados específicos da mesa modificando o`border.Left`, `border.Right`, `border.Top` , e`border.Bottom`propriedades no código-fonte C#. Definir essas propriedades para`null` removerá a borda dos lados correspondentes da mesa.

#### P: Como posso ajustar a espessura da borda da mesa?

 R: Você pode ajustar a espessura da borda da tabela modificando o`border.Width` propriedade no código-fonte C#. Basta definir a largura desejada da borda (em pontos) para obter a espessura desejada.