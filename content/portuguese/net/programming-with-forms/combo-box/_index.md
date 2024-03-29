---
title: Caixa combo
linktitle: Caixa combo
second_title: Referência da API Aspose.PDF para .NET
description: Crie facilmente uma lista de caixas de combinação em seus documentos PDF usando Aspose.PDF para .NET.
type: docs
weight: 30
url: /pt/net/programming-with-forms/combo-box/
---
Neste tutorial, mostraremos como criar uma lista de caixa de combinação usando Aspose.PDF para .NET. Explicaremos o código-fonte C# passo a passo para guiá-lo nesse processo.

## Etapa 1: Preparação

Primeiro, certifique-se de ter importado as bibliotecas necessárias e definido o caminho para o diretório de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: criar um objeto de documento

Crie um objeto Document para armazenar o formulário PDF:

```csharp
Document doc = new Document();
```

## Etapa 3: adicionar uma página

Adicione uma página ao documento:

```csharp
doc.Pages.Add();
```

## Etapa 4: instanciar um objeto ComboBoxField

Instancie um objeto ComboBoxField com as dimensões desejadas:

```csharp
ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
```

## Etapa 5: adicione opções à lista suspensa

Adicione as opções desejadas à lista suspensa:

```csharp
combo.AddOption("Red");
combo.AddOption("Yellow");
combo.AddOption("Green");
combo.AddOption("Blue");
```

## Etapa 6: adicione a lista da caixa de combinação ao formulário

Adicione o objeto ComboBoxField à coleção Document Form Fields:

```csharp
doc.Form.Add(combo);
```

## Etapa 7: salve o documento

Salve o documento PDF:

```csharp
dataDir = dataDir + "ComboBox_out.pdf";
doc.Save(dataDir);
```

### Exemplo de código-fonte para Combo Box usando Aspose.PDF para .NET 
```csharp
try
{
	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Criar objeto Documento
	Document doc = new Document();
	// Adicionar página ao objeto de documento
	doc.Pages.Add();
	// Instanciar objeto ComboBox Field
	ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
	// Adicionar opção ao ComboBox
	combo.AddOption("Red");
	combo.AddOption("Yellow");
	combo.AddOption("Green");
	combo.AddOption("Blue");
	// Adicionar objeto de caixa de combinação à coleção de campos de formulário do objeto de documento
	doc.Form.Add(combo);
	dataDir = dataDir + "ComboBox_out.pdf";
	// Salve o documento PDF
	doc.Save(dataDir);
	Console.WriteLine("\nCombobox field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusão

Neste tutorial, aprendemos como criar uma lista de caixa de combinação usando Aspose.PDF for .NET. Seguindo essas etapas, você pode adicionar facilmente uma lista de caixas de combinação aos seus documentos PDF usando Aspose.PDF.

### Perguntas frequentes

#### P: Posso personalizar a aparência da lista da caixa de combinação usando Aspose.PDF for .NET?

R: Sim, você pode personalizar a aparência da lista da caixa de combinação usando Aspose.PDF for .NET. Você pode definir propriedades como tamanho da fonte, cor, cor de fundo, estilo de borda e muito mais para combinar com a aparência desejada.

#### P: Posso definir opções padrão selecionadas na lista da caixa de combinação?

 R: Sim, você pode definir opções selecionadas padrão na lista da caixa de combinação usando Aspose.PDF para .NET. Você pode usar o`Selected` propriedade do`ComboBoxField` objeto para marcar uma ou mais opções como selecionadas por padrão.

#### P: Como posso recuperar o valor selecionado da lista da caixa de combinação depois que o usuário faz uma seleção?

 R: Você pode recuperar o valor selecionado da lista da caixa de combinação usando Aspose.PDF for .NET. Depois que o usuário fizer uma seleção, você poderá acessar o`Value` propriedade do`ComboBoxField`objeto para obter o valor selecionado.

#### P: É possível adicionar manipuladores de eventos ou ações à lista da caixa de combinação?

 R: Sim, o Aspose.PDF for .NET permite adicionar manipuladores de eventos ou ações à lista da caixa de combinação. Você pode associar ações JavaScript, como`OnValueChanged`, na lista da caixa de combinação para executar ações específicas quando o usuário seleciona uma opção.

#### P: Posso adicionar dicas de ferramentas ou descrições às opções da lista da caixa de combinação?

 R: Sim, você pode adicionar dicas de ferramentas ou descrições às opções na lista da caixa de combinação usando Aspose.PDF for .NET. Você pode definir o`AlternateName` propriedade de cada opção para fornecer uma dica de ferramenta ou descrição que será exibida quando o usuário passar o mouse sobre a opção.