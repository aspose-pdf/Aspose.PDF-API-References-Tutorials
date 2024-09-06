---
title: Criar elemento de estrutura de nota
linktitle: Criar elemento de estrutura de nota
second_title: Referência da API do Aspose.PDF para .NET
description: Guia passo a passo para criar itens de nota estruturados em um documento PDF usando o Aspose.PDF para .NET.
type: docs
weight: 30
url: /pt/net/programming-with-tagged-pdf/create-note-structure-element/
---
Neste tutorial, forneceremos um guia passo a passo sobre como criar um elemento de estrutura de nota em um documento PDF usando o Aspose.PDF para .NET. O Aspose.PDF é uma biblioteca poderosa que permite criar, manipular e converter documentos PDF programaticamente. Usando os recursos de estrutura de conteúdo marcado do Aspose.PDF, você pode adicionar notas estruturadas ao seu documento PDF.

## Pré-requisitos

Antes de começar, certifique-se de ter os seguintes pré-requisitos em vigor:

1. Visual Studio instalado com .NET Framework.
2. A biblioteca Aspose.PDF para .NET.

## Etapa 1: Configuração do projeto

Para começar, crie um novo projeto no Visual Studio e adicione uma referência à biblioteca Aspose.PDF for .NET. Você pode baixar a biblioteca do site oficial do Aspose e instalá-la na sua máquina.

## Etapa 2: Importe os namespaces necessários

No seu arquivo de código C#, importe os namespaces necessários para acessar as classes e métodos fornecidos pelo Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Etapa 3: Criando o documento PDF e os elementos estruturados da nota

Use o código a seguir para criar um documento PDF e adicionar elementos estruturados de notas:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample Grade Items");
taggedContent.SetLanguage("fr-FR");

ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);

NoteElement note1 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note1);
note1.SetText("Note with automatically generated ID. ");

NoteElement note2 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note2);
note2.SetText("Note with ID = 'note_002'.");
note2.SetId("note_002");

NoteElement note3 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note3);
note3.SetText("Note with ID = 'note_003'.");
note3.SetId("note_003");
```

Este código cria um documento PDF vazio e adiciona elementos de nota estruturados a um parágrafo. Cada nota é criada usando os métodos fornecidos pelo Aspose.PDF.

## Etapa 4: salvando o documento PDF

Use o seguinte código para salvar o documento PDF:

```csharp
document. Save(outFile);
```

Este código salva o documento PDF com os elementos estruturados da nota em um arquivo especificado.

### Exemplo de código-fonte para criar elemento de estrutura de nota usando Aspose.PDF para .NET 

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
// Criar documento PDF
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
// Adicionar elemento de parágrafo
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
// Adicionar NoteElement
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
// Adicionar NoteElement
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
// Adicionar NoteElement
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
// Deve lançar uma exceção - Aspose.Pdf.Tagged.TaggedException: O elemento de estrutura com ID='note_002' já existe
//nota3.SetId("nota_002");
// O documento resultante não está em conformidade com PDF/UA se ClearId() for usado para o elemento de estrutura de nota
//nota3.ClearId();
// Salvar documento PDF marcado
document.Save(outFile);
// Verificando a conformidade com PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusão

Neste tutorial, você aprendeu como criar elementos de estrutura de nota em um documento PDF usando Aspose.PDF para .NET. Elementos de nota estruturados permitem que você adicione informações adicionais e estruturadas ao seu documento PDF.

### Perguntas frequentes

#### P: Qual é o propósito de criar elementos de estrutura de notas em um documento PDF usando Aspose.PDF para .NET?

A: Criar elementos de estrutura de nota em um documento PDF usando Aspose.PDF para .NET permite que você adicione notas estruturadas ao conteúdo do documento. Essas notas podem fornecer contexto adicional, explicações ou referências a partes específicas do conteúdo.

#### P: Como a biblioteca Aspose.PDF auxilia na criação de elementos de estrutura de notas em um documento PDF?

R: Aspose.PDF para .NET é uma biblioteca poderosa que fornece funcionalidades para criar, manipular e converter documentos PDF programaticamente. Neste tutorial, os recursos de estrutura de conteúdo marcados da biblioteca são usados para criar elementos de nota estruturados dentro do conteúdo do documento PDF.

#### P: Quais são os pré-requisitos para criar elementos de estrutura de notas em um documento PDF usando o Aspose.PDF para .NET?

R: Antes de começar, certifique-se de ter o Visual Studio instalado com o .NET Framework e de ter a biblioteca Aspose.PDF para .NET referenciada em seu projeto.

#### P: Como o código C# fornecido cria elementos de estrutura de nota no conteúdo do documento PDF?

R: O código demonstra como criar um documento PDF, definir elementos estruturados de nota e adicioná-los a um parágrafo. Cada nota é criada usando métodos fornecidos pelo Aspose.PDF, permitindo que você incorpore notas estruturadas ao conteúdo.

#### P: Posso personalizar o conteúdo e as propriedades dos elementos da estrutura de notas que crio?

R: Sim, você pode personalizar o conteúdo e as propriedades dos elementos da estrutura de nota usando os métodos e propriedades fornecidos pela biblioteca Aspose.PDF. O código mostra como definir o texto e o ID dos elementos de nota, mas você pode personalizá-los ainda mais conforme necessário.

#### P: Como é estabelecida a relação hierárquica entre os elementos da estrutura da nota e o conteúdo do documento?

 A: O relacionamento hierárquico é estabelecido adicionando elementos de estrutura de nota como filhos de outros elementos estruturados, como parágrafos. No código, os elementos de nota são anexados a um elemento de parágrafo usando o`AppendChild` método.

#### P: Posso atribuir IDs exclusivos aos elementos da estrutura de notas?

R: Sim, você pode atribuir IDs exclusivos para observar elementos de estrutura usando o`SetId` método. O código demonstra como definir os IDs dos elementos de nota para valores exclusivos.

#### P: O que acontece se eu tentar atribuir um ID duplicado a um elemento da estrutura de nota?

A: Tentar atribuir um ID duplicado a um elemento de estrutura de nota resultará em uma exceção. O código fornecido no tutorial inclui um comentário ilustrando esse cenário.

#### P: Como posso garantir a conformidade com PDF/UA ao criar elementos de estrutura de notas?

 R: O código fornecido no tutorial demonstra como validar a conformidade com PDF/UA usando o`Validate` método. Ao validar o documento em relação ao padrão PDF/UA, você pode garantir que os elementos de estrutura de nota adicionados estejam de acordo com as diretrizes de acessibilidade.

#### P: Posso usar essa abordagem para adicionar elementos de estrutura de nota a um documento PDF existente?

R: Sim, você pode modificar a abordagem fornecida para adicionar elementos de estrutura de nota a um documento PDF existente. Em vez de criar um novo documento, você carregaria o documento existente usando Aspose.PDF e seguiria etapas semelhantes para anexar elementos de nota.
