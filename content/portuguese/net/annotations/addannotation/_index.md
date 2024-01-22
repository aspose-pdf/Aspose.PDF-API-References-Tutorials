---
title: Adicionar anotação em PDF
linktitle: Adicionar anotação
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como adicionar anotações de texto em PDF com Aspose.PDF for .NET usando este código-fonte C#. Personalize suas anotações com detalhes e ícones específicos.
type: docs
weight: 10
url: /pt/net/annotations/addannotation/
---
Adicionar anotações a documentos PDF é um recurso poderoso que pode aprimorar os processos de colaboração e revisão. Aspose.PDF for .NET facilita a adição de anotações programaticamente a documentos PDF usando C#. Neste guia, explicaremos passo a passo como usar Aspose.PDF for .NET para adicionar anotações a um documento PDF.

## Etapa 1: Crie um novo projeto e instale Aspose.PDF para .NET

Antes de começarmos a escrever o código para adicionar anotações, precisamos criar um novo projeto e instalar o Aspose.PDF for .NET. Para instalar o Aspose.PDF para .NET, siga estas etapas:

1. Abra o Visual Studio e crie um novo projeto C#.
2. Clique com o botão direito no projeto no Solution Explorer e selecione "Gerenciar pacotes NuGet".
3. Procure por "Aspose.PDF" e selecione "Instalar".

Assim que a instalação for concluída, podemos começar a escrever o código.

## Passo 2: Abra o documento PDF

A primeira etapa para adicionar anotações é abrir o documento PDF. Podemos usar o seguinte código para abrir o documento:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");
```

Neste código, especificamos o caminho para o documento PDF que queremos abrir. Certifique-se de substituir "SEU DIRETÓRIO DE DADOS" pelo caminho real para seu diretório de dados.

## Etapa 3: crie a anotação

 Para adicionar uma anotação, precisamos criar uma nova instância do`TextAnnotation` aula. Podemos usar o seguinte código para criar uma nova anotação de texto:

```csharp
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;
```

Neste código, criamos uma nova anotação de texto na segunda página do documento PDF. Também definimos as propriedades de título, assunto, estado, conteúdo, abertura e ícone da anotação.

## Etapa 4: personalize a anotação

 Podemos personalizar a aparência da anotação usando o`Border` aula. Podemos usar o seguinte código para personalizar a borda da anotação:

```csharp
Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
```

 Neste código, criamos um novo`Border`objeto e definir suas propriedades de largura e traço. Definimos então o`Border` propriedade da anotação para o novo`Border` objeto. Por fim, definimos o`Rect` propriedade da anotação para especificar sua posição e tamanho.

## Etapa 5: adicione a anotação ao documento PDF

Depois de criar e personalizar a anotação, precisamos adicioná-la ao documento PDF. Podemos usar o seguinte código para adicionar a anotação ao documento PDF:

```csharp
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

Neste código, adicionamos a anotação à coleção de anotações da segunda página do documento PDF.

## Etapa 6: salve o arquivo de saída

Finalmente, precisamos salvar o documento PDF com a anotação adicionada. Podemos usar o seguinte código para salvar o arquivo de saída:

```csharp
dataDir = dataDir + "AddAnnotation_out.pdf";
pdfDocument.Save(dataDir);
```
### Exemplo de código-fonte para adicionar anotação usando Aspose.PDF para .NET


```csharp   
 // O caminho para o diretório de documentos.
string dataDir = "YOUR DATA DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");

// Criar anotação
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;

Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);

// Adicionar anotação na coleção de anotações da página
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddAnnotation_out.pdf";
// Salvar arquivo de saída
pdfDocument.Save(dataDir);
```
Este código demonstra como adicionar uma anotação de texto com título, assunto, estado, conteúdo e ícone específicos a uma página PDF usando Aspose.PDF for .NET. Você pode modificar este código de acordo com suas necessidades para adicionar anotações aos seus documentos PDF. Apenas lembre-se de substituir SEU DIRETÓRIO DE DADOS pelo caminho real do diretório onde seu arquivo PDF está localizado e onde você deseja salvar o arquivo de saída.

## Conclusão

Adicionar anotações a documentos PDF usando Aspose.PDF for .NET oferece uma ferramenta valiosa para aprimorar a colaboração de documentos e processos de revisão. Seguindo o guia passo a passo fornecido neste artigo, os desenvolvedores podem integrar perfeitamente recursos de anotação em seus aplicativos C#.

### Perguntas frequentes

#### P: Que tipos de anotações podem ser adicionadas usando Aspose.PDF for .NET?

R: Aspose.PDF for .NET oferece suporte a vários tipos de anotações, incluindo anotações de texto, carimbos, links, formas e muito mais. Os desenvolvedores podem personalizar a aparência e as propriedades dessas anotações para atender às suas necessidades específicas.

#### P: Posso adicionar anotações a páginas específicas em um documento PDF de várias páginas?

R: Sim, Aspose.PDF for .NET permite que você especifique a página onde deseja adicionar a anotação. Você pode escolher uma página específica ou adicionar anotações a várias páginas conforme necessário.

#### P: Como posso personalizar a aparência das anotações?

R: As anotações podem ser personalizadas usando propriedades como largura da borda, cor, estilo do traço, estilo do texto e muito mais. Aspose.PDF for .NET oferece um rico conjunto de opções para personalizar a aparência das anotações.

#### P: É possível adicionar hiperlinks como anotações usando Aspose.PDF for .NET?

R: Sim, você pode adicionar hiperlinks como anotações a documentos PDF usando Aspose.PDF for .NET. As anotações de hiperlink podem ser usadas para vincular URLs externos ou locais específicos no mesmo documento.

#### P: Podem ser adicionadas anotações a documentos PDF existentes sem alterar o conteúdo original?

R: Sim, o Aspose.PDF for .NET adiciona anotações como elementos adicionais sem alterar o conteúdo original do documento PDF. O conteúdo original do PDF permanece intacto.