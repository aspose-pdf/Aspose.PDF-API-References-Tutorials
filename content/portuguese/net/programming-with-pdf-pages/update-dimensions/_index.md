---
title: Atualizar dimensões da página PDF
linktitle: Atualizar dimensões da página PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Guia passo a passo para atualizar as dimensões de páginas em PDF usando Aspose.PDF para .NET. Verifique as dimensões de acordo com suas necessidades.
type: docs
weight: 150
url: /pt/net/programming-with-pdf-pages/update-dimensions/
---
Neste tutorial, nós o guiaremos pelo processo passo a passo para atualizar as dimensões da página em um documento PDF usando o Aspose.PDF para .NET. Explicaremos o código-fonte C# incluído e forneceremos um guia abrangente para ajudar você a entender e implementar esse recurso em seus próprios projetos. No final deste tutorial, você saberá como alterar as dimensões da página em um documento PDF usando o Aspose.PDF para .NET.

## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:

- Um conhecimento básico da linguagem de programação C#
- Aspose.PDF para .NET instalado em seu ambiente de desenvolvimento

## Etapa 1: Defina o diretório do documento
Primeiro, você precisa definir o caminho para o diretório dos seus documentos. Este é o local onde você quer salvar seu documento PDF editado. Substitua "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho apropriado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: Abra o documento PDF
 Em seguida, você pode abrir o documento PDF existente usando o`Document` classe de Aspose.PDF. Certifique-se de especificar o caminho correto do documento.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Etapa 3: Obtenha a coleção de páginas
 Agora você pode acessar a coleção de páginas do documento PDF usando o`Pages` propriedade do`Document` aula.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Etapa 4: Obtenha uma página específica
Então você pode selecionar uma página específica do documento usando o índice da página na coleção. Neste exemplo, estamos usando a segunda página (índice 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Etapa 5: Defina as novas dimensões da página
 Agora você pode definir o novo tamanho da página usando o`SetPageSize()` método do`Page`objeto. Neste exemplo, estamos definindo as dimensões da página para A4 (11,7 x 8,3 polegadas), convertidas em pontos (1 polegada = 72 pontos).

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## Etapa 6: Salve o documento atualizado
 Por fim, você pode salvar o documento PDF atualizado em um arquivo usando o`Save()` método do`Document`classe. Certifique-se de especificar o caminho e o nome do arquivo corretos.

```csharp
dataDir = dataDir + "UpdateDimensions_out.pdf";
pdfDocument.Save(dataDir);
```

### Exemplo de código-fonte para Atualizar Dimensões usando Aspose.PDF para .NET 

```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Obter coleção de páginas
PageCollection pageCollection = pdfDocument.Pages;
// Obter página específica
Page pdfPage = pageCollection[1];
// Defina o tamanho da página como A4 (11,7 x 8,3 pol.) e em Aspose.Pdf, 1 polegada = 72 pontos
// Portanto, as dimensões do A4 em pontos serão (842,4, 597,6)
pdfPage.SetPageSize(597.6, 842.4);
dataDir = dataDir + "UpdateDimensions_out.pdf";
// Salvar o documento atualizado
pdfDocument.Save(dataDir);
System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

```

## Conclusão
Neste tutorial, aprendemos como atualizar as dimensões de uma página em um documento PDF usando o Aspose.PDF para .NET. Seguindo este guia passo a passo, você pode facilmente alterar as dimensões de uma página em um documento PDF conforme necessário. O Aspose.PDF oferece uma API poderosa e flexível para trabalhar com arquivos PDF e executar várias manipulações, incluindo a alteração das dimensões da página. Com esse conhecimento, você pode controlar e personalizar as dimensões das suas páginas PDF para atender às suas necessidades específicas.

### Perguntas frequentes sobre atualização das dimensões da página PDF

#### P: Como posso atualizar as dimensões de uma página específica em um documento PDF usando o Aspose.PDF para .NET?

R: Para atualizar as dimensões de uma página específica em um documento PDF usando o Aspose.PDF para .NET, você pode seguir estas etapas:

1. Defina o diretório do documento especificando o caminho onde seu arquivo PDF original está localizado e onde você deseja salvar o arquivo PDF atualizado. Substitua "YOUR DOCUMENTS DIRECTORY" pelo caminho apropriado.
2.  Abra o documento PDF existente para atualizar usando o`Document` classe de Aspose.PDF. Certifique-se de especificar o caminho correto para o documento PDF original.
3.  Acesse a coleção de páginas do documento PDF usando o`Pages` propriedade do`Document` aula.
4. Selecione a página específica que você deseja atualizar da coleção de páginas usando o índice da página. No código-fonte C# fornecido, estamos usando a segunda página (índice 1).
5.  Defina o novo tamanho da página usando o`SetPageSize()` método do`Page` objeto. No exemplo, definimos as dimensões da página para o tamanho A4 (11,7 x 8,3 polegadas), convertido em pontos (1 polegada = 72 pontos).
6.  Salve o documento PDF atualizado em um arquivo usando o`Save()` método do`Document`classe. Certifique-se de especificar o caminho e o nome do arquivo corretos.

#### P: Posso atualizar as dimensões de várias páginas no documento PDF simultaneamente?

R: Sim, você pode modificar o código-fonte fornecido para atualizar as dimensões de várias páginas no documento PDF simultaneamente. Em vez de selecionar uma página específica (como mostrado na etapa 4), você pode percorrer todas as páginas na coleção de páginas e definir o tamanho de página desejado para cada página.

#### P: Como faço para converter dimensões de página de polegadas para pontos ao usar o Aspose.PDF para .NET?

 R: No Aspose.PDF para .NET, a unidade de medida usada para dimensões de página é pontos, onde 1 polegada é equivalente a 72 pontos. Para converter polegadas em pontos, você pode usar a fórmula:`points = inches * 72`. Por exemplo, para definir um tamanho de página de 11,7 x 8,3 polegadas, você pode calcular as dimensões correspondentes em pontos como (11,7 * 72) e (8,3 * 72).

#### P: A atualização das dimensões de uma página afetará o layout do conteúdo do documento PDF?

R: Sim, atualizar as dimensões de uma página afetará o layout de conteúdo do documento PDF naquela página específica. Quando você altera as dimensões da página, o conteúdo na página será ajustado de acordo para caber dentro das novas dimensões.

#### P: É possível reverter as alterações e restaurar as dimensões originais da página depois de atualizá-las?

R: Sim, se você quiser reverter as alterações e restaurar as dimensões originais da página, você pode manter uma cópia do documento PDF original antes de fazer alterações ou reabrir o documento PDF original novamente sem salvar as alterações. Dessa forma, as dimensões originais serão preservadas.