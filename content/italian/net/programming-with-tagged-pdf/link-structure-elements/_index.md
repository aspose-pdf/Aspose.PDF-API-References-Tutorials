---
title: Elementi della struttura del collegamento
linktitle: Elementi della struttura del collegamento
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come creare elementi di struttura dei link in un PDF utilizzando Aspose.PDF per .NET. Guida dettagliata per aggiungere link accessibili, immagini e convalida della conformità.
type: docs
weight: 120
url: /it/net/programming-with-tagged-pdf/link-structure-elements/
---
## Introduzione

Creare e gestire elementi di struttura di collegamento all'interno di un PDF può essere cruciale per i documenti che richiedono accessibilità e navigazione fluida. In questo tutorial, ti guideremo attraverso come farlo usando Aspose.PDF per .NET. Se sei nuovo di Aspose.PDF o della manipolazione PDF in generale, non preoccuparti. Spiegherò ogni passaggio in dettaglio in modo che tu possa seguire facilmente!

## Prerequisiti  

Prima di immergerci nella codifica, chiariamo subito alcune cose. Questi sono i requisiti di base per garantire un'esperienza di sviluppo fluida.

1.  Aspose.PDF per .NET: puoi scaricare l'ultima versione[Qui](https://releases.aspose.com/pdf/net/).
2. Ambiente di sviluppo .NET: che si tratti di Visual Studio o di qualsiasi altro IDE compatibile con .NET, installatelo e rendetelo pronto all'uso.
3.  Licenza Aspose: puoi utilizzare la versione di prova gratuita di Aspose.PDF[Qui](https://releases.aspose.com/) o acquisire un[licenza temporanea](https://purchase.aspose.com/temporary-license/).
4. Conoscenza di base di C#: lavoreremo con un po' di codice C#, quindi comprendere i fondamenti renderà le cose molto più semplici.

## Importa pacchetti

Dovrai importare alcuni pacchetti prima di scrivere il codice per gli elementi della struttura di collegamento. Inizia facendo riferimento alle librerie Aspose.PDF necessarie nel tuo progetto:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Queste importazioni ci consentono di lavorare con documenti PDF, aggiungere tag e gestire elementi strutturali.

Ora creeremo un documento PDF con diversi tipi di strutture di link e ogni passaggio sarà suddiviso per aiutarti a comprendere a fondo il processo.

## Passaggio 1: inizializzare il documento  

Iniziamo creando un nuovo documento PDF e impostando il contenuto taggato per l'accessibilità.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// Crea un nuovo documento PDF
Document document = new Document(); 

// Recupera l'interfaccia TaggedContent
ITaggedContent taggedContent = document.TaggedContent;
```
  
 Qui, stiamo inizializzando il`Document` oggetto, che rappresenta il nostro file PDF. Recuperiamo anche il`TaggedContent` interfaccia, che ci consente di aggiungere elementi strutturali quali paragrafi, collegamenti e immagini.

## Passaggio 2: imposta titolo e lingua  

Ogni PDF dovrebbe avere un titolo e un'impostazione della lingua, soprattutto se si vuole garantire la conformità agli standard PDF/UA.

```csharp
// Imposta il titolo e la lingua del documento
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");
```
  
Questo passaggio assicura che il tuo PDF abbia un titolo significativo e imposta la lingua su inglese (`en-US`). Ciò è fondamentale per l'accessibilità e garantisce che gli screen reader o altre tecnologie assistive possano interpretare correttamente il documento.

## Passaggio 3: creare e aggiungere paragrafi  

In questa fase aggiungeremo dei paragrafi per contenere i nostri elementi di collegamento.

```csharp
// Crea l'elemento radice
StructureElement rootElement = taggedContent.RootElement;

// Crea un paragrafo e aggiungilo all'elemento radice
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
```
  
Creiamo un elemento struttura radice, che è essenzialmente il contenitore di livello superiore per tutti gli altri elementi. Quindi creiamo un paragrafo (`p1`) e aggiungerlo all'elemento radice.

## Passaggio 4: aggiungere un collegamento semplice  

Aggiungiamo ora un collegamento ipertestuale di base che punti a Google.

```csharp
// Crea un elemento di collegamento e aggiungilo al paragrafo
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);

// Imposta collegamento ipertestuale e testo per il collegamento
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
```
  
In questa fase, abbiamo creato un elemento link, impostato il suo collegamento ipertestuale su "http://google.com" e fornito il testo ("Google") per il collegamento. Abbiamo anche aggiunto una descrizione alternativa per garantire l'accessibilità.

## Passaggio 5: aggiunta di un collegamento con intervalli  

Possiamo anche creare collegamenti con diverse porzioni di testo.

```csharp
// Crea un altro paragrafo
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);

// Crea un collegamento con un elemento span
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");

SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);

link2.AlternateDescriptions = "Link to Google";
```
  
Qui abbiamo utilizzato un elemento span per racchiudere parte del testo all'interno del collegamento, consentendoci di personalizzare l'aspetto di determinate porzioni del collegamento.

## Passaggio 6: collegamento multilinea  

E se il testo del tuo link fosse troppo lungo? Nessun problema, puoi suddividerlo su più righe.

```csharp
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);

LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google...");
link4.AlternateDescriptions = "Link to Google (multiline)";
```
  
In questo caso, abbiamo creato un collegamento multilinea semplicemente impostando un valore di testo lungo; il testo verrà automaticamente disposto su più righe.

## Passaggio 7: aggiungere un'immagine al collegamento  

Infine, puoi anche aggiungere immagini all'interno di un collegamento.

```csharp
// Crea un nuovo paragrafo e un elemento di collegamento
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);

LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");

// Aggiungi un'immagine al collegamento
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
link5.AppendChild(figure5);

link5.AlternateDescriptions = "Link to Google";
```
  
Questo passaggio dimostra come puoi migliorare i tuoi link con un'immagine. In questo caso, abbiamo aggiunto un'icona di Google all'interno del link. Abbiamo anche garantito l'accessibilità impostando un testo alternativo per l'immagine.

## Fase 8: convalidare il PDF per la conformità  

Se si punta alla conformità PDF/UA (uno standard di accessibilità), è buona norma convalidare il documento.

```csharp
// Salva il documento PDF
document.Save(outFile);

// Convalida il documento per la conformità PDF/UA
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```
  
Abbiamo salvato il documento e lo abbiamo convalidato rispetto allo standard PDF/UA, che garantisce che il PDF soddisfi i requisiti di accessibilità.

## Conclusione  

In questo tutorial, abbiamo spiegato come creare documenti PDF strutturati usando Aspose.PDF per .NET. Dall'aggiunta di collegamenti ipertestuali di base a strutture più complesse come span, collegamenti multilinea e persino immagini, questa guida fornisce una solida base per la manipolazione degli elementi di collegamento nei tuoi PDF. Con l'ulteriore vantaggio della conformità PDF/UA, ora sei pronto per creare PDF accessibili e navigabili.

## Domande frequenti

### Posso aggiungere strutture più complesse, come tabelle, all'interno dei link?  
No, i link sono principalmente per testo e immagini, ma puoi incorporare elementi complessi nelle vicinanze.

### La convalida PDF/UA è obbligatoria?  
Non sempre, ma è altamente consigliato se si ha a cuore l'accessibilità.

### Cosa succede se il percorso del file immagine non è corretto?  
Il documento non visualizzerà l'immagine e potrebbe generare un errore durante il rendering.

### Posso formattare il testo all'interno del collegamento?  
Sì, puoi applicare stili di testo utilizzando gli elementi span.

### È possibile creare collegamenti interni ai documenti?  
Assolutamente! Puoi creare un collegamento a sezioni specifiche all'interno dello stesso documento.