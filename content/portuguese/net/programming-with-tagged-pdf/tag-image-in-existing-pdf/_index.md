---
title: Marcar imagem em PDF existente
linktitle: Marcar imagem em PDF existente
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como marcar imagens em PDFs existentes usando o Aspose.PDF para .NET. Guia passo a passo para melhorar a acessibilidade com conformidade com PDF/UA.
type: docs
weight: 210
url: /pt/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
## Introdução

Neste tutorial, mostraremos como marcar uma imagem em um PDF existente usando o Aspose.PDF para .NET. Ao final deste guia, você poderá definir texto alternativo para imagens, ajustar atributos de layout e garantir que seu PDF esteja em conformidade com os padrões de acessibilidade.

## Pré-requisitos

Antes de começarmos, vamos ver o que você precisa para começar:

-  Aspose.PDF para .NET: certifique-se de ter baixado e instalado a versão mais recente do Aspose.PDF para .NET.[Baixe aqui](https://releases.aspose.com/pdf/net/).
- .NET Framework: certifique-se de ter um ambiente de desenvolvimento .NET, como o Visual Studio, configurado.
- Noções básicas sobre a estrutura do PDF: familiaridade com elementos da estrutura do PDF, como parágrafos, extensões, tabelas e imagens.
-  Uma licença válida: você pode comprar uma licença[aqui](https://purchase.aspose.com/buy) ou use um temporário[aqui](https://purchase.aspose.com/temporary-license/).

## Pacotes de importação

Para começar a codificar, você precisa importar os namespaces essenciais do Aspose.PDF para .NET. Eles darão a você acesso às classes e métodos necessários para manipular o documento PDF.

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Agora que definimos o cenário, vamos dividir o processo de marcação de uma imagem em várias etapas.

## Etapa 1: Carregue o documento PDF existente

O primeiro passo é carregar o arquivo PDF com o qual você quer trabalhar. Pode ser qualquer arquivo PDF com uma imagem que você queira marcar.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Abra o documento
Document document = new Document(inFile);
```

-  Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para seu arquivo.
-  O`Document` class permite que você carregue um PDF existente. Você modificará esse PDF para marcar a imagem.

## Etapa 2: Acesse o conteúdo marcado e o elemento de estrutura raiz

Depois de abrir o PDF, o próximo passo é acessar o conteúdo marcado e identificar o elemento da estrutura raiz. Isso é crucial, pois permite que você navegue pelos elementos no PDF e faça modificações.

```csharp
// Obtenha conteúdo marcado e elemento de estrutura raiz
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

- `TaggedContent` fornece acesso aos elementos estruturados no PDF.
-  O`RootElement` é o elemento estrutural mais alto, a partir do qual você pode navegar para outros elementos, como parágrafos, tabelas e imagens.

## Etapa 3: Defina o título do documento PDF marcado

Adicionar um título ao documento PDF marcado garante que seu documento seja rotulado corretamente, o que é útil para acessibilidade e conformidade com PDF/UA.

```csharp
// Definir título para o documento PDF marcado
taggedContent.SetTitle("Document with images");
```

- Definir um título para seu PDF marcado melhora a acessibilidade e melhora a clareza do documento para leitores de tela e tecnologias assistivas.

## Etapa 4: Encontre e marque a imagem

 Agora, vamos encontrar o elemento de imagem (chamado de`FigureElement` em Aspose.PDF), defina um texto alternativo para ele e configure seus atributos de layout.

```csharp
// Percorrer todos os elementos da Figura (imagens) e definir atributos alternativos de texto e layout
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
    // Definir texto alternativo para a figura
    figureElement.AlternativeText = "Figure alternative text (technique 2)";
    
    // Crie e defina o atributo BBox (caixa delimitadora)
    StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
    bboxAttribute.SetRectangleValue(new Aspose.Pdf.Rectangle(0.0, 0.0, 100.0, 100.0));
    
    // Definir atributos de layout para a figura
    StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
    figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

-  Este código percorre todos os`FigureElement` objetos na estrutura raiz, que representam imagens.
- Ele define o texto alternativo para acessibilidade (leitores de tela usarão isso para descrever a imagem).
- A caixa delimitadora (`BBox`especifica as coordenadas para o layout da imagem, garantindo que ela seja exibida corretamente no documento.

## Etapa 5: Modificar elementos de span dentro da tabela

 Em alguns casos, pode ser necessário modificar elementos span dentro de uma tabela. Aqui, demonstraremos como encontrar um`SpanElement` e movê-lo para um parágrafo.

```csharp
// Encontre os elementos de tabela, intervalo e parágrafo
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Mova o elemento span para o parágrafo
spanElement.ChangeParentElement(paragraph);
```

-  Aqui, localizamos o`TableElement`, `SpanElement` , e`ParagraphElement` dentro do PDF.
-  Usando o`ChangeParentElement` método, movemos o intervalo para o parágrafo para garantir marcação e estrutura adequadas.

## Etapa 6: Salve o documento e valide a conformidade com PDF/UA

Depois que todas as alterações forem feitas, a etapa final é salvar o PDF atualizado e verificar se ele está em conformidade com os padrões PDF/UA.

```csharp
// Salvar o documento PDF atualizado
document.Save(outFile);

// Validar a conformidade com PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

-  O`Validate` O método verifica o documento PDF em relação aos padrões PDF/UA e registra os resultados.
- Garantir a conformidade ajuda a melhorar a acessibilidade e atender aos requisitos regulatórios para publicação de documentos.

## Conclusão

Neste tutorial, mostramos como marcar imagens em um PDF existente usando o Aspose.PDF para .NET. Ao definir texto alternativo, ajustar atributos de layout e validar o documento para conformidade com PDF/UA, você pode garantir que seus PDFs sejam acessíveis e atendam aos padrões modernos. O Aspose.PDF facilita o trabalho com elementos estruturados, dando a você controle sobre o layout e a acessibilidade do seu documento.

## Perguntas frequentes

### Para que é usado o Aspose.PDF para .NET?
Aspose.PDF para .NET é uma biblioteca poderosa usada para criar, editar e manipular documentos PDF programaticamente em um ambiente .NET.

### Como posso garantir a conformidade com PDF/UA?
 Você pode usar o Aspose.PDF`Validate` método para verificar a conformidade do PDF/UA após fazer modificações no documento.

### O que é texto alternativo em PDFs?
Texto alternativo é uma descrição adicionada a imagens em PDFs para melhorar a acessibilidade, especialmente para usuários que dependem de leitores de tela.

### Posso manipular tabelas e intervalos em um PDF com Aspose.PDF?
Sim, o Aspose.PDF permite que você manipule tabelas, intervalos e outros elementos estruturados dentro de um documento PDF.

### Onde posso baixar o Aspose.PDF para .NET?
 Você pode baixar a versão mais recente do Aspose.PDF para .NET[aqui](https://releases.aspose.com/pdf/net/).