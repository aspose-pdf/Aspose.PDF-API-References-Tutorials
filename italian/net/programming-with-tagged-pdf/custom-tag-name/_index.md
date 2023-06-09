---
title: Nome tag personalizzato
linktitle: Nome tag personalizzato
second_title: Aspose.PDF per riferimento API .NET
description: Guida dettagliata all'utilizzo di un nome di tag personalizzato con Aspose.PDF per .NET. Migliora la struttura dei tuoi PDF con tag personalizzati.
type: docs
weight: 90
url: /it/net/programming-with-tagged-pdf/custom-tag-name/
---
In questa guida dettagliata, ti illustreremo come utilizzare un nome di tag personalizzato con Aspose.PDF per .NET. Aspose.PDF è una potente libreria che ti consente di manipolare i documenti PDF a livello di programmazione. L'utilizzo di tag personalizzati consente di aggiungere informazioni strutturali specifiche al documento PDF, rendendolo più facile da usare e più facile da accedere.

Immergiamoci nel codice e impariamo come utilizzare un nome di tag personalizzato con Aspose.PDF per .NET.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1. Libreria Aspose.PDF per .NET installata.
2. Conoscenza di base del linguaggio di programmazione C#.

## Passaggio 1: configurazione dell'ambiente

Per iniziare, apri il tuo ambiente di sviluppo C# e crea un nuovo progetto. Assicurati di aver aggiunto un riferimento alla libreria Aspose.PDF per .NET nel tuo progetto.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creazione del documento

 Il primo passaggio consiste nel creare un nuovo documento PDF utilizzando il file`Document` classe.

```csharp
// Crea il documento PDF
Document document = new Document();
```

## Passaggio 3: lavorare con i contenuti contrassegnati

Quindi otteniamo il contenuto con tag del documento con cui lavorare.

```csharp
// Ottieni il contenuto con tag del documento
ITaggedContent taggedContent = document.TaggedContent;
```

## Passaggio 4: imposta il titolo e la lingua del documento

Ora possiamo impostare il titolo e la lingua del documento.

```csharp
// Definire il titolo e la lingua del documento
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## Passaggio 5: creazione di elementi della struttura logica

Ora creiamo alcuni elementi di struttura logica per organizzare il nostro contenuto.

```csharp
// Creare elementi di struttura logica
SectElement sect = taggedContent.CreateSectElement();
taggedContent.RootElement.AppendChild(sect);
ParagraphElement p1 = taggedContent.CreateParagraphElement();
ParagraphElement p2 = taggedContent.CreateParagraphElement();
ParagraphElement p3 = taggedContent.CreateParagraphElement();
ParagraphElement p4 = taggedContent.CreateParagraphElement();
p1.SetText("P1.");
p2.SetText("P2.");
p3.SetText("P3.");
p4.SetText("P4.");
p1.SetTag("P1");
p2.SetTag("Para");
p3.SetTag("Para");
p4.SetTag("Paragraph");
sect.AppendChild(p1);
sect.AppendChild(p2);
sect.AppendChild(p3);
sect.AppendChild(p4);
SpanElement span1 = taggedContent.CreateSpanElement();
SpanElement span2 = taggedContent.CreateSpanElement();
SpanElement span3 = taggedContent.CreateSpanElement();
SpanElement span4 = taggedContent.CreateSpanElement();
span1.SetText("Span 1.");
span2.SetText("Span 2.");
span3.SetText("Span 3.");
span4.SetText("Span 4.");
span1.SetTag("SPAN");
span2.SetTag("Sp");
span3.SetTag("Sp");
span4.SetTag("TheSpan");
p1.AppendChild(span1);
p2.AppendChild(span2);
p3.AppendChild(span3);
p4.AppendChild(span4);
```

Qui creiamo elementi paragrafo ed elementi span per il nostro contenuto e assegniamo loro tag personalizzati.

## Passaggio 6: salvare il documento PDF con tag

Infine, salviamo il documento PDF con tag.

```csharp
// Salva il documento PDF con tag
document.Save(dataDir + "CustomTag.pdf");
```

### Esempio di codice sorgente per Nome tag personalizzato utilizzando Aspose.PDF per .NET 
```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea documento Pdf
Document document = new Document();

// Ottieni contenuti per lavorare con TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// Imposta titolo e lingua per il documento
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// Crea elementi della struttura logica
SectElement sect = taggedContent.CreateSectElement();
taggedContent.RootElement.AppendChild(sect);
ParagraphElement p1 = taggedContent.CreateParagraphElement();
ParagraphElement p2 = taggedContent.CreateParagraphElement();
ParagraphElement p3 = taggedContent.CreateParagraphElement();
ParagraphElement p4 = taggedContent.CreateParagraphElement();
p1.SetText("P1. ");
p2.SetText("P2. ");
p3.SetText("P3. ");
p4.SetText("P4. ");
p1.SetTag("P1");
p2.SetTag("Para");
p3.SetTag("Para");
p4.SetTag("Paragraph");
sect.AppendChild(p1);
sect.AppendChild(p2);
sect.AppendChild(p3);
sect.AppendChild(p4);
SpanElement span1 = taggedContent.CreateSpanElement();
SpanElement span2 = taggedContent.CreateSpanElement();
SpanElement span3 = taggedContent.CreateSpanElement();
SpanElement span4 = taggedContent.CreateSpanElement();
span1.SetText("Span 1.");
span2.SetText("Span 2.");
span3.SetText("Span 3.");
span4.SetText("Span 4.");
span1.SetTag("SPAN");
span2.SetTag("Sp");
span3.SetTag("Sp");
span4.SetTag("TheSpan");
p1.AppendChild(span1);
p2.AppendChild(span2);
p3.AppendChild(span3);
p4.AppendChild(span4);

// Salva documento PDF con tag
document.Save(dataDir + "CustomTag.pdf");

```

## Conclusione

Congratulazioni! Hai imparato come utilizzare un nome di tag personalizzato con Aspose.PDF per .NET. Ora puoi aggiungere informazioni strutturali specifiche al tuo documento PDF utilizzando tag personalizzati. Esplora più funzionalità di Aspose.PDF per scoprire il suo pieno potenziale.
