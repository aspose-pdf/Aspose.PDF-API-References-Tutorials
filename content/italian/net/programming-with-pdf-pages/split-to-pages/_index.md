---
title: Dividi in pagine
linktitle: Dividi in pagine
second_title: Aspose.PDF per riferimento all'API .NET
description: Guida passo passo per dividere un documento PDF in singole pagine utilizzando Aspose.PDF per .NET.
type: docs
weight: 140
url: /it/net/programming-with-pdf-pages/split-to-pages/
---
In questo tutorial ti guideremo attraverso il processo passo passo per dividere un documento PDF in singole pagine utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come dividere un documento PDF in più file PDF, ciascuno contenente una singola pagina.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

- Conoscenza base del linguaggio di programmazione C#
- Aspose.PDF per .NET installato nel tuo ambiente di sviluppo

## Passaggio 1: definire la directory dei documenti
Innanzitutto, devi impostare il percorso della directory dei documenti. Qui è dove si trova il documento PDF che desideri dividere. Sostituisci "DIRECTORY DOCUMENTI" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: apri il documento PDF
 Quindi puoi aprire il documento PDF da dividere utilizzando il file`Document` classe di Aspose.PDF. Assicurati di specificare il percorso corretto del documento.

```csharp
Document pdfDocument = new Document(dataDir + "SplitToPages.pdf");
```

## Passaggio 3: sfoglia le pagine e dividile
Ora puoi scorrere tutte le pagine del documento PDF utilizzando un ciclo. Per ogni pagina, crea un nuovo documento e aggiungi quella pagina a questo nuovo documento. Quindi salva il nuovo documento utilizzando un nome file univoco per ciascuna pagina.

```csharp
int pageCount = 1;
foreach(Page pdfPage in pdfDocument.Pages)
{
Document newDocument = newDocument();
newDocument.Pages.Add(pdfPage);
newDocument.Save(dataDir + "page_" + pageCount + "_out" + ".pdf");
pageCount++;
}
```

### Codice sorgente di esempio per Dividi in pagine utilizzando Aspose.PDF per .NET 

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "SplitToPages.pdf");
int pageCount = 1;
// Passa in rassegna tutte le pagine
foreach (Page pdfPage in pdfDocument.Pages)
{
	Document newDocument = new Document();
	newDocument.Pages.Add(pdfPage);
	newDocument.Save(dataDir + "page_" + pageCount + "_out" + ".pdf");
	pageCount++;
}

```

## Conclusione
In questo tutorial, abbiamo imparato come dividere un documento PDF in singole pagine utilizzando Aspose.PDF per .NET. Seguendo questa guida passo passo, puoi facilmente dividere un documento PDF in più file PDF, ciascuno contenente una singola pagina. Aspose.PDF offre un'API potente e flessibile per lavorare con documenti PDF nei tuoi progetti. Ora puoi utilizzare questa funzionalità per eseguire operazioni di suddivisione dei documenti PDF in base alle tue esigenze specifiche.

### Domande frequenti

#### D: Come posso dividere un documento PDF in singole pagine utilizzando Aspose.PDF per .NET?

R: Per dividere un documento PDF in singole pagine utilizzando Aspose.PDF per .NET, puoi seguire questi passaggi:

1. Imposta la directory dei documenti specificando il percorso in cui si trova il file PDF originale e dove desideri salvare i file PDF divisi. Sostituisci "DIRECTORY DOCUMENTI" con il percorso appropriato.
2.  Apri il documento PDF da dividere utilizzando il file`Document` classe di Aspose.PDF. Assicurati di specificare il percorso corretto del documento PDF originale.
3. Passa in rassegna tutte le pagine del documento PDF utilizzando un ciclo.
4.  Per ogni pagina, crea un nuovo documento utilizzando il file`Document` classe e aggiungi quella pagina a questo nuovo documento usando il file`Add()` metodo del`Pages` proprietà.
5.  Salva il nuovo documento con un nome file univoco per ogni pagina utilizzando il file`Save()` metodo del`Document` classe.

#### D: La divisione del documento PDF influirà sul file PDF originale?

R: No, la divisione del documento PDF non influirà sul file PDF originale. Ogni pagina viene copiata in un nuovo documento e i nuovi documenti vengono salvati separatamente, lasciando intatto il file PDF originale.

#### D: Posso specificare un formato file diverso per le pagine divise, ad esempio immagini o file di testo?

R: Il codice sorgente C# fornito dimostra come dividere il documento PDF in file PDF separati per ogni pagina. Tuttavia, puoi modificare il codice per salvare le pagine divise in altri formati, come immagini o file di testo, a seconda delle tue esigenze specifiche.

#### D: Esiste un limite al numero di pagine che possono essere divise utilizzando Aspose.PDF per .NET?

R: Non esiste un limite specifico imposto da Aspose.PDF per .NET sul numero di pagine che possono essere divise. Tuttavia, la quantità di memoria e risorse disponibili nel sistema potrebbero influire sulle prestazioni quando si lavora con un numero elevato di pagine.

#### D: Posso dividere un intervallo specifico di pagine dal documento PDF?

R: Sì, puoi modificare il codice sorgente fornito per dividere un intervallo specifico di pagine dal documento PDF. Invece di scorrere tutte le pagine, puoi implementare la logica per selezionare un intervallo specifico di pagine e creare nuovi documenti solo per quelle pagine.