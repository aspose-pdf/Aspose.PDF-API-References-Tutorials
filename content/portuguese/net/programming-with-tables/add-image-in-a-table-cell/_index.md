---
title: Adicionar imagem em uma célula de tabela
linktitle: Adicionar imagem em uma célula de tabela
second_title: Referência da API Aspose.PDF para .NET
description: Adicione uma imagem em uma célula de tabela com Aspose.PDF for .NET, um guia passo a passo para manipulação precisa de imagens em documentos PDF.
type: docs
weight: 10
url: /pt/net/programming-with-tables/add-image-in-a-table-cell/
---
Neste tutorial, iremos guiá-lo através do processo de adição de uma imagem a uma célula de tabela usando Aspose.PDF for .NET. O código-fonte C# fornecido demonstra como obter essa funcionalidade. Seguindo as etapas descritas abaixo, você poderá incorporar imagens nas células da tabela de maneira eficaz.

Antes de mergulharmos no código, certifique-se de ter a biblioteca Aspose.PDF for .NET instalada e referenciada em seu projeto.

## Passo 1: Configurando o Documento

 Para começar, precisamos criar uma nova instância do`Document` classe do namespace Aspose.Pdf. Esta classe representa um documento PDF.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanciar um objeto Document
Document pdfDocument = new Document();
```

## Etapa 2: Criando uma página

A seguir, precisamos adicionar uma página ao documento PDF. Uma página serve como contêiner para a tabela e outros elementos.

```csharp
// Crie uma página no documento PDF
Page sec1 = pdfDocument.Pages.Add();
```

## Etapa 3: adicionar uma tabela

 Nesta etapa, criaremos uma tabela instanciando o`Table` classe do namespace Aspose.Pdf.

```csharp
// Instanciar um objeto de tabela
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Etapa 4: definir a borda da célula padrão

 Para garantir a consistência, podemos definir uma borda de célula padrão usando o comando`DefaultCellBorder`propriedade da tabela`BorderInfo` objeto.

```csharp
// Definir borda de célula padrão usando o objeto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Etapa 5: definir larguras de coluna

 Para definir a largura de cada coluna da tabela, podemos definir o`ColumnWidths` propriedade. Especifique as larguras como uma string com valores separados por espaço.

```csharp
// Definir com larguras de coluna da tabela
tab1.ColumnWidths = "100 100 120";
```

## Etapa 6: adicionar uma imagem a uma célula da tabela

Agora vem a parte interessante: adicionar uma imagem a uma célula da tabela. Para fazer isso, seguiremos estas subetapas:

## Etapa 6.1: Criando um objeto de imagem

 Crie uma instância do`Image` classe do namespace Aspose.Pdf. Colocou o`File` propriedade ao caminho do arquivo de imagem que você deseja adicionar.

```csharp
// Crie um objeto de imagem
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
```

## Etapa 6.2: Criando uma linha e células

Para adicionar a imagem à tabela, primeiro precisamos criar uma linha e as células necessárias.

```csharp
// Crie uma linha na tabela
Aspose.Pdf.Row row1 = tab1.Rows.Add();

// Adicione uma célula de texto à linha
row1.Cells.Add("Sample text in cell");

// Adicione a célula que contém a imagem
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
```

## Etapa 6.3: Adicionando a imagem à célula da tabela

Finalmente, podemos adicionar a imagem à célula da tabela adicionando-a como um parágrafo dentro da célula.

```csharp
// Adicione a imagem à célula da tabela
cell2.Paragraphs.Add(img);
```

## Etapa 6.4: Adicionando células adicionais

Depois de adicionar a célula da imagem, podemos adicionar mais células à linha, se necessário.

```csharp
//Adicione outra célula à linha
row1.Cells.Add("Previous cell with image");

// Ajuste o alinhamento vertical da terceira célula
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
```

## Etapa 7: salvando o documento

 Finalmente, podemos salvar o documento modificado em um local especificado usando o`Save` método.

```csharp
// Salve o documento
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

Parabéns! Você aprendeu com sucesso como adicionar uma imagem a uma célula de tabela usando Aspose.PDF for .NET. Sinta-se à vontade para explorar outras opções de personalização e integrar essa funcionalidade em seus projetos.

### Exemplo de código-fonte para adicionar imagem em uma célula de tabela usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanciar um objeto Document
Document pdfDocument = new Document();
// Crie uma página no documento PDF
Page sec1 = pdfDocument.Pages.Add();
// Instanciar um objeto de tabela
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Adicione a tabela na coleção de parágrafos da página desejada
sec1.Paragraphs.Add(tab1);
// Definir borda de célula padrão usando o objeto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Definir com larguras de coluna da tabela
tab1.ColumnWidths = "100 100 120";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
// Crie linhas na tabela e depois células nas linhas
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Sample text in cell");
// Adicione a célula que contém a imagem
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
// Adicione a imagem à célula da tabela
cell2.Paragraphs.Add(img);
row1.Cells.Add("Previous cell with image");
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
// Salve o documento
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

## Conclusão

Neste tutorial, abordamos um guia passo a passo sobre como adicionar uma imagem a uma célula de tabela usando Aspose.PDF for .NET. Começamos configurando o documento, criando uma página e adicionando uma tabela. Em seguida, definimos a borda da célula padrão e as larguras das colunas. Demonstramos como adicionar uma imagem a uma célula de tabela e ajustar o alinhamento vertical da célula. Finalmente, salvamos o documento modificado. Seguindo essas etapas, você pode aprimorar seus documentos PDF com imagens em células de tabela de forma eficiente.

### Perguntas frequentes

#### P: Posso adicionar várias imagens a células diferentes na mesma tabela usando Aspose.PDF for .NET?

R: Sim, você pode adicionar várias imagens a células diferentes na mesma tabela usando Aspose.PDF for .NET. Basta seguir o mesmo processo demonstrado no tutorial para cada imagem que deseja adicionar à tabela.

#### P: Posso personalizar o tamanho e a posição da imagem na célula da tabela?

 R: Sim, você pode personalizar o tamanho e a posição da imagem na célula da tabela ajustando as propriedades do`Image`objeto. Você pode definir a largura e a altura da imagem, bem como o alinhamento dentro da célula.

#### P: Posso adicionar imagens a uma tabela com um número dinâmico de linhas e colunas?

R: Sim, você pode adicionar imagens a uma tabela com um número dinâmico de linhas e colunas. Aspose.PDF for .NET oferece flexibilidade na criação de tabelas com dimensões variadas. Você pode adicionar linhas e células conforme necessário e, em seguida, adicionar imagens a células específicas de acordo.

#### P: Quais formatos de imagem são suportados pelo Aspose.PDF for .NET para adicionar imagens às células da tabela?

R: Aspose.PDF for .NET oferece suporte a uma ampla variedade de formatos de imagem, incluindo JPEG, PNG, GIF, BMP e TIFF. Você pode usar imagens de qualquer um desses formatos para adicioná-las às células da tabela.

#### P: Posso adicionar imagens a tabelas em um documento PDF existente?

R: Sim, você pode adicionar imagens a tabelas em um documento PDF existente usando Aspose.PDF for .NET. Basta carregar o documento existente e seguir os mesmos passos para adicionar imagens à tabela conforme demonstrado no tutorial.