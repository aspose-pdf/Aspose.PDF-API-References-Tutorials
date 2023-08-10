---
title: Aggiungi HTML usando DOM
linktitle: Aggiungi HTML usando DOM
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere contenuto HTML utilizzando DOM in Aspose.PDF per .NET.
type: docs
weight: 40
url: /it/net/programming-with-text/add-html-using-dom/
---

Questo tutorial ti guiderà attraverso il processo di aggiunta di contenuto HTML utilizzando DOM (Document Object Model) in Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di disporre di quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato nel tuo computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito Web ufficiale di Aspose o utilizzare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa gli spazi dei nomi richiesti
Nel file di codice in cui desideri aggiungere il contenuto HTML, aggiungi le seguenti direttive using nella parte superiore del file:

```csharp
using Aspose.Pdf;
```

## Passaggio 3: impostare la directory del documento e il percorso del file di output
 Nel codice, individuare la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i documenti.

## Passaggio 4: creare un nuovo oggetto documento
 Crea un'istanza di un nuovo`Document` oggetto aggiungendo la seguente riga di codice:

```csharp
Document doc = new Document();
```

## Passaggio 5: aggiungi una pagina al documento
 Aggiungere una nuova pagina al documento utilizzando il file`Add` metodo del`Pages` collezione. Nel codice fornito, la nuova pagina è assegnata alla variabile`page`.

```csharp
Page page = doc.Pages.Add();
```

## Passaggio 6: creare un HtmlFragment con il contenuto HTML
Istanziare un`HtmlFragment` oggetto e fornire il contenuto HTML desiderato. Nel codice fornito, il contenuto HTML è assegnato alla variabile`titel`. È possibile modificare il contenuto HTML secondo necessità.

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

## Passaggio 7: impostare le informazioni sul margine
Regola il margine inferiore e superiore del frammento HTML, se necessario. Nel codice fornito, il margine inferiore è impostato su 10 e il margine superiore è impostato su 200.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 200;
```

## Passaggio 8: aggiungere HtmlFragment alla pagina
 Aggiungi il`HtmlFragment` opporsi alla raccolta di paragrafi della pagina.

```csharp
page.Paragraphs.Add(title);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

## Passaggio 9: salvare il documento PDF
 Salvare il documento PDF utilizzando il file`Save` metodo del`Document` oggetto. Specificare il percorso del file di output impostato nel passaggio 3.

```csharp
doc.Save(dataDir);
```

## Passaggio 10: visualizza il messaggio di successo
Visualizza un messaggio di successo insieme al percorso in cui è stato salvato il file PDF.

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

### Esempio di codice sorgente per Aggiungi HTMLUsing DOM utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un'istanza dell'oggetto Document
Document doc = new Document();
// Aggiungi una pagina alla raccolta di pagine di file PDF
Page page = doc.Pages.Add();
// Crea un'istanza di HtmlFragment con contnet HTML
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
// Imposta le informazioni sul margine inferiore
titel.Margin.Bottom = 10;
// Imposta le informazioni sul margine superiore
titel.Margin.Top = 200;
// Aggiungi frammento HTML alla raccolta di paragrafi della pagina
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
// Salva file PDF
doc.Save(dataDir);
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

## Conclusione
Hai aggiunto con successo il contenuto HTML utilizzando DOM in Aspose.PDF per .NET. Il file PDF risultante può ora essere trovato nel percorso del file di output specificato.