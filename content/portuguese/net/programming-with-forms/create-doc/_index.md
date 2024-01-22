---
title: Criar documento
linktitle: Criar documento
second_title: Referência da API Aspose.PDF para .NET
description: Crie facilmente um documento com botões de opção usando Aspose.PDF for .NET.
type: docs
weight: 40
url: /pt/net/programming-with-forms/create-doc/
---
Neste tutorial, mostraremos como criar um documento com botões de opção usando Aspose.PDF for .NET. Explicaremos o código-fonte C# passo a passo para guiá-lo nesse processo.

##Etapa 1: Preparação

Primeiro, certifique-se de ter importado as bibliotecas necessárias e definido o caminho para o diretório de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passo 2: Crie um novo documento

Crie um novo objeto Document para armazenar o documento PDF:

```csharp
Document doc = new Document();
```

## Etapa 3: adicionar uma página

Adicione uma nova página ao documento:

```csharp
Page page = doc.Pages.Add();
```

## Etapa 4: adicione um campo de botão de opção

Crie um campo de botão de opção e defina sua posição e tamanho:

```csharp
RadioButtonField field = new RadioButtonField(page);
field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
field. PartialName = "NewField";
```

## Etapa 5: adicionar opções de botão de opção

Adicione as opções desejadas ao campo do botão de opção. Você pode definir as coordenadas e o tamanho de cada opção conforme necessário:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
opt1.OptionName = "Item1";
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt2 = new RadioButtonOptionField();
opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
opt2.OptionName = "Item2";
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
opt3.OptionName = "Item3";
opt3.Border = new Border(opt3);
opt3.Border.Width = 1;
opt3.Characteristics.Border = System.Drawing.Color.Black;

field. Add(opt1);
field. Add(opt2);
field. Add(opt3);
```

## Etapa 6: adicione o campo do botão de opção ao formulário

Adicione o campo do botão de opção à coleção Document Form Fields:

```csharp
doc.Form.Add(field);
```

## Etapa 7: salve o documento

Salve o documento PDF:

```csharp
dataDir = dataDir + "CreateDoc_out.pdf";
doc.Save(dataDir);
```

### Exemplo de código-fonte para Create Doc usando Aspose.PDF para .NET 
```csharp
try
{
	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Crie um novo documento
	Document doc = new Document();
	Page page = doc.Pages.Add();
	// Adicionar campo de botão de opção
	RadioButtonField field = new RadioButtonField(page);
	field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
	field.PartialName = "NewField";
	// Adicione opções de botão de opção. observe que essas opções estão situadas
	// Nem horizontalmente nem verticalmente.
	// Você pode tentar definir quaisquer coordenadas (e até mesmo tamanho) para eles.
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
	opt1.OptionName = "Item1";
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
	opt2.OptionName = "Item2";
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
	opt3.OptionName = "Item3";
	opt3.Border = new Border(opt3);
	opt3.Border.Width = 1;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	field.Add(opt1);
	field.Add(opt2);
	field.Add(opt3);
	doc.Form.Add(field);
	dataDir = dataDir + "CreateDoc_out.pdf";
	// Salve o documento PDF
	doc.Save(dataDir);
	Console.WriteLine("\nNew doc with 3 items radio button created successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusão

Neste tutorial, aprendemos como criar um documento com botões de opção usando Aspose.PDF for .NET. Seguindo essas etapas, você pode adicionar facilmente botões de opção aos seus documentos PDF usando Aspose.PDF.

### Perguntas frequentes

#### P: Posso personalizar a aparência dos botões de opção no documento usando Aspose.PDF for .NET?

R: Sim, você pode personalizar a aparência dos botões de opção no documento usando Aspose.PDF for .NET. Você pode definir propriedades como tamanho, cor, estilo de borda e muito mais para personalizar a aparência dos botões de opção.

#### P: Como posso adicionar grupos de botões de opção com opções mutuamente exclusivas?

R: Para criar opções mutuamente exclusivas, você pode adicionar vários campos de botão de opção com o mesmo nome. Isso garantirá que quando uma opção for selecionada, as outras opções com o mesmo nome serão automaticamente desmarcadas.

#### P: É possível definir uma opção padrão selecionada para os botões de opção?

R: Sim, você pode definir uma opção selecionada padrão para os botões de opção usando Aspose.PDF for .NET. Você pode usar o`Selected` propriedade do`RadioButtonOptionField` objeto para marcar uma opção como selecionada por padrão.

#### P: Posso adicionar manipuladores de eventos aos botões de opção?

 R: Sim, você pode adicionar manipuladores de eventos aos botões de opção usando Aspose.PDF for .NET. Você pode associar ações JavaScript, como`OnValueChanged`, aos botões de opção para executar ações específicas quando o usuário seleciona uma opção.

#### P: Como posso recuperar a opção selecionada do grupo de botões de opção depois que o usuário faz uma seleção?

 R: Você pode recuperar a opção selecionada do grupo de botões de opção usando Aspose.PDF for .NET. Depois que o usuário fizer uma seleção, você poderá acessar o`Selected` propriedade do`RadioButtonOptionField` objeto para verificar qual opção está selecionada.