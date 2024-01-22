---
title: Caixa de texto
linktitle: Caixa de texto
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como criar um campo de texto em um documento PDF usando Aspose.PDF for .NET.
type: docs
weight: 290
url: /pt/net/programming-with-forms/text-box/
---
Neste guia, explicaremos passo a passo como usar a biblioteca Aspose.PDF para .NET para criar um campo de texto em um documento PDF. Mostraremos como abrir o documento, criar o campo de texto, personalizar suas propriedades e salvar o PDF editado.

## Passo 1: Configurando o diretório do documento

 O primeiro passo é configurar o diretório do documento onde está localizado o arquivo PDF no qual você deseja trabalhar. Você pode usar o`dataDir` variável para especificar o caminho do diretório.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Certifique-se de substituir`"YOUR DOCUMENTS DIRECTORY"` com o caminho real para o diretório de documentos.

## Passo 2: Abrindo o documento PDF

Nesta etapa, abriremos o documento PDF usando o`Document` classe de Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "TextField.pdf");
```

Certifique-se de que o arquivo PDF esteja presente no diretório de documentos especificado.

## Etapa 3: Criando o campo de texto

 Criaremos um campo de texto usando o`TextBoxField` aula. Você pode especificar coordenadas de posição e tamanho do campo usando o`Rectangle` aula.

```csharp
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField. PartialName = "textbox1";
textBoxField.Value = "Text Field";
```

Personalize as coordenadas, tamanho, nome parcial e valor do campo de texto conforme necessário.

## Etapa 4: personalizar as propriedades do campo de texto

Nesta etapa, personalizaremos as propriedades do campo de texto, como borda, cor, etc.

```csharp
Border border = new Border(textBoxField);
border. width = 5;
border. Dash = new Dash(1, 1);
textBoxField. Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```

Personalize as propriedades do campo de texto de acordo com suas preferências.

## Passo 5: Adicionando o campo ao documento

Agora que criamos e configuramos o campo de texto, podemos adicioná-lo ao documento PDF.

```csharp
pdfDocument.Form.Add(textBoxField, 1);
```

## Passo 6: Salvando o PDF modificado

 Finalmente, podemos salvar o PDF modificado usando o`Save` método do`Document` aula.

```csharp
dataDir = dataDir + "TextBox_out.pdf";
pdfDocument.Save(dataDir);
```

Certifique-se de especificar o caminho completo e o nome do arquivo do PDF editado.

### Exemplo de código-fonte para caixa de texto usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "TextField.pdf");
// Crie um campo
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField.PartialName = "textbox1";
textBoxField.Value = "Text Box";
//TextBoxField.Border = nova Borda(
Border border = new Border(textBoxField);
border.Width = 5;
border.Dash = new Dash(1, 1);
textBoxField.Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
// Adicionar campo ao documento
pdfDocument.Form.Add(textBoxField, 1);
dataDir = dataDir + "TextBox_out.pdf";
// Salvar PDF modificado
pdfDocument.Save(dataDir);
Console.WriteLine("\nTextbox field added successfully.\nFile saved at " + dataDir);
```

## Conclusão

Neste guia, aprendemos como usar a biblioteca Aspose.PDF para .NET para criar um campo de texto em um documento PDF. Seguindo as etapas descritas, você pode personalizar as propriedades do campo de texto e adicioná-lo ao documento conforme necessário. Sinta-se à vontade para explorar ainda mais os recursos do Aspose.PDF for .NET para expandir as possibilidades de manipulação de arquivos PDF.

### Perguntas frequentes

#### P: Posso usar o Aspose.PDF for .NET para criar vários campos de texto em um único documento PDF?

R: Sim, você pode criar vários campos de texto em um único documento PDF usando Aspose.PDF for .NET. Basta repetir o processo de criação e personalização de campos de texto para cada local desejado no documento.

#### P: Como posso personalizar a aparência do campo de texto, como tamanho e cor da fonte?

R: Você pode personalizar a aparência do campo de texto ajustando suas propriedades, como tamanho da fonte, estilo da fonte, cor, estilo da borda, cor de fundo e muito mais. No código-fonte de amostra fornecido, a largura da borda, o padrão do traço da borda e a cor do texto são personalizados.

#### P: É possível extrair o texto inserido pelo usuário do campo de texto criado?

R: Sim, você pode extrair o texto inserido pelo usuário do campo de texto criado. Depois que os usuários preencherem o campo de texto no documento PDF, você poderá recuperar programaticamente o valor do campo usando Aspose.PDF for .NET.

#### P: Posso adicionar campos de texto a um documento PDF existente sem criar um novo?

R: Sim, você pode adicionar campos de texto a um documento PDF existente sem criar um novo. Aspose.PDF for .NET oferece a capacidade de modificar documentos PDF existentes, incluindo a adição de campos de texto, caixas de seleção e outros elementos de formulário.

#### P: O Aspose.PDF for .NET oferece suporte a outros tipos de campos de formulário, como caixas de seleção e botões de opção?

R: Sim, o Aspose.PDF for .NET oferece suporte a vários tipos de campos de formulário, incluindo caixas de seleção, botões de opção, listas suspensas e muito mais. Você pode usar a biblioteca para trabalhar com diferentes tipos de elementos de formulário em documentos PDF.