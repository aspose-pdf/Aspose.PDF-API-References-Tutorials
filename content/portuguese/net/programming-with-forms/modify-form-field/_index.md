---
title: Modificar campo de formulário em documento PDF
linktitle: Modificar campo de formulário em documento PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Edite facilmente campos de formulário em documentos PDF com Aspose.PDF para .NET.
type: docs
weight: 190
url: /pt/net/programming-with-forms/modify-form-field/
---
Neste tutorial, mostraremos como editar um campo de formulário em um documento PDF usando Aspose.PDF para .NET. Explicaremos o código-fonte C# passo a passo para guiá-lo por esse processo.

## Etapa 1: Preparação

Certifique-se de ter importado as bibliotecas necessárias e definido o caminho para o diretório de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: Carregue o documento

Carregue o documento PDF existente:

```csharp
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
```

## Etapa 3: Obtenha o campo do formulário

Obtenha o campo de formulário que você deseja editar:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Etapa 4: Altere o valor do campo

Alterar o valor do campo do formulário:

```csharp
textBoxField.Value = "New Value";
```

## Etapa 5: Editar propriedades do campo

Modifique propriedades adicionais do campo de formulário conforme necessário. Por exemplo, você pode torná-lo somente leitura:

```csharp
textBoxField.ReadOnly = true;
```

## Etapa 6: Salve o documento editado

Salve o documento PDF modificado:

```csharp
dataDir = dataDir + "ModifyFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Código-fonte de exemplo para Modificar campo de formulário usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
// Pegue um campo
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Modificar valor do campo
textBoxField.Value = "New Value";
textBoxField.ReadOnly = true;
dataDir = dataDir + "ModifyFormField_out.pdf";
// Salvar documento atualizado
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field modified successfully.\nFile saved at " + dataDir);
```

## Conclusão

Neste tutorial, aprendemos como editar um campo de formulário em um documento PDF usando o Aspose.PDF for .NET. Seguindo essas etapas, você pode navegar facilmente para um campo específico, alterar seu valor e ajustar suas propriedades conforme necessário.


### Perguntas frequentes

#### P: Posso editar vários campos de formulário em um único documento PDF usando o Aspose.PDF para .NET?

R: Sim, você pode editar vários campos de formulário em um único documento PDF usando o Aspose.PDF for .NET. Basta repetir o processo para cada campo de formulário que você deseja modificar.

#### P: O Aspose.PDF para .NET é compatível com todas as versões do .NET Framework?

R: Sim, o Aspose.PDF para .NET é compatível com todas as versões do .NET Framework, incluindo .NET Core e .NET Standard.

#### P: Posso modificar outros tipos de campos de formulário, como caixas de seleção ou botões de opção, usando o Aspose.PDF para .NET?

R: Sim, o Aspose.PDF para .NET oferece suporte à modificação de vários tipos de campos de formulário, incluindo caixas de seleção, botões de opção e muito mais.

#### P: Como posso adicionar novos campos de formulário a um documento PDF usando o Aspose.PDF para .NET?

 R: Para adicionar novos campos de formulário a um documento PDF, você pode usar o`Form` propriedade do`Document` classe para acessar o`Field` coleção e, em seguida, adicionar novos campos de formulário programaticamente.

#### P: O Aspose.PDF para .NET oferece suporte a outras linguagens de programação além de C#?

R: Sim, o Aspose.PDF para .NET oferece suporte a várias linguagens de programação, como VB.NET e ASP.NET, além de C#.