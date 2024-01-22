---
title: Atualizar dimensões da página PDF
linktitle: Atualizar dimensões da página PDF
second_title: Referência da API Aspose.PDF para .NET
description: Guia passo a passo para atualizar as dimensões da página PDF usando Aspose.PDF for .NET. Verifique as dimensões de acordo com sua necessidade.
type: docs
weight: 150
url: /pt/net/programming-with-pdf-pages/update-dimensions/
---
Neste tutorial, orientaremos você no processo passo a passo para atualizar as dimensões da página em um documento PDF usando Aspose.PDF for .NET. Explicaremos o código-fonte C# incluído e forneceremos um guia completo para ajudá-lo a entender e implementar esse recurso em seus próprios projetos. Ao final deste tutorial, você saberá como alterar as dimensões da página em um documento PDF usando Aspose.PDF for .NET.

## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:

- Conhecimento básico da linguagem de programação C#
- Aspose.PDF for .NET instalado em seu ambiente de desenvolvimento

## Passo 1: Defina o diretório do documento
Primeiro, você precisa definir o caminho para o diretório de documentos. Este é o local onde você deseja salvar o documento PDF editado. Substitua "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho apropriado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passo 2: Abra o documento PDF
 Então você pode abrir o documento PDF existente usando o`Document` classe de Aspose.PDF. Certifique-se de especificar o caminho correto do documento.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Etapa 3: obtenha a coleção de páginas
 Agora você pode acessar a coleção de páginas do documento PDF usando o`Pages` propriedade do`Document` aula.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Etapa 4: obtenha uma página específica
Então você pode selecionar uma página específica do documento usando o índice da página na coleção. Neste exemplo, estamos usando a segunda página (índice 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Etapa 5: definir as novas dimensões da página
 Agora você pode definir o novo tamanho da página usando o`SetPageSize()` método do`Page`objeto. Neste exemplo, estamos definindo as dimensões da página como A4 (11,7 x 8,3 polegadas), convertidas em pontos (1 polegada = 72 pontos).

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## Etapa 6: salve o documento atualizado
 Finalmente, você pode salvar o documento PDF atualizado em um arquivo usando o`Save()` método do`Document`aula. Certifique-se de especificar o caminho e o nome do arquivo corretos.

```csharp
dataDir = dataDir + "UpdateDimensions_out.pdf";
pdfDocument.Save(dataDir);
```

### Exemplo de código-fonte para atualizar dimensões usando Aspose.PDF para .NET 

```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Obter coleção de páginas
PageCollection pageCollection = pdfDocument.Pages;
// Obtenha uma página específica
Page pdfPage = pageCollection[1];
// Defina o tamanho da página como A4 (11,7 x 8,3 pol.) E em Aspose.Pdf, 1 polegada = 72 pontos
// Portanto, as dimensões A4 em pontos serão (842,4, 597,6)
pdfPage.SetPageSize(597.6, 842.4);
dataDir = dataDir + "UpdateDimensions_out.pdf";
// Salve o documento atualizado
pdfDocument.Save(dataDir);
System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

```

## Conclusão
Neste tutorial, aprendemos como atualizar as dimensões de uma página em um documento PDF usando Aspose.PDF for .NET. Seguindo este guia passo a passo, você pode alterar facilmente as dimensões de uma página em um documento PDF conforme necessário. Aspose.PDF oferece uma API poderosa e flexível para trabalhar com arquivos PDF e realizar diversas manipulações, incluindo alteração das dimensões da página. Com esse conhecimento, você pode controlar e personalizar as dimensões das suas páginas PDF para atender às suas necessidades específicas.

### Perguntas frequentes sobre atualização de dimensões de páginas PDF

#### P: Como posso atualizar as dimensões de uma página específica em um documento PDF usando Aspose.PDF for .NET?

R: Para atualizar as dimensões de uma página específica em um documento PDF usando Aspose.PDF for .NET, você pode seguir estas etapas:

1. Defina o diretório do documento especificando o caminho onde o arquivo PDF original está localizado e onde você deseja salvar o arquivo PDF atualizado. Substitua "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho apropriado.
2.  Abra o documento PDF existente para atualizar usando o`Document` classe de Aspose.PDF. Certifique-se de especificar o caminho correto para o documento PDF original.
3.  Acesse a coleção de páginas do documento PDF usando o`Pages` propriedade do`Document` aula.
4. Selecione a página específica que deseja atualizar na coleção de páginas usando o índice da página. No código-fonte C# fornecido, estamos usando a segunda página (índice 1).
5.  Defina o novo tamanho da página usando o`SetPageSize()` método do`Page` objeto. No exemplo, definimos as dimensões da página para tamanho A4 (11,7 x 8,3 polegadas), convertidas em pontos (1 polegada = 72 pontos).
6.  Salve o documento PDF atualizado em um arquivo usando o`Save()` método do`Document`aula. Certifique-se de especificar o caminho e o nome do arquivo corretos.

#### P: Posso atualizar as dimensões de várias páginas do documento PDF simultaneamente?

R: Sim, você pode modificar o código-fonte fornecido para atualizar as dimensões de várias páginas do documento PDF simultaneamente. Em vez de selecionar uma página específica (como mostrado na etapa 4), você pode percorrer todas as páginas da coleção de páginas e definir o tamanho de página desejado para cada página.

#### P: Como faço para converter dimensões de página de polegadas para pontos ao usar Aspose.PDF para .NET?

 R: No Aspose.PDF for .NET, a unidade de medida usada para dimensões de página são pontos, onde 1 polegada equivale a 72 pontos. Para converter polegadas em pontos, você pode usar a fórmula:`points = inches * 72`. Por exemplo, para definir um tamanho de página de 11,7 x 8,3 polegadas, você pode calcular as dimensões correspondentes em pontos como (11,7 * 72) e (8,3 * 72).

#### P: A atualização das dimensões de uma página afetará o layout do conteúdo do documento PDF?

R: Sim, a atualização das dimensões de uma página afetará o layout do conteúdo do documento PDF nessa página específica. Quando você altera as dimensões da página, o conteúdo da página será ajustado de acordo para caber nas novas dimensões.

#### P: É possível reverter as alterações e restaurar as dimensões originais da página após atualizá-las?

R: Sim, se quiser reverter as alterações e restaurar as dimensões originais da página, você pode manter uma cópia do documento PDF original antes de fazer alterações ou reabrir o documento PDF original novamente sem salvar as alterações. Desta forma, as dimensões originais serão preservadas.