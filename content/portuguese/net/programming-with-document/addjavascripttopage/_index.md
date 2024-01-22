---
title: Adicionar Java Script ao arquivo PDF
linktitle: Adicionar arquivo PDF Java Script
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como adicionar JavaScript a um arquivo PDF usando Aspose.PDF for .NET. Guia passo a passo com tutoriais de código para scripts em nível de documento e página.
type: docs
weight: 10
url: /pt/net/programming-with-document/addjavascripttopage/
---
Para adicionar JavaScript a um arquivo PDF, usaremos Aspose.PDF for .NET. Esta biblioteca oferece uma maneira simples e eficiente de trabalhar com arquivos PDF em aplicativos .NET. As etapas a seguir irão guiá-lo através do processo de adição de JavaScript a um arquivo PDF usando Aspose.PDF for .NET.

## Passo 1: Carregue o arquivo PDF

 A primeira etapa é carregar o arquivo PDF ao qual deseja adicionar JavaScript. Você pode fazer isso usando o`Document` classe fornecida por Aspose.PDF para .NET. O`Document` classe fornece métodos para carregar, salvar e manipular arquivos PDF.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carregar arquivos PDF existentes
Document doc = new Document(dataDir + "input.pdf");
```

## Etapa 2: adicionar JavaScript no nível do documento

Para adicionar JavaScript no nível do documento, usaremos o`JavascriptAction` classe fornecida por Aspose.PDF para .NET. Esta classe permite especificar a instrução JavaScript que deseja adicionar ao arquivo PDF.

```csharp
// Adicionando JavaScript no nível do documento
// Instancie JavascriptAction com a instrução JavaScript desejada
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Atribuir objeto JavascriptAction à ação desejada do Documento
doc.OpenAction = javaScript;
```

Neste tutorial, estamos adicionando uma instrução JavaScript que imprimirá o arquivo PDF com as opções especificadas quando o documento for aberto.

## Etapa 3: adicionar JavaScript no nível da página

 Para adicionar JavaScript no nível da página, usaremos o`JavascriptAction` classe e o`Actions` propriedade fornecida por Aspose.PDF para .NET. Esta propriedade permite especificar instruções JavaScript que serão executadas quando a página for aberta ou fechada.

```csharp
// Adicionando JavaScript no nível da página
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");
```

Neste tutorial, adicionamos instruções JavaScript que exibirão uma mensagem de alerta quando a página for aberta ou fechada.

## Etapa 4: salve o arquivo PDF

Depois de adicionar o JavaScript ao arquivo PDF, você precisa salvar o arquivo modificado. Você pode fazer isso usando o`Save` método fornecido pelo`Document` aula.

```csharp
dataDir = dataDir + "JavaScript-Added_out.pdf";
// Salvar documento PDF
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);
```

Este código salvará o arquivo PDF modificado no diretório especificado.

### Exemplo de código-fonte para adicionar Java Script à página usando Aspose.PDF para .NET

```csharp
            
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carregar arquivos PDF existentes
Document doc = new Document(dataDir + "input.pdf");

// Adicionando JavaScript no nível do documento
// Instancie JavascriptAction com instrução JavaScript desejada
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Atribuir objeto JavascriptAction à ação desejada do Documento
doc.OpenAction = javaScript;

// Adicionando JavaScript no nível da página
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");

dataDir = dataDir + "JavaScript-Added_out.pdf";
// Salvar documento PDF
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);     
```

## Conclusão

Neste artigo, explicamos como adicionar JavaScript a um arquivo PDF tanto no nível do documento quanto no nível da página usando Aspose.PDF for .NET. Fornecemos instruções passo a passo e incluímos o código-fonte completo para cada exemplo. Com esse conhecimento, você pode adicionar JavaScript aos seus arquivos PDF e personalizar seu comportamento de acordo com suas necessidades.


### Perguntas frequentes sobre como adicionar java script ao arquivo PDF

#### P: O que é Aspose.PDF para .NET?

R: Aspose.PDF for .NET é uma biblioteca poderosa que permite aos desenvolvedores trabalhar com arquivos PDF em aplicativos .NET. Ele oferece uma ampla gama de recursos para criar, modificar e manipular documentos PDF.

#### P: Posso adicionar JavaScript a um documento PDF usando Aspose.PDF for .NET?

R: Sim, o Aspose.PDF for .NET permite adicionar JavaScript ao nível do documento e ao nível da página de um arquivo PDF, permitindo criar documentos PDF dinâmicos e interativos.

#### P: Como carrego um arquivo PDF existente usando Aspose.PDF for .NET?

 R: Você pode carregar um arquivo PDF existente usando o`Document` classe e seus métodos, conforme mostrado no guia passo a passo.

#### P: Que tipos de ações JavaScript posso adicionar a um documento PDF?

R: Com Aspose.PDF for .NET, você pode adicionar uma ampla variedade de ações JavaScript, como impressão, mensagens de alerta, manipulação de campos de formulário e muito mais.

#### P: O Aspose.PDF for .NET é adequado para projetos comerciais?

R: Sim, Aspose.PDF for .NET é uma biblioteca confiável e robusta que é comumente usada em projetos comerciais para tarefas de manipulação e geração de PDF.

