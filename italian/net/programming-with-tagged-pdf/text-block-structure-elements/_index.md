---
title: Elementi della struttura del blocco di testo
linktitle: Elementi della struttura del blocco di testo
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come utilizzare Aspose.PDF per .NET per aggiungere elementi della struttura del blocco di testo, come intestazioni e paragrafi con tag, a un documento PDF esistente.
type: docs
weight: 220
url: /it/net/programming-with-tagged-pdf/text-block-structure-elements/
---

In questo tutorial dettagliato, ti guideremo attraverso il codice sorgente C # fornito passo dopo passo per creare elementi di struttura a blocchi di testo in un documento PDF con tag utilizzando Aspose.PDF per .NET. Segui le istruzioni di seguito per capire come aggiungere intestazioni a più livelli e paragrafi con tag al tuo documento PDF.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di aver configurato il tuo ambiente di sviluppo per utilizzare Aspose.PDF per .NET. Ciò include l'installazione della libreria Aspose.PDF e la configurazione del progetto per farvi riferimento.

## Passaggio 2: creazione del documento PDF

In questo passaggio, creeremo un nuovo oggetto documento PDF con Aspose.PDF.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crea il documento PDF
Document document = new Document();
```

Abbiamo creato un nuovo documento PDF con Aspose.PDF.

## Passaggio 3: ottieni contenuti taggati e imposta titolo e lingua

Ora prendiamo il contenuto con tag del documento PDF e impostiamo il titolo e la lingua del documento.

```csharp
// Ottieni contenuti taggati
ITaggedContent taggedContent = document.TaggedContent;

// Definire il titolo e la lingua del documento
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

Abbiamo impostato il titolo e la lingua del documento PDF con tag.

## Passaggio 4: ottenere l'elemento della struttura radice

Ora prendiamo l'elemento della struttura radice del documento PDF.

```csharp
// Ottenere l'elemento della struttura radice
StructureElement rootElement = taggedContent.RootElement;
```

Abbiamo ottenuto l'elemento della struttura principale del documento PDF.

## Passaggio 5: aggiungi intestazioni e paragrafi

Ora aggiungeremo intestazioni di diversi livelli e paragrafi con tag al nostro documento PDF.

```csharp
//Crea intestazioni di diversi livelli
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);

// Definizione del testo dell'intestazione
h1.SetText("H1. Level 1 header");
h2.SetText("H2. Level 2 header");
h3.SetText("H3. Level 3 header");
h4.SetText("H4. Level 4 header");
h5.SetText("H5. Heading level 5");
h6.SetText("H6. Level 6 header");

// Aggiungi intestazioni all'elemento della struttura principale
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

// Crea il paragrafo
ParagraphElement p = taggedContent.CreateParagraphElement();

// Definizione del testo del paragrafo
p.SetText("P. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean nec lectus ac sem faucibus imperdiet. Sed ut erat ac magna ullamcorper hendrerit. Cras pellentesque libero semper, gravida magna sed, luctus leo. Fusce lectus odio, laoreet Nec ullamcorper ut, molestie eu elit. Interdum et malesuada fames ac ante ipsum primis in faucibus. Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");

// Aggiungere il paragrafo all'elemento della struttura principale
rootElement.AppendChild(p);
```

Abbiamo aggiunto intestazioni di diversi livelli e un paragrafo con tag all'elemento della struttura principale del documento PDF.

## Passaggio 6: salvare il documento PDF

Ora che abbiamo finito di modificare il documento PDF, salviamolo in un file.

```csharp
// Salva il documento PDF con tag
document.Save(dataDir + "ElementsDeStructureDeBlocsDeTexte.pdf");
```

Abbiamo salvato il documento PDF con tag con gli elementi della struttura del blocco di testo nella directory specificata.

### Esempio di codice sorgente per gli elementi della struttura del blocco di testo utilizzando Aspose.PDF per .NET 
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

// Ottieni elemento struttura radice
StructureElement rootElement = taggedContent.RootElement;
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
h1.SetText("H1. Header of Level 1");
h2.SetText("H2. Header of Level 2");
h3.SetText("H3. Header of Level 3");
h4.SetText("H4. Header of Level 4");
h5.SetText("H5. Header of Level 5");
h6.SetText("H6. Header of Level 6");
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean nec lectus ac sem faucibus imperdiet. Sed ut erat ac magna ullamcorper hendrerit. Cras pellentesque libero semper, gravida magna sed, luctus leo. Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. Interdum et malesuada fames ac ante ipsum primis in faucibus. Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
rootElement.AppendChild(p);

// Salva documento PDF con tag
document.Save(dataDir + "TextBlockStructureElements.pdf");
```

## Conclusione

In questo tutorial, abbiamo imparato come utilizzare Aspose.PDF per .NET per aggiungere elementi della struttura del blocco di testo, come intestazioni e paragrafi con tag, a un documento PDF. Ora puoi utilizzare queste funzionalità per migliorare la struttura e l'accessibilità dei tuoi documenti PDF.
