---
title: Definir legenda do botão de opção
linktitle: Definir legenda do botão de opção
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como definir legendas de botões de opção em PDFs usando o Aspose.PDF para .NET. Este guia passo a passo orienta você a carregar, modificar e salvar seus formulários PDF.
type: docs
weight: 280
url: /pt/net/programming-with-forms/set-radio-button-caption/
---
## Introdução

Se você está mergulhando na manipulação de PDF com o Aspose.PDF para .NET, você está em uma surpresa! Hoje, estamos focando em um recurso prático: definir legendas de botões de opção em seus formulários PDF. Botões de opção são essenciais para formulários de usuário onde você precisa de uma escolha entre um conjunto de opções. Imagine-os como perguntas de múltipla escolha onde apenas uma resposta é permitida. Este tutorial irá guiá-lo pelo processo de atualização de legendas de botões de opção em um formulário PDF, para que seus documentos sejam interativos e fáceis de usar. 

## Pré-requisitos

Antes de mergulhar no código, há algumas coisas que você precisa garantir que tem:

1. Aspose.PDF para .NET: Certifique-se de ter a biblioteca Aspose.PDF instalada. Esta biblioteca ajudará você a manipular arquivos PDF programaticamente.
2. Ambiente de desenvolvimento: você deve ter um ambiente de desenvolvimento .NET configurado, como o Visual Studio.
3. Formulário PDF de amostra: para este tutorial, você precisará de um formulário PDF de amostra com botões de opção. Você pode usar qualquer formulário PDF existente ou criar um novo com botões de opção.
4. Conhecimento básico de C#: Este guia pressupõe que você tenha um conhecimento básico de conceitos de programação em C# e .NET.

 Se você ainda não instalou o Aspose.PDF para .NET ou precisa de uma licença temporária, você pode[baixe aqui](https://releases.aspose.com/pdf/net/) ou[obter uma licença temporária](https://purchase.aspose.com/temporary-license/).

## Pacotes de importação

Para começar, você precisa importar os pacotes necessários no seu projeto C#. Veja como incluir a biblioteca Aspose.PDF:

```csharp
using System;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
using Aspose.Pdf.Text;
```

Certifique-se de ter esses pacotes adicionados ao seu projeto via NuGet ou seu método preferido.

## Etapa 1: Carregue o formulário PDF

 Primeiro, você precisa carregar o formulário PDF que contém os botões de opção. O`Aspose.Pdf.Facades.Form`class é usada para esse propósito. Veja como fazer isso:

```csharp
// Defina o caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carregue o formulário PDF de origem
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
```

Neste trecho de código:
- `dataDir` especifica o caminho onde seu PDF está localizado.
- `Form` A classe é usada para interagir com os campos de formulário dentro do PDF.
- `Document` A classe fornece acesso às páginas do documento PDF.

## Etapa 2: iterar pelos campos de botão de opção

Em seguida, você precisará iterar pelos campos do seu formulário para identificar e manipular os campos dos botões de opção:

```csharp
foreach (var item in form1.FieldNames)
{
    Console.WriteLine(item.ToString());
    Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
```

Neste loop:
- `FieldNames` fornece uma lista de todos os nomes de campos no PDF.
- `GetButtonOptionValues(item)` recupera as opções disponíveis para cada botão de opção.

## Etapa 3: Modificar opções de botões de rádio

 Depois de identificar os campos do botão de opção, você pode modificar suas opções. Para isso, você precisa converter o campo para`RadioButtonField` e atualizar suas opções:

```csharp
    if (item.Contains("radio1"))
    {
        Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
        Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
        fieldoption.OptionName = "Yes";
        fieldoption.PartialName = "Yesname";
```

Aqui:
- Verificamos se o nome do campo contém "radio1" para identificar o campo de botão de opção específico que queremos modificar.
- `RadioButtonField`é lançado a partir dos campos do formulário para fazer modificações específicas.

## Etapa 4: Defina a legenda do botão de opção

 Para definir ou atualizar a legenda do botão de opção, você precisará criar um`TextFragment` e usar`TextBuilder` para colocá-lo no local desejado:

```csharp
        var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
        updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
        updatedFragment.TextState.FontSize = 10;
        updatedFragment.TextState.LineSpacing = 6.32f;

        // Criar objeto TextParagraph
        TextParagraph par = new TextParagraph();
        // Definir posição do parágrafo
        par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
        // Especificar modo de quebra de linha
        par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
        // Adicionar novo TextFragment ao parágrafo
        par.AppendLine(updatedFragment);
        // Adicione o TextParagraph usando o TextBuilder
        TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
        textBuilder.AppendParagraph(par);
```

Nesta parte:
- `TextFragment` é usado para definir o texto e sua aparência.
- `TextParagraph` ajuda a posicionar e formatar o texto.
- `TextBuilder` adiciona o texto à página especificada do PDF.

## Etapa 5: Salve o PDF atualizado

Por fim, salve o PDF atualizado em um novo arquivo:

```csharp
        field0.DeleteOption("item1");
    }
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Isso garantirá que:
- As alterações são aplicadas ao PDF.
- A opção de botão de opção original foi removida conforme especificado.

## Conclusão

Modificar legendas de botões de opção em um formulário PDF usando o Aspose.PDF para .NET pode melhorar muito a interatividade e a usabilidade dos seus documentos. Com as etapas descritas neste tutorial, você pode facilmente carregar um PDF, atualizar opções de botões de opção e salvar suas alterações. Essa abordagem é útil para gerenciamento de formulários e garante que seus PDFs atendam às necessidades exatas dos seus usuários. Mergulhe no Aspose.PDF e explore seus recursos para outras manipulações de PDF!

## Perguntas frequentes

### Posso atualizar vários campos de botão de opção de uma só vez?
Sim, você pode iterar por todos os campos de botões de opção e aplicar alterações conforme necessário.

### Preciso de uma licença para usar o Aspose.PDF?
 Você pode começar com uma avaliação gratuita, mas é necessária uma licença para uso prolongado.[Obtenha uma licença aqui](https://purchase.aspose.com/buy).

### Como posso testar as alterações antes de salvar o PDF?
Você pode visualizar o PDF no seu ambiente de desenvolvimento ou usar um visualizador de PDF para verificar as modificações.

### O Aspose.PDF é compatível com todas as versões do .NET?
Aspose.PDF suporta várias versões do .NET. Certifique-se de verificar a compatibilidade com sua versão específica do .NET.

### Posso manipular outros campos de formulário de forma semelhante?
Sim, técnicas semelhantes podem ser aplicadas a outros tipos de campos de formulário em documentos PDF.