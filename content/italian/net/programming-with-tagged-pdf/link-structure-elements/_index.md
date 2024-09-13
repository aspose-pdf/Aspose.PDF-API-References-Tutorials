---
title: Elementi della struttura del collegamento
linktitle: Elementi della struttura del collegamento
second_title: Riferimento API Aspose.PDF per .NET
description: Guida passo passo all'utilizzo degli elementi della struttura dei link con Aspose.PDF per .NET. Crea collegamenti ipertestuali nei tuoi documenti PDF.
type: docs
weight: 120
url: /it/net/programming-with-tagged-pdf/link-structure-elements/
---
In questa guida passo passo, ti mostreremo come usare gli elementi della struttura dei link con Aspose.PDF per .NET. Aspose.PDF è una potente libreria che ti consente di creare e manipolare documenti PDF a livello di programmazione. Gli elementi della struttura dei link ti consentono di aggiungere collegamenti ipertestuali al tuo documento PDF, consentendo agli utenti di fare clic sui link e navigare verso risorse online.

Analizziamo il codice e impariamo come utilizzare gli elementi della struttura dei link con Aspose.PDF per .NET.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1. Libreria Aspose.PDF per .NET installata.
2. Conoscenza di base del linguaggio di programmazione C#.

## Fase 1: Impostazione dell'ambiente

Per iniziare, apri il tuo ambiente di sviluppo C# e crea un nuovo progetto. Assicurati di aver aggiunto un riferimento alla libreria Aspose.PDF per .NET nel tuo progetto.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
```

## Fase 2: Creazione del documento

 Il primo passo è creare un nuovo documento PDF utilizzando`Document` classe.

```csharp
// Crea il documento PDF
Document document = new Document();
```

## Passaggio 3: lavorare con i contenuti taggati

Quindi otteniamo il contenuto taggato del documento con cui lavorare.

```csharp
// Ottieni il contenuto taggato del documento
ITaggedContent taggedContent = document.TaggedContent;
```

## Passaggio 4: impostare il titolo e la lingua del documento

Ora possiamo impostare il titolo e la lingua del documento.

```csharp
// Definire il titolo e la lingua del documento
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## Passaggio 5: aggiungere elementi alla struttura del collegamento

Ora aggiungiamo elementi di struttura dei link al nostro documento. Creeremo diversi tipi di link, inclusi link di testo semplici, link di immagini e link multi-linea.
```csharp
// Ottieni l'elemento della struttura radice (elemento della struttura del documento)
StructureElement rootElement = taggedContent.RootElement;

// Aggiungere un paragrafo con un collegamento ipertestuale
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

// Aggiungere un paragrafo con un collegamento ipertestuale contenente testo formattato
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

// Aggiungere un paragrafo con un collegamento ipertestuale contenente testo parzialmente formattato
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";

// Aggiungere un paragrafo con un collegamento ipertestuale multilinea
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

// Aggiungere un paragrafo con un collegamento ipertestuale contenente un'immagine
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";
```

## Passaggio 6: salvare il documento PDF taggato

Infine, salviamo il documento PDF taggato.

```csharp
// Salva il documento PDF taggato
document. Save(outFile);
```

## Fase 7: verificare la conformità PDF/UA

 Possiamo anche controllare il documento per la conformità PDF/UA utilizzando`Validate` metodo del`Document` classe.

```csharp
// Controllare la conformità PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### Esempio di codice sorgente per gli elementi della struttura di collegamento utilizzando Aspose.PDF per .NET 
```csharp

// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

//Creazione di documenti e ottenimento di contenuti PDF taggati
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// Impostazione del titolo e della lingua della natura per il documento
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

// Ottenere l'elemento della struttura radice (elemento della struttura del documento)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";

// Salva il documento PDF taggato
document.Save(outFile);

// Controllo della conformità PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## Conclusione

Congratulazioni! Hai imparato a usare gli elementi della struttura dei link con Aspose.PDF per .NET. Ora puoi creare collegamenti ipertestuali nei tuoi documenti PDF, consentendo agli utenti di navigare verso risorse online. Sperimenta ed esplora altre funzionalità di Aspose.PDF per creare documenti PDF interattivi e arricchiti.

### Domande frequenti

#### D: Cosa sono gli elementi della struttura dei collegamenti in un documento PDF e come migliorano l'interattività del documento?

A: Gli elementi della struttura dei link in un documento PDF vengono utilizzati per creare collegamenti ipertestuali che consentono agli utenti di navigare verso risorse online o posizioni specifiche all'interno del documento. Questi elementi migliorano l'interattività fornendo link cliccabili che consentono agli utenti di accedere a contenuti correlati o siti Web esterni.

#### D: In che modo gli elementi della struttura di collegamento possono essere utili in un documento PDF?

A: Gli elementi della struttura dei link migliorano l'esperienza utente rendendo il documento PDF interattivo. Forniscono un rapido accesso a informazioni aggiuntive, contenuti correlati, siti Web esterni o sezioni specifiche all'interno del documento, migliorando la navigazione e facilitando il recupero delle informazioni.

#### D: Posso creare diversi tipi di collegamenti ipertestuali utilizzando gli elementi della struttura dei collegamenti in Aspose.PDF per .NET?

R: Sì, puoi creare vari tipi di collegamenti ipertestuali utilizzando elementi di struttura dei collegamenti. Aspose.PDF per .NET ti consente di creare collegamenti ipertestuali con testo normale, testo RTF, immagini e descrizioni multi-riga, offrendo versatilità nel modo in cui ti colleghi a contenuti esterni o posizioni all'interno del documento.

#### D: Come posso impostare e inizializzare gli elementi della struttura dei collegamenti in un documento PDF utilizzando Aspose.PDF per .NET?

 A: Per utilizzare gli elementi della struttura dei collegamenti, è necessario prima creare un nuovo documento PDF utilizzando`Document` classe. Quindi, ottenere il contenuto taggato utilizzando il`TaggedContent`proprietà del documento. Da lì, puoi creare e personalizzare gli elementi della struttura di collegamento e aggiungerli all'elemento della struttura radice.

#### D: Come posso creare un semplice collegamento ipertestuale di testo utilizzando gli elementi della struttura dei collegamenti?
 A: È possibile creare un semplice collegamento ipertestuale di testo creando un`LinkElement` e impostando il suo`Hyperlink` proprietà a un`WebHyperlink` con l'URL a cui vuoi collegarti. Puoi anche impostare il testo visualizzato del collegamento utilizzando`SetText` metodo.

#### D: È possibile creare collegamenti ipertestuali con immagini utilizzando elementi di struttura dei collegamenti?

 R: Sì, puoi creare collegamenti ipertestuali con immagini utilizzando elementi di struttura dei collegamenti. Dovresti creare un`LinkElement` e quindi aggiungere un`FigureElement` con un'immagine. Questo ti consente di creare un collegamento ipertestuale basato su immagini.

#### D: Come posso assicurarmi che il mio documento PDF con collegamenti ipertestuali sia conforme allo standard PDF/UA per l'accessibilità?

 A: Aspose.PDF per .NET offre la possibilità di convalidare la conformità del documento PDF con lo standard PDF/UA utilizzando`Validate` metodo del`Document`classe. Ciò garantisce che i collegamenti ipertestuali del documento siano accessibili agli utenti con disabilità.

#### D: Quali sono le descrizioni alternative per gli elementi della struttura dei link e perché sono importanti?

A: Le descrizioni alternative (testo alt) per gli elementi della struttura dei link forniscono descrizioni testuali degli hyperlink. Queste descrizioni sono essenziali per l'accessibilità, consentendo agli utenti con disabilità visive di comprendere lo scopo del link e la sua destinazione.

#### D: Posso personalizzare l'aspetto e il comportamento dei collegamenti ipertestuali creati utilizzando gli elementi della struttura dei collegamenti?

R: Mentre gli elementi della struttura dei link si concentrano principalmente sulla creazione di hyperlink, puoi personalizzare ulteriormente l'aspetto e il comportamento degli hyperlink utilizzando altre funzionalità offerte da Aspose.PDF per .NET. Ciò include la specificazione di colori, stili e azioni di collegamento.

#### D: In che modo gli elementi della struttura dei link contribuiscono a rendere i documenti PDF più interattivi e intuitivi?

A: Gli elementi della struttura dei link trasformano i documenti PDF statici in esperienze interattive aggiungendo collegamenti ipertestuali cliccabili. Questa interattività migliora il coinvolgimento dell'utente, consente una navigazione fluida tra contenuti correlati e migliora l'usabilità complessiva del documento.