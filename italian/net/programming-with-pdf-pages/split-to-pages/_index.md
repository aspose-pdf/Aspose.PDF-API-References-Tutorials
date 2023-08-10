---
title: Dividi in pagine
linktitle: Dividi in pagine
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo passo per dividere un documento PDF in singole pagine utilizzando Aspose.PDF per .NET.
type: docs
weight: 140
url: /it/net/programming-with-pdf-pages/split-to-pages/
---
In questo tutorial, ti guideremo attraverso il processo passo-passo per dividere un documento PDF in singole pagine utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come suddividere un documento PDF in più file PDF, ciascuno contenente una singola pagina.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

- Conoscenza di base del linguaggio di programmazione C#
- Aspose.PDF per .NET installato nel tuo ambiente di sviluppo

## Passaggio 1: definire la directory dei documenti
Innanzitutto, devi impostare il percorso della directory dei documenti. Qui è dove si trova il documento PDF che vuoi dividere. Sostituisci "LA TUA CARTELLA DEI DOCUMENTI" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: apri il documento PDF
 Quindi puoi aprire il documento PDF da dividere usando il file`Document` classe di Aspose.PDF. Assicurati di specificare il percorso del documento corretto.

```csharp
Document pdfDocument = new Document(dataDir + "SplitToPages.pdf");
```

## Passaggio 3: sfoglia le pagine e dividile
Ora puoi scorrere tutte le pagine del documento PDF usando un ciclo. Per ogni pagina, crea un nuovo documento e aggiungi quella pagina a questo nuovo documento. Quindi salvare il nuovo documento utilizzando un nome file univoco per ogni pagina.

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

### Esempio di codice sorgente per Split To Pages utilizzando Aspose.PDF per .NET 

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "SplitToPages.pdf");
int pageCount = 1;
// Scorri tutte le pagine
foreach (Page pdfPage in pdfDocument.Pages)
{
	Document newDocument = new Document();
	newDocument.Pages.Add(pdfPage);
	newDocument.Save(dataDir + "page_" + pageCount + "_out" + ".pdf");
	pageCount++;
}

```

## Conclusione
In questo tutorial, abbiamo imparato come dividere un documento PDF in singole pagine utilizzando Aspose.PDF per .NET. Seguendo questa guida passo-passo, puoi dividere facilmente un documento PDF in più file PDF, ciascuno contenente una singola pagina. Aspose.PDF offre un'API potente e flessibile per lavorare con i documenti PDF nei tuoi progetti. Ora puoi utilizzare questa funzione per eseguire operazioni di suddivisione di documenti PDF in base alle tue esigenze specifiche.

### FAQ

#### D: Come posso dividere un documento PDF in singole pagine utilizzando Aspose.PDF per .NET?

R: Per dividere un documento PDF in singole pagine utilizzando Aspose.PDF per .NET, puoi seguire questi passaggi:

1. Impostare la directory del documento specificando il percorso in cui si trova il file PDF originale e dove si desidera salvare i file PDF divisi. Sostituisci "LA TUA CARTELLA DEI DOCUMENTI" con il percorso appropriato.
2.  Apri il documento PDF da dividere utilizzando il file`Document` classe di Aspose.PDF. Assicurati di specificare il percorso corretto del documento PDF originale.
3. Passa attraverso tutte le pagine del documento PDF usando un loop.
4.  Per ogni pagina, crea un nuovo documento utilizzando il file`Document` class e aggiungi quella pagina a questo nuovo documento usando il file`Add()` metodo del`Pages` proprietà.
5.  Salva il nuovo documento con un nome file univoco per ogni pagina utilizzando il file`Save()` metodo del`Document` classe.

#### D: La divisione del documento PDF influirà sul file PDF originale?

R: No, la divisione del documento PDF non influirà sul file PDF originale. Ogni pagina viene copiata in un nuovo documento e i nuovi documenti vengono salvati separatamente, lasciando intatto il file PDF originale.

#### D: Posso specificare un formato di file diverso per le pagine divise, come immagini o file di testo?

R: Il codice sorgente C# fornito mostra come suddividere il documento PDF in file PDF separati per ogni pagina. Tuttavia, è possibile modificare il codice per salvare le pagine divise in altri formati, ad esempio immagini o file di testo, a seconda dei requisiti specifici.

#### D: Esiste un limite al numero di pagine che possono essere suddivise utilizzando Aspose.PDF per .NET?

R: Non esiste un limite specifico imposto da Aspose.PDF per .NET sul numero di pagine che possono essere suddivise. Tuttavia, la quantità di memoria e le risorse disponibili nel sistema possono influire sulle prestazioni quando si lavora con un numero elevato di pagine.

#### D: Posso dividere un intervallo specifico di pagine dal documento PDF?

R: Sì, puoi modificare il codice sorgente fornito per dividere un intervallo specifico di pagine dal documento PDF. Invece di scorrere tutte le pagine, puoi implementare la logica per selezionare un intervallo specifico di pagine e creare nuovi documenti solo per quelle pagine.