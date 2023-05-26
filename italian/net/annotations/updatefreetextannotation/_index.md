---
title: Aggiorna l'annotazione di testo libero
linktitle: Aggiorna l'annotazione di testo libero
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiornare la funzione di annotazione del testo libero di Aspose.PDF per .NET utilizzando il codice sorgente C#.
type: docs
weight: 160
url: /it/net/annotations/updatefreetextannotation/
---
In questo articolo, forniremo una guida dettagliata per spiegare il seguente codice sorgente C# della funzione Aggiorna annotazione testo libero di Aspose.PDF per .NET. Esamineremo ogni riga di codice e spiegheremo cosa fa, così anche i principianti possono capirlo.

Ora spieghiamo passo dopo passo ogni riga del codice precedente:

## Passaggio 1: impostazione della directory dei documenti

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

In questa riga, stiamo impostando il percorso della directory che contiene il documento PDF che vogliamo aggiornare.

## Passaggio 2: apertura del documento PDF

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

 Qui stiamo aprendo il documento PDF utilizzando Aspose.PDF`Document` class e specificando il percorso del file PDF di input.

## Passaggio 3: aggiornare la dimensione del carattere e il colore dell'annotazione di testo libero

```csharp
(doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.FontSize = 18;
(doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.Color = System.Drawing.Color.Green;
```

 In questo passaggio, stiamo aggiornando la dimensione del carattere e il colore della prima annotazione di testo libero sulla seconda pagina del documento PDF. Lo stiamo facendo accedendo al file`TextStyle` proprietà del`FreeTextAnnotation` oggetto e impostando il suo`FontSize` E`Color` proprietà a 18 e Green, rispettivamente.

## Passaggio 4: gestione delle eccezioni

```csharp
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

 Questo è uno standard`try-catch` blocco che rileva eventuali eccezioni che possono verificarsi durante l'esecuzione del codice e stampa il messaggio di errore sulla console.

## Conclusione

In questo articolo, abbiamo fornito una guida dettagliata per spiegare il codice sorgente C# della funzione Aggiorna annotazione di testo libero di Aspose.PDF per .NET. Seguendo questi passaggi, puoi aggiornare facilmente la dimensione del carattere e il colore delle annotazioni di testo libero nei tuoi documenti PDF utilizzando Aspose.PDF per .NET.

### Esempio di codice sorgente per l'aggiornamento dell'annotazione di testo libero utilizzando Aspose.PDF per .NET

Prima di addentrarci nella spiegazione del codice, diamo prima un'occhiata al codice stesso. Questo esempio di codice mostra come aggiornare le proprietà di un'annotazione di testo libero in un documento PDF utilizzando Aspose.PDF per .NET.

```csharp
try
{
    // Il percorso della directory dei documenti.
    string dataDir = "YOUR DOCUMENT DIRECTORY";

    // Apri documento
    Document doc1 = new Document(dataDir + "input.pdf");

    // Imposta la dimensione del carattere e il colore dell'annotazione:
    (doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.FontSize = 18;
    (doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.Color = System.Drawing.Color.Green;
                
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```