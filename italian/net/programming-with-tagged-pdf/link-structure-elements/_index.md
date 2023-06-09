---
title: Collega gli elementi della struttura
linktitle: Collega gli elementi della struttura
second_title: Aspose.PDF per riferimento API .NET
description: Guida dettagliata all'utilizzo degli elementi della struttura di collegamento con Aspose.PDF per .NET. Crea collegamenti ipertestuali nei tuoi documenti PDF.
type: docs
weight: 120
url: /it/net/programming-with-tagged-pdf/link-structure-elements/
---
In questa guida dettagliata, ti mostreremo come utilizzare gli elementi della struttura di collegamento con Aspose.PDF per .NET. Aspose.PDF è una potente libreria che ti consente di creare e manipolare documenti PDF in modo programmatico. Gli elementi della struttura dei collegamenti consentono di aggiungere collegamenti ipertestuali al documento PDF, consentendo agli utenti di fare clic sui collegamenti e navigare verso le risorse online.

Immergiamoci nel codice e impariamo come utilizzare gli elementi della struttura di collegamento con Aspose.PDF per .NET.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1. Libreria Aspose.PDF per .NET installata.
2. Conoscenza di base del linguaggio di programmazione C#.

## Passaggio 1: configurazione dell'ambiente

Per iniziare, apri il tuo ambiente di sviluppo C# e crea un nuovo progetto. Assicurati di aver aggiunto un riferimento alla libreria Aspose.PDF per .NET nel tuo progetto.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
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
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## Passaggio 5: aggiungere elementi della struttura del collegamento

Ora aggiungiamo gli elementi della struttura dei collegamenti al nostro documento. Creeremo diversi tipi di collegamenti, inclusi semplici collegamenti di testo, collegamenti di immagini e collegamenti multilinea.
```csharp
// Ottieni l'elemento della struttura radice (elemento della struttura del documento)
StructureElement rootElement = taggedContent.RootElement;

// Aggiungi un paragrafo con un collegamento ipertestuale
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.it");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

// Aggiungere un paragrafo con un collegamento ipertestuale contenente rich text
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.it");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

// Aggiungere un paragrafo con un collegamento ipertestuale contenente testo parzialmente formattato
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.it");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";

// Aggiungi un paragrafo con un collegamento ipertestuale multilinea
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.it");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

//Aggiungi un paragrafo con un collegamento ipertestuale contenente un'immagine
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.it");
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

## Passaggio 6: salvare il documento PDF con tag

Infine, salviamo il documento PDF con tag.

```csharp
// Salva il documento PDF con tag
document. Save(outFile);
```

## Passaggio 7: verificare la conformità PDF/UA

 Possiamo anche verificare la conformità del documento a PDF/UA utilizzando il file`Validate` metodo del`Document` classe.

```csharp
// Verifica la conformità PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### Codice sorgente di esempio per gli elementi della struttura di collegamento utilizzando Aspose.PDF per .NET 
```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

//Documento di creazione e acquisizione di contenuti Pdf con tag
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// Impostazione del titolo e della lingua della natura per il documento
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

// Ottenere l'elemento della struttura principale (elemento della struttura del documento)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.it");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.it");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.it");
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
link4.Hyperlink = new WebHyperlink("http://google.it");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.it");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";

// Salva documento PDF con tag
document.Save(outFile);

// Controllo della conformità PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## Conclusione

Congratulazioni! Hai imparato come utilizzare gli elementi della struttura di collegamento con Aspose.PDF per .NET. Ora puoi creare collegamenti ipertestuali nei tuoi documenti PDF, consentendo agli utenti di navigare verso le risorse online. Sperimenta ed esplora più funzionalità di Aspose.PDF per creare documenti PDF interattivi e arricchiti.