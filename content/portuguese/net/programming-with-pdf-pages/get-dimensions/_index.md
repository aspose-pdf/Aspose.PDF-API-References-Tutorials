---
title: Obter dimensões da página em PDF
linktitle: Obter dimensões da página em PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Neste tutorial, explicamos como obter dimensões de páginas em PDF e executar manipulações usando Aspose.PDF para .NET. Etapas detalhadas são fornecidas para guiá-lo pelo processo.
type: docs
weight: 60
url: /pt/net/programming-with-pdf-pages/get-dimensions/
---
Neste tutorial, vamos orientá-lo no processo passo a passo de obter dimensões de página em um arquivo PDF usando o Aspose.PDF para .NET. Explicaremos o código-fonte C# incluído e forneceremos um guia abrangente para ajudar você a entender e implementar esse recurso em seus próprios projetos. No final deste tutorial, você saberá como obter as dimensões de uma página em um arquivo PDF usando o Aspose.PDF para .NET.

## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:

- Um conhecimento básico da linguagem de programação C#
- Aspose.PDF para .NET instalado em seu ambiente de desenvolvimento

## Etapa 1: Defina o diretório do documento
Primeiro, você precisa definir o caminho para o diretório dos seus documentos. Este é o local onde seu arquivo PDF está localizado. Substitua "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho apropriado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: Abra o documento PDF
 Então você pode abrir o arquivo PDF usando o`Document` classe de Aspose.PDF. Certifique-se de especificar o caminho correto para o arquivo PDF.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Etapa 3: adicione uma página em branco (se necessário)
 Se o documento PDF já contiver páginas, você pode pular para uma página existente usando o índice`1` (a primeira página tem um índice de 1). Caso contrário, você pode adicionar uma nova página ao documento.

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## Etapa 4: Obtenha as dimensões da página
 Agora você pode obter as dimensões da página usando o`GetPageRect()` método do`Page` objeto. Este método retorna um`Rectangle` objeto contendo as dimensões da página. Você pode acessar a largura e a altura usando o`Width` e`Height` propriedades.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## Etapa 5: Gire a página
 Se você quiser girar a página, você pode usar o`Rotate` propriedade do`Page`objeto. Neste exemplo, a página é girada 90 graus.

```csharp
page. Rotate = Rotate. on90;
```

## Etapa 6: Obtenha as dimensões da página novamente
 Após a rotação da página, você pode obter as dimensões da página novamente usando o`GetPageRect()` método.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### Código-fonte de exemplo para Obter dimensões usando Aspose.PDF para .NET 

```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Adiciona uma página em branco ao documento PDF
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
// Obtenha informações sobre altura e largura da página
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
// Girar a página em um ângulo de 90 graus
page.Rotate = Rotation.on90;
// Obtenha informações sobre altura e largura da página
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## Conclusão
Neste tutorial, aprendemos como obter as dimensões de uma página em um arquivo PDF usando o Aspose.PDF para .NET. Seguindo as etapas fornecidas, você pode facilmente extrair as dimensões da página e executar outras operações de manipulação de PDF. O Aspose.PDF para .NET oferece grande flexibilidade para trabalhar com arquivos PDF e permite que você desenvolva soluções poderosas e personalizadas.

Sinta-se à vontade para explorar mais a documentação do Aspose.PDF para descobrir todos os recursos oferecidos por esta biblioteca.

### Perguntas frequentes sobre como obter dimensões de páginas em PDF

#### P: Como posso obter as dimensões de uma página específica em um arquivo PDF?

R: Para obter as dimensões de uma página específica em um arquivo PDF, você pode usar o`GetPageRect()` método do`Page` objeto em Aspose.PDF para .NET. Este método retorna um`Rectangle` objeto contendo as dimensões (largura e altura) da página.

####  P: O que o`GetPageRect(true)` method do in the provided C# source code?

 A: O`GetPageRect(true)` O método no código-fonte C# fornecido retorna as dimensões da página após aplicar quaisquer rotações. Se a página for rotacionada, o método retornará as dimensões da página rotacionada, que podem ser diferentes das dimensões originais.

#### P: Posso obter as dimensões de todas as páginas no documento PDF usando o Aspose.PDF para .NET?

 R: Sim, você pode obter as dimensões de todas as páginas no documento PDF iterando através do`Pages` coleção do`Document` objeto e usando o`GetPageRect(true)` método para cada página.

#### P: Como posso determinar a orientação de uma página (retrato ou paisagem) com base em suas dimensões?

R: Para determinar a orientação de uma página com base em suas dimensões, você pode comparar a largura e a altura da página. Se a largura for maior que a altura, a página está na orientação paisagem, e se a altura for maior que a largura, a página está na orientação retrato.

#### P: Posso modificar as dimensões de uma página usando o Aspose.PDF para .NET?

 R: Sim, você pode modificar as dimensões de uma página no Aspose.PDF para .NET. Após obter o`Rectangle` objeto que representa as dimensões da página, você pode ajustar a largura e a altura conforme suas necessidades e então aplicar as alterações à página.