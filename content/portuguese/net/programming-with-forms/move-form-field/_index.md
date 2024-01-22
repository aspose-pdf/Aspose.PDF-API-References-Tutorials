---
title: Mover campo do formulário
linktitle: Mover campo do formulário
second_title: Referência da API Aspose.PDF para .NET
description: Mova facilmente os campos do formulário em seus documentos PDF com Aspose.PDF para .NET.
type: docs
weight: 200
url: /pt/net/programming-with-forms/move-form-field/
---
Neste tutorial, mostraremos como mover um campo de formulário em um documento PDF usando Aspose.PDF for .NET. Explicaremos o código-fonte C# passo a passo para guiá-lo neste processo.

## Etapa 1: Preparação

Certifique-se de importar as bibliotecas necessárias e definir o caminho para o diretório de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passo 2: Carregue o documento

Carregue o documento PDF existente:

```csharp
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

## Etapa 3: obtenha o campo do formulário

Obtenha o campo do formulário que deseja mover:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Etapa 4: alterar a localização do campo

Altere a localização do campo do formulário definindo uma nova área retangular:

```csharp
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
```

## Etapa 5: salve o documento editado

Salve o documento PDF modificado:

```csharp
dataDir = dataDir + "MoveFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Exemplo de código-fonte para Mover campo de formulário usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
// Obtenha um campo
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Modificar localização do campo
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
dataDir = dataDir + "MoveFormField_out.pdf";
// Salvar documento modificado
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

## Conclusão

Neste tutorial, aprendemos como mover um campo de formulário em um documento PDF usando Aspose.PDF for .NET. Seguindo essas etapas, você pode navegar facilmente até um campo específico e alterar sua localização conforme necessário.


### Perguntas frequentes

#### P: Posso mover vários campos de formulário em um único documento PDF usando Aspose.PDF for .NET?

R: Sim, você pode mover vários campos de formulário em um único documento PDF usando Aspose.PDF for .NET. Basta repetir o processo para cada campo do formulário que deseja realocar.

#### P: A movimentação de um campo de formulário afetará os dados ou funcionalidades associados?

R: Não, mover um campo de formulário não afeta os dados ou funcionalidades associados. O campo do formulário mantém todas as suas propriedades e valores após ser movido para um novo local.

#### P: Como posso determinar as coordenadas exatas do novo local do campo do formulário?

 R: Você pode especificar o novo local usando o`Aspose.Pdf.Rectangle` classe, onde você define as coordenadas X e Y do canto superior esquerdo e as coordenadas X e Y do canto inferior direito da área retangular.

#### P: O Aspose.PDF for .NET é compatível com ambientes Windows e Linux?

R: Sim, o Aspose.PDF for .NET é compatível com ambientes Windows e Linux, proporcionando flexibilidade para os desenvolvedores trabalharem em seus sistemas operacionais preferidos.