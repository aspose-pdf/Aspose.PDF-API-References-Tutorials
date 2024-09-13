---
title: Elementi della struttura in linea
linktitle: Elementi della struttura in linea
second_title: Riferimento API Aspose.PDF per .NET
description: Guida passo passo all'utilizzo di elementi strutturali online con Aspose.PDF per .NET. Organizza i tuoi PDF con titoli e paragrafi.
type: docs
weight: 110
url: /it/net/programming-with-tagged-pdf/inline-structure-elements/
---
In questa guida passo passo, ti mostreremo come usare gli elementi di struttura inline con Aspose.PDF per .NET. Aspose.PDF è una potente libreria che ti consente di manipolare i documenti PDF a livello di programmazione. Gli elementi di struttura inline ti consentono di creare una struttura gerarchica nel tuo documento PDF usando titoli di diversi livelli e paragrafi.

Analizziamo il codice e impariamo come utilizzare gli elementi della struttura in linea con Aspose.PDF per .NET.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1. Libreria Aspose.PDF per .NET installata.
2. Conoscenza di base del linguaggio di programmazione C#.

## Fase 1: Impostazione dell'ambiente

Per iniziare, apri il tuo ambiente di sviluppo C# e crea un nuovo progetto. Assicurati di aver aggiunto un riferimento alla libreria Aspose.PDF per .NET nel tuo progetto.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
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
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## Passaggio 5: aggiungere elementi strutturali online

Adesso aggiungeremo al nostro documento elementi di struttura in linea, come titoli di diversi livelli e paragrafi.

```csharp
// Ottieni l'elemento della struttura radice
StructureElement rootElement = taggedContent.RootElement;

// Aggiungere intestazioni di diversi livelli
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

// Aggiungere contenuto a ogni intestazione
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

// Aggiungere contenuto al paragrafo
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

Qui creiamo elementi di struttura in linea, come titoli di diversi livelli e un paragrafo, e aggiungiamo loro del contenuto.

## Passaggio 6: salvare il documento PDF taggato

Infine, salviamo il documento PDF taggato.

```csharp
// Salva il documento PDF taggato
document.Save(dataDir + "InlineStructureElements.pdf");
```

### Esempio di codice sorgente per elementi di struttura in linea utilizzando Aspose.PDF per .NET 

```csharp

// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea documento PDF
Document document = new Document();

// Ottieni contenuti per lavorare con TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// Imposta titolo e lingua per il documento
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

// Salva il documento PDF taggato
document.Save(dataDir + "InlineStructureElements.pdf");

```

## Conclusione

Congratulazioni! Hai imparato a usare gli elementi di struttura inline con Aspose.PDF per .NET. Ora puoi creare una struttura gerarchica nel tuo documento PDF usando titoli di diversi livelli e paragrafi. Esplora altre funzionalità di Aspose.PDF per scoprirne il pieno potenziale.

### Domande frequenti

#### D: Cosa sono gli elementi di struttura in linea in un documento PDF e come contribuiscono a creare una struttura gerarchica?

A: Gli elementi di struttura in linea in un documento PDF, come titoli di diversi livelli e paragrafi, vengono utilizzati per creare una struttura gerarchica che organizza e presenta il contenuto in modo strutturato. Questi elementi consentono di stabilire una chiara gerarchia e un flusso di informazioni all'interno del documento.

#### D: In che modo gli elementi di struttura in linea possono migliorare la leggibilità e l'organizzazione di un documento PDF?

A: Gli elementi di struttura in linea, in particolare titoli e paragrafi, aiutano a migliorare la leggibilità e l'organizzazione di un documento PDF fornendo una struttura logica. I titoli indicano diversi livelli di importanza e aiutano i lettori a navigare nel contenuto, mentre i paragrafi raggruppano insieme le informazioni correlate.

#### D: In che modo Aspose.PDF per .NET facilita l'uso di elementi di struttura in linea?

R: Aspose.PDF per .NET offre classi e metodi per creare e manipolare elementi di struttura inline, come titoli e paragrafi. Questi elementi possono essere personalizzati, organizzati gerarchicamente e arricchiti con contenuti per migliorare la presentazione visiva e l'accessibilità del documento.

####  D: Qual è lo scopo del`taggedContent` object in relation to inline structure elements?

 A: Il`taggedContent` oggetto, ottenuto dal`TaggedContent` proprietà di un`Document`, consente di lavorare con elementi strutturati, inclusi gli elementi di struttura in linea. Consente di creare, personalizzare e organizzare titoli e paragrafi all'interno del documento.

#### D: In che modo gli elementi della struttura in linea aiutano a creare una chiara gerarchia dei documenti?

A: Gli elementi di struttura in linea, come titoli di vari livelli, contribuiscono a stabilire una gerarchia chiara e ben definita nel documento. I lettori possono identificare rapidamente gli argomenti principali, i sottoargomenti e i contenuti correlati, rendendo il documento più facile da navigare e comprendere.

#### D: Posso personalizzare l'aspetto e la formattazione degli elementi della struttura in linea utilizzando Aspose.PDF per .NET?

R: Sì, puoi personalizzare l'aspetto e la formattazione degli elementi della struttura in linea. Puoi impostare proprietà come stili di carattere, dimensioni, colori, allineamento, rientro e spaziatura per ottenere la presentazione visiva desiderata per titoli e paragrafi.

#### D: Come posso creare e aggiungere intestazioni di diversi livelli a un documento PDF utilizzando elementi di struttura in linea in Aspose.PDF per .NET?

 A: È possibile creare titoli di diversi livelli utilizzando`CreateHeaderElement` poi aggiungerli all'elemento struttura radice. Successivamente, puoi aggiungere contenuto a ogni elemento di intestazione usando il metodo`CreateSpanElement` metodo per creare porzioni di testo.

#### D: Posso utilizzare elementi di struttura in linea per creare elenchi, punti elenco o altri tipi di organizzazione dei contenuti in un documento PDF?

R: Sebbene gli elementi di struttura in linea siano utilizzati principalmente per titoli e paragrafi, è possibile utilizzarli in combinazione con altre funzionalità offerte da Aspose.PDF per .NET per creare elenchi, punti elenco, tabelle e altri tipi di organizzazione dei contenuti per una struttura di documento completa.

#### D: In che modo gli elementi della struttura in linea contribuiscono all'accessibilità del documento?

A: Gli elementi di struttura in linea svolgono un ruolo cruciale nel migliorare l'accessibilità del documento. Titoli e paragrafi strutturati correttamente forniscono una chiara gerarchia del documento che aiuta gli screen reader e altre tecnologie assistive a interpretare e trasmettere con precisione il contenuto agli utenti con disabilità.

#### D: Posso esplorare utilizzi più avanzati degli elementi di struttura in linea, come la creazione di elementi interattivi o l'incorporamento di contenuti multimediali?

R: Assolutamente! Mentre questo tutorial si concentra sulla creazione di titoli e paragrafi, Aspose.PDF per .NET offre funzionalità avanzate per creare elementi interattivi, incorporare contenuti multimediali, aggiungere collegamenti ipertestuali e altro ancora. Consulta la documentazione e gli esempi della libreria per approfondire queste funzionalità avanzate.