---
title: Dividi in pagine
linktitle: Dividi in pagine
second_title: Riferimento API Aspose.PDF per .NET
description: Guida passo passo per dividere un documento PDF in singole pagine utilizzando Aspose.PDF per .NET.
type: docs
weight: 140
url: /it/net/programming-with-pdf-pages/split-to-pages/
---
In questo tutorial, ti guideremo passo dopo passo attraverso il processo per dividere un documento PDF in singole pagine usando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come dividere un documento PDF in più file PDF, ognuno contenente una singola pagina.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

- Una conoscenza di base del linguaggio di programmazione C#
- Aspose.PDF per .NET installato nel tuo ambiente di sviluppo

## Passaggio 1: definire la directory dei documenti
Per prima cosa, devi impostare il percorso per la directory dei tuoi documenti. È qui che si trova il documento PDF che vuoi dividere. Sostituisci "YOUR DOCUMENTS DIRECTORY" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: aprire il documento PDF
 Quindi puoi aprire il documento PDF da dividere utilizzando`Document` classe di Aspose.PDF. Assicurati di specificare il percorso corretto del documento.

```csharp
Document pdfDocument = new Document(dataDir + "SplitToPages.pdf");
```

## Fase 3: Sfoglia le pagine e dividile
Ora puoi scorrere tutte le pagine del documento PDF usando un loop. Per ogni pagina, crea un nuovo documento e aggiungi quella pagina a questo nuovo documento. Quindi salva il nuovo documento usando un nome file univoco per ogni pagina.

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

// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "SplitToPages.pdf");
int pageCount = 1;
// Sfoglia tutte le pagine
foreach (Page pdfPage in pdfDocument.Pages)
{
	Document newDocument = new Document();
	newDocument.Pages.Add(pdfPage);
	newDocument.Save(dataDir + "page_" + pageCount + "_out" + ".pdf");
	pageCount++;
}

```

## Conclusione
In questo tutorial, abbiamo imparato come dividere un documento PDF in singole pagine usando Aspose.PDF per .NET. Seguendo questa guida passo passo, puoi facilmente dividere un documento PDF in più file PDF, ognuno contenente una singola pagina. Aspose.PDF offre un'API potente e flessibile per lavorare con documenti PDF nei tuoi progetti. Ora puoi usare questa funzionalità per eseguire operazioni di divisione di documenti PDF in base alle tue esigenze specifiche.

### Domande frequenti

#### D: Come posso dividere un documento PDF in singole pagine utilizzando Aspose.PDF per .NET?

A: Per dividere un documento PDF in singole pagine utilizzando Aspose.PDF per .NET, puoi seguire questi passaggi:

1. Imposta la directory dei documenti specificando il percorso in cui si trova il tuo file PDF originale e dove vuoi salvare i file PDF divisi. Sostituisci "YOUR DOCUMENTS DIRECTORY" con il percorso appropriato.
2.  Aprire il documento PDF da dividere utilizzando`Document` classe di Aspose.PDF. Assicurati di specificare il percorso corretto al documento PDF originale.
3. Scorrere tutte le pagine del documento PDF utilizzando un ciclo.
4.  Per ogni pagina, crea un nuovo documento utilizzando`Document` classe e aggiungi quella pagina a questo nuovo documento utilizzando`Add()` metodo del`Pages` proprietà.
5.  Salvare il nuovo documento con un nome file univoco per ogni pagina utilizzando`Save()` metodo del`Document` classe.

#### D: La divisione del documento PDF inciderà sul file PDF originale?

R: No, la divisione del documento PDF non inciderà sul file PDF originale. Ogni pagina viene copiata in un nuovo documento e i nuovi documenti vengono salvati separatamente, lasciando intatto il file PDF originale.

#### D: Posso specificare un formato di file diverso per le pagine divise, ad esempio immagini o file di testo?

R: Il codice sorgente C# fornito dimostra come dividere il documento PDF in file PDF separati per ogni pagina. Tuttavia, puoi modificare il codice per salvare le pagine divise in altri formati, come immagini o file di testo, a seconda delle tue esigenze specifiche.

#### D: Esiste un limite al numero di pagine che possono essere suddivise utilizzando Aspose.PDF per .NET?

R: Non esiste un limite specifico imposto da Aspose.PDF per .NET sul numero di pagine che possono essere divise. Tuttavia, la quantità di memoria e risorse disponibili nel sistema potrebbe influire sulle prestazioni quando si lavora con un numero elevato di pagine.

#### D: Posso dividere un intervallo specifico di pagine dal documento PDF?

R: Sì, puoi modificare il codice sorgente fornito per dividere un intervallo specifico di pagine dal documento PDF. Invece di scorrere tutte le pagine, puoi implementare la logica per selezionare un intervallo specifico di pagine e creare nuovi documenti solo per quelle pagine.