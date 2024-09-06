---
title: Botão de rádio
linktitle: Botão de rádio
second_title: Referência da API do Aspose.PDF para .NET
description: Adicione botões de opção facilmente aos seus documentos PDF com o Aspose.PDF para .NET.
type: docs
weight: 220
url: /pt/net/programming-with-forms/radio-button/
---
Neste tutorial, mostraremos como adicionar um botão de opção em um documento PDF usando Aspose.PDF para .NET. Explicaremos o código-fonte C# passo a passo para guiá-lo por esse processo.

## Etapa 1: Preparação

Certifique-se de ter importado as bibliotecas necessárias e definido o caminho para o diretório de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: Instanciar um objeto de documento

Instanciar um objeto Document para criar um novo documento PDF:

```csharp
Document pdfDocument = new Document();
```

## Etapa 3: Adicionar uma página

Adicione uma página ao documento PDF:

```csharp
pdfDocument.Pages.Add();
```

## Etapa 4: Instanciar um objeto RadioButtonField

Instanciar um objeto RadioButtonField especificando o número da página como um argumento:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Etapa 5: Adicionar opções de botão de opção

Adicione opções de botão de opção ao objeto RadioButtonField especificando as coordenadas de cada opção com um objeto Rectangle:

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## Etapa 6: adicione o botão de opção ao formulário

Adicione o botão de opção ao objeto Formulário do documento:

```csharp
pdfDocument.Form.Add(radio);
```

## Etapa 7: Salve o documento PDF

Salve o documento PDF criado:

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### Exemplo de código-fonte para botão de rádio usando Aspose.PDF para .NET 
```csharp
try
{
	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Instanciar objeto Document
	Document pdfDocument = new Document();
	// Adicionar uma página ao arquivo PDF
	pdfDocument.Pages.Add();
	// Instanciar objeto RadioButtonField com número de página como argumento
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Adicione a primeira opção de botão de opção e também especifique sua origem usando o objeto Rectangle
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// Adicionar segunda opção de botão de opção
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// Adicionar botão de opção ao objeto de formulário do objeto Documento
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "RadioButton_out.pdf";
	// Salvar o arquivo PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadio button field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusão

Neste tutorial, aprendemos como adicionar um botão de opção em um documento PDF usando o Aspose.PDF para .NET. Seguindo essas etapas, você pode facilmente criar um botão de opção e colocá-lo em uma página específica do seu documento PDF.


### Perguntas frequentes

#### P: Posso personalizar a aparência do botão de opção, como tamanho e cor?

 R: Sim, você pode personalizar a aparência do botão de opção usando o`Rectangle` coordenadas do objeto para definir seu tamanho e posição. O Aspose.PDF for .NET permite que você ajuste a aparência do botão de opção para atender às suas necessidades.

#### P: Posso adicionar vários botões de opção com grupos diferentes na mesma página?

R: Sim, você pode adicionar vários botões de opção com grupos diferentes na mesma página. Cada grupo de botões de opção pode ter um nome exclusivo, e apenas uma opção dentro de cada grupo pode ser selecionada por vez.

#### P: Como posso adicionar um rótulo ou uma descrição de texto às opções do botão de opção?

 R: Para adicionar um rótulo ou descrição de texto às opções do botão de opção, você pode usar o`TextStamp`classe do Aspose.PDF para .NET para sobrepor texto no documento PDF em coordenadas específicas.

#### P: O Aspose.PDF para .NET é compatível com todas as versões do .NET Framework?

R: Sim, o Aspose.PDF para .NET é compatível com todas as versões do .NET Framework, incluindo .NET Core e .NET Standard.

#### P: Posso controlar programaticamente a seleção de uma opção de botão de opção no documento PDF?

 R: Sim, você pode controlar programaticamente a seleção de uma opção de botão de rádio usando o`IsSelected` propriedade do`RadioButtonOption` classe. Esta propriedade permite que você defina uma opção específica como selecionada.