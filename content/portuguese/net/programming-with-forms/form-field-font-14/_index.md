---
title: Fonte do campo de formulário 14
linktitle: Fonte do campo de formulário 14
second_title: Referência da API do Aspose.PDF para .NET
description: Configure facilmente a fonte dos campos de formulário em seus documentos PDF com o Aspose.PDF para .NET.
type: docs
weight: 110
url: /pt/net/programming-with-forms/form-field-font-14/
---
Neste tutorial, mostraremos como configurar a fonte de um campo de formulário usando Aspose.PDF para .NET. Explicaremos o código-fonte C# passo a passo para guiá-lo por esse processo.

## Etapa 1: Preparação

Primeiro, certifique-se de ter importado as bibliotecas necessárias e definido o caminho para o diretório de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: Abra o documento

Abra o documento PDF existente:

```csharp
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
```

## Etapa 3: Obtenha um campo de formulário específico

Obtenha o campo de formulário desejado (neste exemplo, estamos usando o campo "textbox1"):

```csharp
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
```

## Etapa 4: Crie um objeto de fonte

Crie um objeto de fonte para a nova fonte que você deseja usar (por exemplo, "ComicSansMS"):

```csharp
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
```

## Etapa 5: Configurar informações de fonte para o campo de formulário

Configure as informações de fonte para o campo de formulário usando a fonte criada anteriormente:

```csharp
field.DefaultAppearance = new Aspose.Pdf.Forms.DefaultAppearance(font, 14, System.Drawing.Color.Black);
```

## Etapa 6: Salve o documento atualizado

Salve o documento PDF atualizado:

```csharp
dataDir = dataDir + "FormFieldFont14_out.pdf";
pdfDocument.Save(dataDir);
```


### Exemplo de código-fonte para Form Field Font 14 usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
// Obter campo de formulário específico do documento
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
// Criar objeto de fonte
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
// Defina as informações da fonte para o campo do formulário
// Campo.DefaultAppearance = novo Aspose.Pdf.Forms.in.DefaultAppearance(fonte, 10, Sistema.Desenho.Cor.Preto);
dataDir = dataDir + "FormFieldFont14_out.pdf";
// Salvar documento atualizado
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field font setup successfully.\nFile saved at " + dataDir);
```

## Conclusão

Neste tutorial, aprendemos como configurar a fonte de um campo de formulário usando o Aspose.PDF para .NET. Seguindo essas etapas, você pode facilmente especificar a fonte e o tamanho da fonte para campos de formulário em seus documentos PDF usando o Aspose.PDF.

### Perguntas frequentes

#### P: Posso usar qualquer fonte para campos de formulário no Aspose.PDF para .NET?

R: Sim, você pode usar qualquer fonte TrueType ou OpenType para campos de formulário no Aspose.PDF para .NET. Desde que a fonte esteja disponível e instalada no sistema ou acessível por meio do FontRepository, você pode usá-la para personalizar a aparência do texto do campo de formulário.

#### P: Como encontro as fontes disponíveis no Aspose.PDF para .NET?

 R: Para encontrar as fontes disponíveis no Aspose.PDF para .NET, você pode usar o`FontRepository.GetAvailableFonts()`método. Este método retorna uma matriz de fontes disponíveis que você pode usar para campos de formulário ou quaisquer outras operações relacionadas a texto em seu documento PDF.

#### P: Posso alterar o tamanho da fonte dos campos do formulário para qualquer valor?

R: Sim, você pode alterar o tamanho da fonte para campos de formulário para qualquer valor numérico positivo usando o Aspose.PDF para .NET. No entanto, é essencial garantir que o tamanho da fonte seja apropriado para o campo de formulário específico e não leve ao truncamento do texto ou à sobreposição com outros elementos no documento.

#### P: Posso alterar a cor da fonte dos campos do formulário?

R: Sim, você pode alterar a cor da fonte para campos de formulário usando Aspose.PDF para .NET. No código-fonte C# fornecido, a cor da fonte é definida como preta (`System.Drawing.Color.Black`), mas você pode personalizá-lo para qualquer outro valor de cor válido.

#### P: Como posso alinhar o texto dentro do campo do formulário?

 R: Para alinhar o texto dentro do campo do formulário, você pode usar o`Multiline`propriedade do campo de formulário e defina-a como true. Esta propriedade habilita texto multilinha dentro do campo de formulário, permitindo que você controle o alinhamento do texto com quebras de linha e retornos de carro.