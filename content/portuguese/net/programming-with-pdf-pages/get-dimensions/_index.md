---
title: Obtenha as dimensões da página PDF
linktitle: Obtenha as dimensões da página PDF
second_title: Referência da API Aspose.PDF para .NET
description: Neste tutorial, explicamos como obter dimensões de páginas PDF e realizar manipulações usando Aspose.PDF for .NET. Etapas detalhadas são fornecidas para orientá-lo durante o processo.
type: docs
weight: 60
url: /pt/net/programming-with-pdf-pages/get-dimensions/
---
Neste tutorial, orientaremos você no processo passo a passo de obtenção das dimensões da página em um arquivo PDF usando Aspose.PDF for .NET. Explicaremos o código-fonte C# incluído e forneceremos um guia completo para ajudá-lo a entender e implementar esse recurso em seus próprios projetos. Ao final deste tutorial, você saberá como obter as dimensões de uma página em um arquivo PDF usando Aspose.PDF for .NET.

## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:

- Conhecimento básico da linguagem de programação C#
- Aspose.PDF for .NET instalado em seu ambiente de desenvolvimento

## Passo 1: Defina o diretório do documento
Primeiro, você precisa definir o caminho para o diretório de documentos. Este é o local onde seu arquivo PDF está localizado. Substitua "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho apropriado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passo 2: Abra o documento PDF
 Então você pode abrir o arquivo PDF usando o`Document` classe de Aspose.PDF. Certifique-se de especificar o caminho correto para o arquivo PDF.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Etapa 3: adicione uma página em branco (se necessário)
 Se o documento PDF já contém páginas, você pode ir para uma página existente usando o índice`1` (a primeira página tem índice 1). Caso contrário, você poderá adicionar uma nova página ao documento.

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## Etapa 4: obtenha as dimensões da página
 Agora você pode obter as dimensões da página usando o`GetPageRect()` método do`Page` objeto. Este método retorna um`Rectangle` objeto que contém as dimensões da página. Você pode acessar a largura e a altura usando o`Width` e`Height` propriedades.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## Etapa 5: gire a página
 Se quiser girar a página, você pode usar o`Rotate` propriedade do`Page`objeto. Neste exemplo, a página é girada 90 graus.

```csharp
page. Rotate = Rotate. on90;
```

## Etapa 6: obtenha as dimensões da página novamente
 Após a rotação da página, você pode obter as dimensões da página novamente usando o comando`GetPageRect()` método.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### Exemplo de código-fonte para obter dimensões usando Aspose.PDF para .NET 

```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Adiciona uma página em branco ao documento PDF
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
// Obtenha informações de altura e largura da página
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
// Girar a página em um ângulo de 90 graus
page.Rotate = Rotation.on90;
// Obtenha informações de altura e largura da página
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## Conclusão
Neste tutorial, aprendemos como obter as dimensões de uma página em um arquivo PDF usando Aspose.PDF for .NET. Seguindo as etapas fornecidas, você pode extrair facilmente as dimensões da página e realizar outras operações de manipulação de PDF. Aspose.PDF for .NET oferece grande flexibilidade para trabalhar com arquivos PDF e permite desenvolver soluções poderosas e personalizadas.

Sinta-se à vontade para explorar mais a documentação do Aspose.PDF para descobrir todos os recursos oferecidos por esta biblioteca.

### Perguntas frequentes sobre como obter dimensões de páginas em PDF

#### P: Como posso obter as dimensões de uma página específica em um arquivo PDF?

R: Para obter as dimensões de uma página específica em um arquivo PDF, você pode usar o`GetPageRect()` método do`Page` objeto em Aspose.PDF para .NET. Este método retorna um`Rectangle` objeto contendo as dimensões (largura e altura) da página.

####  P: O que o`GetPageRect(true)` method do in the provided C# source code?

 R: O`GetPageRect(true)` O método no código-fonte C# fornecido retorna as dimensões da página após aplicar qualquer rotação. Se a página for girada, o método retornará as dimensões da página girada, que podem ser diferentes das dimensões originais.

#### P: Posso obter as dimensões de todas as páginas do documento PDF usando Aspose.PDF for .NET?

 R: Sim, você pode obter as dimensões de todas as páginas do documento PDF iterando pelo`Pages` coleção do`Document` objeto e usando o`GetPageRect(true)` método para cada página.

#### P: Como posso determinar a orientação de uma página (retrato ou paisagem) com base nas suas dimensões?

R: Para determinar a orientação de uma página com base em suas dimensões, você pode comparar a largura e a altura da página. Se a largura for maior que a altura, a página estará na orientação paisagem, e se a altura for maior que a largura, a página estará na orientação retrato.

#### P: Posso modificar as dimensões de uma página usando Aspose.PDF for .NET?

 R: Sim, você pode modificar as dimensões de uma página no Aspose.PDF for .NET. Depois de obter o`Rectangle` objeto que representa as dimensões da página, você pode ajustar a largura e a altura conforme seus requisitos e, em seguida, aplicar as alterações à página.