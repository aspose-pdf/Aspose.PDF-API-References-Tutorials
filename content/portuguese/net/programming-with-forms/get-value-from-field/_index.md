---
title: Obter valor do campo em documento PDF
linktitle: Obter valor do campo em documento PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Obtenha facilmente o valor de um campo de formulário em um documento PDF com Aspose.PDF para .NET.
type: docs
weight: 140
url: /pt/net/programming-with-forms/get-value-from-field/
---
Neste tutorial, mostraremos como obter o valor de um campo de formulário usando Aspose.PDF para .NET. Explicaremos o código-fonte C# passo a passo para guiá-lo por esse processo.

## Etapa 1: Preparação

Certifique-se de ter importado as bibliotecas necessárias e definido o caminho para o diretório de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: Abra o documento

Abra o documento PDF:

```csharp
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
```

## Etapa 3: Obter campo

Obtenha o campo de formulário desejado (neste exemplo, estamos usando o campo "textbox1"):

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Etapa 4: Obter valor do campo

 Obtenha o valor do campo usando o`Value` propriedade:

```csharp
Console.WriteLine("PartialName: {0}", textBoxField.PartialName);
Console.WriteLine("Value: {0}", textBoxField.Value);
```

### Código-fonte de exemplo para Obter valor do campo usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
// Pegue um campo
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Obter valor do campo
Console.WriteLine("PartialName : {0} ", textBoxField.PartialName);
Console.WriteLine("Value : {0} ", textBoxField.Value);
```

## Conclusão

Neste tutorial, aprendemos como obter o valor de um campo de formulário usando Aspose.PDF para .NET. Seguindo essas etapas, você pode facilmente extrair o valor de um campo de formulário específico em seus documentos PDF usando Aspose.PDF.

### Perguntas frequentes

#### P: Posso obter o valor de um campo de formulário sem saber seu nome de antemão?

 R: Não, você precisa saber o nome ou parte do nome do campo do formulário para obter seu valor usando Aspose.PDF para .NET. O`pdfDocument.Form["fieldname"]` a sintaxe requer o nome exato ou parcial do campo do formulário para acessar suas propriedades, incluindo o valor.

#### P: E se o campo de formulário não existir no documento PDF?

 R: Se o campo do formulário não existir no documento PDF, o`pdfDocument.Form["fieldname"]` a sintaxe retornará`null` . É essencial lidar com esses casos verificando`null` antes de acessar as propriedades do campo do formulário para evitar exceções.

#### P: Como posso manipular diferentes tipos de campos de formulário (por exemplo, caixas de seleção, botões de opção) para obter seus valores?

 A: Para lidar com diferentes tipos de campos de formulário, você pode usar as classes de campo apropriadas disponíveis no Aspose.PDF para .NET. Por exemplo, use`CheckBoxField` para trabalhar com caixas de seleção e`RadioButtonField`para trabalhar com botões de opção. Depois que você tiver o objeto de campo correto, você pode acessar suas propriedades, incluindo o valor.

#### P: Posso obter os valores de vários campos de formulário de uma só vez?

R: Sim, você pode obter os valores de vários campos de formulário de uma vez iterando pela coleção de campos de formulário usando um loop ou consultas LINQ. Dessa forma, você pode acessar o valor de cada campo de formulário no documento PDF programaticamente.

#### P: É possível modificar o valor de um campo de formulário e salvar as alterações no documento PDF?

 R: Sim, você pode modificar o valor de um campo de formulário usando Aspose.PDF para .NET e salvar as alterações de volta no documento PDF. Após atualizar o`Value` propriedade do campo de formulário, você pode usar o`pdfDocument.Save()` método para salvar as alterações no documento PDF original.