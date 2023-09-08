---
title: Elementi della struttura in linea
linktitle: Elementi della struttura in linea
second_title: Aspose.PDF per riferimento all'API .NET
description: Guida passo passo all'utilizzo di elementi strutturali online con Aspose.PDF per .NET. Organizza i tuoi PDF con intestazioni e paragrafi.
type: docs
weight: 110
url: /it/net/programming-with-tagged-pdf/inline-structure-elements/
---
In questa guida passo passo, ti mostreremo come utilizzare gli elementi della struttura in linea con Aspose.PDF per .NET. Aspose.PDF è una potente libreria che ti consente di manipolare i documenti PDF a livello di codice. Gli elementi della struttura in linea ti consentono di creare una struttura gerarchica nel tuo documento PDF utilizzando intestazioni di diversi livelli e paragrafi.

Immergiamoci nel codice e impariamo come utilizzare gli elementi della struttura in linea con Aspose.PDF per .NET.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1. Libreria Aspose.PDF per .NET installata.
2. Conoscenza base del linguaggio di programmazione C#.

## Passaggio 1: configurazione dell'ambiente

Per iniziare, apri il tuo ambiente di sviluppo C# e crea un nuovo progetto. Assicurati di aver aggiunto un riferimento alla libreria Aspose.PDF per .NET nel tuo progetto.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creazione del documento

 Il primo passo è creare un nuovo documento PDF utilizzando il file`Document` classe.

```csharp
// Crea il documento PDF
Document document = new Document();
```

## Passaggio 3: lavora con i contenuti taggati

Quindi otteniamo il contenuto taggato del documento con cui lavorare.

```csharp
// Ottieni il contenuto taggato del documento
ITaggedContent taggedContent = document.TaggedContent;
```

## Passaggio 4: imposta il titolo e la lingua del documento

Ora possiamo impostare il titolo e la lingua del documento.

```csharp
// Definire il titolo e la lingua del documento
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## Passaggio 5: aggiungi elementi strutturali online

Ora aggiungeremo elementi di struttura in linea come titoli di diversi livelli e paragrafi al nostro documento.

```csharp
// Ottieni l'elemento della struttura radice
StructureElement rootElement = taggedContent.RootElement;

// Aggiungi intestazioni di diversi livelli
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

// Aggiungi contenuto a ciascuna intestazione
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1.");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 header");
h1.AppendChild(spanH12);

SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2.");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 header");
h2.AppendChild(spanH22);

SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3.");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 header");
h3.AppendChild(spanH32);

SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4.");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 header");
h4.AppendChild(spanH42);

SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5.");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 header");
h5.AppendChild(spanH52);

SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6.");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Heading level 6");
h6.AppendChild(spanH62);

// Aggiungi un paragrafo
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P.");
rootElement.AppendChild(p);

// Aggiungi contenuto al paragrafo
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit.");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet.");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit.");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo.");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit.");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. So cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit.");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);
```

Qui creiamo elementi di struttura in linea, come titoli di diversi livelli e un paragrafo, e aggiungiamo loro contenuto.

## Passaggio 6: salva il documento PDF contrassegnato

Infine, salviamo il documento PDF taggato.

```csharp
// Salva il documento PDF contrassegnato
document.Save(dataDir + "InlineStructureElements.pdf");
```

### Codice sorgente di esempio per gli elementi della struttura in linea utilizzando Aspose.PDF per .NET 

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea documento PDF
Document document = new Document();

// Ottieni contenuti per lavorare con TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// Imposta titolo e lingua per Documnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// Ottieni l'elemento della struttura radice
StructureElement rootElement = taggedContent.RootElement;
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1. ");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 Header");
h1.AppendChild(spanH12);
SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2. ");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 Header");
h2.AppendChild(spanH22);
SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3. ");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 Header");
h3.AppendChild(spanH32);
SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4. ");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 Header");
h4.AppendChild(spanH42);
SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5. ");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 Header");
h5.AppendChild(spanH52);
SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6. ");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Level 6 Header");
h6.AppendChild(spanH62);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. ");
rootElement.AppendChild(p);
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit. ");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet. ");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit. ");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo. ");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. ");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. ");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);

// Salva documento PDF contrassegnato
document.Save(dataDir + "InlineStructureElements.pdf");

```

## Conclusione

Congratulazioni! Hai imparato come utilizzare gli elementi della struttura in linea con Aspose.PDF per .NET. Ora puoi creare una struttura gerarchica nel tuo documento PDF utilizzando intestazioni di diversi livelli e paragrafi. Esplora altre funzionalità di Aspose.PDF per scoprirne tutto il potenziale.

### Domande frequenti

#### D: Cosa sono gli elementi della struttura in linea in un documento PDF e in che modo contribuiscono alla creazione di una struttura gerarchica?

R: Gli elementi della struttura in linea in un documento PDF, come intestazioni di diversi livelli e paragrafi, vengono utilizzati per creare una struttura gerarchica che organizza e presenta il contenuto in modo strutturato. Questi elementi consentono di stabilire una chiara gerarchia e un flusso di informazioni all'interno del documento.

#### D: In che modo gli elementi della struttura incorporata possono migliorare la leggibilità e l'organizzazione di un documento PDF?

R: Gli elementi della struttura in linea, in particolare intestazioni e paragrafi, aiutano a migliorare la leggibilità e l'organizzazione di un documento PDF fornendo una struttura logica. I titoli indicano diversi livelli di importanza e aiutano i lettori a navigare nel contenuto, mentre i paragrafi raggruppano insieme le informazioni correlate.

#### D: In che modo Aspose.PDF per .NET facilita l'uso di elementi di struttura in linea?

R: Aspose.PDF per .NET offre classi e metodi per creare e manipolare elementi di struttura in linea, come intestazioni e paragrafi. Questi elementi possono essere personalizzati, organizzati gerarchicamente e arricchiti con contenuti per migliorare la presentazione visiva e l'accessibilità del documento.

####  D: Qual è lo scopo di`taggedContent` object in relation to inline structure elements?

 R: Il`taggedContent` oggetto, ottenuto da`TaggedContent` proprietà di a`Document`, consente di lavorare con elementi strutturati, inclusi elementi di struttura in linea. Ti consente di creare, personalizzare e organizzare intestazioni e paragrafi all'interno del documento.

#### D: In che modo gli elementi della struttura in linea aiutano a creare una chiara gerarchia dei documenti?

R: Gli elementi della struttura in linea, come i titoli di vari livelli, contribuiscono a stabilire una gerarchia chiara e ben definita nel documento. I lettori possono identificare rapidamente gli argomenti principali, i sottoargomenti e i contenuti correlati, rendendo il documento più facile da navigare e comprendere.

#### D: Posso personalizzare l'aspetto e la formattazione degli elementi della struttura in linea utilizzando Aspose.PDF per .NET?

R: Sì, puoi personalizzare l'aspetto e la formattazione degli elementi della struttura incorporata. Puoi impostare proprietà quali stili di carattere, dimensioni, colori, allineamento, rientro e spaziatura per ottenere la presentazione visiva desiderata per intestazioni e paragrafi.

#### D: Come posso creare e aggiungere intestazioni di diversi livelli a un documento PDF utilizzando elementi di struttura in linea in Aspose.PDF per .NET?

 R: Puoi creare intestazioni di diversi livelli utilizzando il file`CreateHeaderElement` metodo e quindi aggiungerli all'elemento della struttura root. Successivamente, puoi aggiungere contenuto a ciascun elemento dell'intestazione utilizzando il file`CreateSpanElement` metodo per creare porzioni di testo.

#### D: Posso utilizzare elementi di struttura in linea per creare elenchi, punti elenco o altri tipi di organizzazione del contenuto in un documento PDF?

R: Sebbene gli stessi elementi della struttura in linea vengano utilizzati principalmente per intestazioni e paragrafi, è possibile utilizzarli in combinazione con altre funzionalità offerte da Aspose.PDF per .NET per creare elenchi, punti elenco, tabelle e altri tipi di organizzazione del contenuto per un elenco completo struttura del documento.

#### D: In che modo gli elementi della struttura in linea contribuiscono all'accessibilità dei documenti?

R: Gli elementi della struttura in linea svolgono un ruolo cruciale nel migliorare l'accessibilità dei documenti. Intestazioni e paragrafi adeguatamente strutturati forniscono una chiara gerarchia dei documenti che aiuta i lettori di schermo e altre tecnologie assistive a interpretare e trasmettere accuratamente il contenuto agli utenti con disabilità.

#### D: Posso esplorare usi più avanzati degli elementi della struttura in linea, come la creazione di elementi interattivi o l'incorporamento di contenuti multimediali?

R: Assolutamente! Mentre questo tutorial si concentra sulla creazione di intestazioni e paragrafi, Aspose.PDF per .NET offre funzionalità avanzate per creare elementi interattivi, incorporare contenuti multimediali, aggiungere collegamenti ipertestuali e altro ancora. Controlla la documentazione e gli esempi della libreria per approfondire queste funzionalità avanzate.