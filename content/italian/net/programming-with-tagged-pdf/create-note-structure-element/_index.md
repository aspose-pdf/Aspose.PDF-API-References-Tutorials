---
title: Crea elemento struttura nota
linktitle: Crea elemento struttura nota
second_title: Riferimento API Aspose.PDF per .NET
description: Guida passo passo per creare elementi di note strutturati in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 30
url: /it/net/programming-with-tagged-pdf/create-note-structure-element/
---
In questo tutorial, ti forniremo una guida passo passo su come creare un elemento di struttura nota in un documento PDF usando Aspose.PDF per .NET. Aspose.PDF è una potente libreria che ti consente di creare, manipolare e convertire documenti PDF in modo programmatico. Utilizzando le funzionalità di struttura del contenuto contrassegnato di Aspose.PDF, puoi aggiungere note strutturate al tuo documento PDF.

## Prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

1. Visual Studio installato con .NET Framework.
2. La libreria Aspose.PDF per .NET.

## Fase 1: Impostazione del progetto

Per iniziare, crea un nuovo progetto in Visual Studio e aggiungi un riferimento alla libreria Aspose.PDF per .NET. Puoi scaricare la libreria dal sito Web ufficiale di Aspose e installarla sul tuo computer.

## Passaggio 2: importare gli spazi dei nomi necessari

Nel file di codice C#, importa gli spazi dei nomi necessari per accedere alle classi e ai metodi forniti da Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Fase 3: Creazione del documento PDF e degli elementi strutturati delle note

Utilizzare il seguente codice per creare un documento PDF e aggiungere elementi strutturati come note:

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

Questo codice crea un documento PDF vuoto e aggiunge elementi di nota strutturati a un paragrafo. Ogni nota viene creata utilizzando i metodi forniti da Aspose.PDF.

## Passaggio 4: salvataggio del documento PDF

Utilizzare il seguente codice per salvare il documento PDF:

```csharp
document. Save(outFile);
```

Questo codice salva il documento PDF con gli elementi strutturati della nota in un file specificato.

### Esempio di codice sorgente per creare un elemento di struttura della nota utilizzando Aspose.PDF per .NET 

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
// Crea documento PDF
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
// Aggiungi elemento paragrafo
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
// Aggiungi elemento nota
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
// Aggiungi elemento nota
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
// Aggiungi elemento nota
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
// Deve essere generata un'eccezione - Aspose.Pdf.Tagged.TaggedException: l'elemento della struttura con ID='note_002' esiste già
//nota3.SetId("nota_002");
// Il documento risultante non è conforme a PDF/UA se ClearId() viene utilizzato per l'elemento struttura nota
//nota3.ClearId();
// Salva il documento PDF taggato
document.Save(outFile);
// Controllo della conformità PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusione

In questo tutorial, hai imparato come creare elementi di struttura delle note in un documento PDF usando Aspose.PDF per .NET. Gli elementi di struttura delle note consentono di aggiungere informazioni aggiuntive e strutturate al documento PDF.

### Domande frequenti

#### D: Qual è lo scopo della creazione di elementi di struttura delle note in un documento PDF utilizzando Aspose.PDF per .NET?

R: La creazione di elementi di struttura delle note in un documento PDF tramite Aspose.PDF per .NET consente di aggiungere note strutturate al contenuto del documento. Queste note possono fornire contesto aggiuntivo, spiegazioni o riferimenti a parti specifiche del contenuto.

#### D: In che modo la libreria Aspose.PDF aiuta a creare elementi di struttura delle note in un documento PDF?

R: Aspose.PDF per .NET è una potente libreria che fornisce funzionalità per creare, manipolare e convertire documenti PDF a livello di programmazione. In questo tutorial, le funzionalità di struttura del contenuto contrassegnato della libreria vengono utilizzate per creare elementi di nota strutturati all'interno del contenuto del documento PDF.

#### D: Quali sono i prerequisiti per creare elementi di struttura delle note in un documento PDF utilizzando Aspose.PDF per .NET?

R: Prima di iniziare, assicurati di aver installato Visual Studio con .NET Framework e di aver fatto riferimento alla libreria Aspose.PDF per .NET nel tuo progetto.

#### D: In che modo il codice C# fornito crea elementi di struttura delle note nel contenuto del documento PDF?

R: Il codice dimostra come creare un documento PDF, definire elementi strutturati di nota e aggiungerli a un paragrafo. Ogni nota viene creata utilizzando metodi forniti da Aspose.PDF, consentendo di incorporare note strutturate nel contenuto.

#### D: Posso personalizzare il contenuto e le proprietà degli elementi della struttura delle note che creo?

R: Sì, puoi personalizzare il contenuto e le proprietà degli elementi della struttura della nota utilizzando i metodi e le proprietà forniti dalla libreria Aspose.PDF. Il codice mostra come impostare il testo e l'ID degli elementi della nota, ma puoi personalizzarli ulteriormente in base alle tue esigenze.

#### D: Come viene stabilita la relazione gerarchica tra gli elementi della struttura della nota e il contenuto del documento?

 A: La relazione gerarchica viene stabilita aggiungendo elementi di struttura nota come figli di altri elementi strutturati, come i paragrafi. Nel codice, gli elementi nota vengono aggiunti a un elemento paragrafo utilizzando`AppendChild` metodo.

#### D: Posso assegnare ID univoci agli elementi della struttura della nota?

A: Sì, puoi assegnare ID univoci agli elementi della struttura della nota utilizzando`SetId` metodo. Il codice dimostra come impostare gli ID degli elementi nota su valori univoci.

#### D: Cosa succede se provo ad assegnare un ID duplicato a un elemento della struttura della nota?

R: Il tentativo di assegnare un ID duplicato a un elemento della struttura della nota genererà un'eccezione. Il codice fornito nel tutorial include un commento che illustra questo scenario.

#### D: Come posso garantire la conformità PDF/UA quando creo elementi della struttura delle note?

 A: Il codice fornito nel tutorial dimostra come convalidare la conformità PDF/UA utilizzando`Validate` metodo. Convalidando il documento rispetto allo standard PDF/UA, puoi assicurarti che gli elementi della struttura delle note aggiunti aderiscano alle linee guida sull'accessibilità.

#### D: Posso usare questo approccio per aggiungere elementi di struttura delle note a un documento PDF esistente?

R: Sì, puoi modificare l'approccio fornito per aggiungere elementi di struttura delle note a un documento PDF esistente. Invece di creare un nuovo documento, caricheresti il documento esistente usando Aspose.PDF e poi seguiresti passaggi simili per aggiungere elementi di nota.
