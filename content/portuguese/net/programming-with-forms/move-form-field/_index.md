---
title: Mover campo de formulário
linktitle: Mover campo de formulário
second_title: Referência da API do Aspose.PDF para .NET
description: Mova facilmente campos de formulário em seus documentos PDF com Aspose.PDF para .NET.
type: docs
weight: 200
url: /pt/net/programming-with-forms/move-form-field/
---
Neste tutorial, mostraremos como mover um campo de formulário em um documento PDF usando Aspose.PDF para .NET. Explicaremos o código-fonte C# passo a passo para guiá-lo por esse processo.

## Etapa 1: Preparação

Certifique-se de ter importado as bibliotecas necessárias e definido o caminho para o diretório de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: Carregue o documento

Carregue o documento PDF existente:

```csharp
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

## Etapa 3: Obtenha o campo do formulário

Obtenha o campo de formulário que você deseja mover:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Etapa 4: Alterar a localização do campo

Altere a localização do campo do formulário definindo uma nova área retangular:

```csharp
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
```

## Etapa 5: Salve o documento editado

Salve o documento PDF modificado:

```csharp
dataDir = dataDir + "MoveFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Código-fonte de exemplo para Mover campo de formulário usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
// Pegue um campo
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Modificar localização do campo
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
dataDir = dataDir + "MoveFormField_out.pdf";
// Salvar documento modificado
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

## Conclusão

Neste tutorial, aprendemos como mover um campo de formulário em um documento PDF usando o Aspose.PDF para .NET. Seguindo essas etapas, você pode navegar facilmente para um campo específico e alterar sua localização conforme necessário.


### Perguntas frequentes

#### P: Posso mover vários campos de formulário dentro de um único documento PDF usando o Aspose.PDF para .NET?

R: Sim, você pode mover vários campos de formulário dentro de um único documento PDF usando o Aspose.PDF para .NET. Basta repetir o processo para cada campo de formulário que você deseja realocar.

#### P: Mover um campo de formulário afetará seus dados ou funcionalidade associados?

R: Não, mover um campo de formulário não afeta seus dados ou funcionalidade associados. O campo de formulário retém todas as suas propriedades e valores após ser movido para um novo local.

#### P: Como posso determinar as coordenadas exatas para o novo local do campo do formulário?

 R: Você pode especificar o novo local usando o`Aspose.Pdf.Rectangle` classe, onde você define as coordenadas X e Y do canto superior esquerdo e as coordenadas X e Y do canto inferior direito da área retangular.

#### P: O Aspose.PDF para .NET é compatível com ambientes Windows e Linux?

R: Sim, o Aspose.PDF para .NET é compatível com ambientes Windows e Linux, oferecendo flexibilidade para que os desenvolvedores trabalhem em seus sistemas operacionais preferidos.