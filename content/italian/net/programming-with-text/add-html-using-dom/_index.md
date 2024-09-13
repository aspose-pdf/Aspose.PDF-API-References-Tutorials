---
title: Aggiungere HTML utilizzando DOM
linktitle: Aggiungere HTML utilizzando DOM
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come aggiungere contenuto HTML utilizzando DOM in Aspose.PDF per .NET.
type: docs
weight: 40
url: /it/net/programming-with-text/add-html-using-dom/
---
Questo tutorial ti guiderà attraverso il processo di aggiunta di contenuto HTML tramite DOM (Document Object Model) in Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato sul computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito web ufficiale di Aspose o usare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importare gli spazi dei nomi richiesti
Nel file di codice in cui vuoi aggiungere il contenuto HTML, aggiungi le seguenti direttive using all'inizio del file:

```csharp
using Aspose.Pdf;
```

## Passaggio 3: impostare la directory del documento e il percorso del file di output
 Nel codice, individua la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i tuoi documenti.

## Passaggio 4: creare un nuovo oggetto Documento
 Crea un'istanza di un nuovo`Document` oggetto aggiungendo la seguente riga di codice:

```csharp
Document doc = new Document();
```

## Passaggio 5: aggiungere una pagina al documento
 Aggiungere una nuova pagina al documento utilizzando il`Add` metodo del`Pages` raccolta. Nel codice fornito, la nuova pagina è assegnata alla variabile`page`.

```csharp
Page page = doc.Pages.Add();
```

## Passaggio 6: creare un HtmlFragment con il contenuto HTML
 Crea un'istanza`HtmlFragment` oggetto e fornire il contenuto HTML desiderato. Nel codice fornito, il contenuto HTML è assegnato alla variabile`titel`È possibile modificare il contenuto HTML in base alle proprie esigenze.

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

## Passaggio 7: impostare le informazioni sul margine
Se necessario, regola il margine inferiore e superiore del frammento HTML. Nel codice fornito, il margine inferiore è impostato su 10 e il margine superiore è impostato su 200.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 200;
```

## Passaggio 8: aggiungere HtmlFragment alla pagina
 Aggiungere il`HtmlFragment` oggetto alla raccolta di paragrafi della pagina.

```csharp
page.Paragraphs.Add(title);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

## Passaggio 9: Salvare il documento PDF
 Salvare il documento PDF utilizzando`Save` metodo del`Document` oggetto. Specifica il percorso del file di output impostato nel passaggio 3.

```csharp
doc.Save(dataDir);
```

## Passaggio 10: visualizzare il messaggio di successo
Visualizza un messaggio di successo insieme al percorso in cui è stato salvato il file PDF.

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

### Esempio di codice sorgente per aggiungere HTMLUsando DOM usando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un'istanza dell'oggetto Documento
Document doc = new Document();
// Aggiungi una pagina alla raccolta di pagine del file PDF
Page page = doc.Pages.Add();
// Crea un'istanza di HtmlFragment con contenuti HTML
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
Hai aggiunto con successo contenuto HTML usando DOM in Aspose.PDF per .NET. Il file PDF risultante può ora essere trovato nel percorso del file di output specificato.

### Domande frequenti

#### D: Qual è l'obiettivo di questo tutorial?

R: Questo tutorial ha lo scopo di fornire una guida passo passo su come aggiungere contenuto HTML a un documento PDF utilizzando il Document Object Model (DOM) in Aspose.PDF per .NET. Include frammenti di codice sorgente C# per aiutarti a comprendere e implementare il processo.

#### D: Quali namespace devo importare per questo tutorial?

A: Nel file di codice in cui intendi aggiungere contenuto HTML, importa il seguente namespace all'inizio del file:

```csharp
using Aspose.Pdf;
```

#### D: Come faccio a specificare la directory del documento e il percorso del file di output?

 A: Nel codice, trova la riga`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory del documento.

#### D: Come si crea un oggetto Documento?

 A: Nel passaggio 4, crea un nuovo`Document` oggetto aggiungendo la seguente riga di codice:

```csharp
Document doc = new Document();
```

#### D: Come posso aggiungere una pagina al documento?

 A: Nel passaggio 5, aggiungerai una nuova pagina al documento utilizzando`Add` metodo del`Pages` collezione:

```csharp
Page page = doc.Pages.Add();
```

#### D: Come posso impostare il contenuto HTML utilizzando il DOM?

 A: Nel passaggio 6, creerai un`HtmlFragment` oggetto e assegnargli il contenuto HTML desiderato. Il contenuto HTML viene assegnato alla variabile`titel`:

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

#### D: Posso modificare il margine del contenuto HTML?

R: Sì, nel passaggio 7 puoi modificare i margini inferiore e superiore del frammento HTML in base alle tue esigenze:

```csharp
titel.Margin.Bottom = 10;
titel.Margin.Top = 200;
```

#### D: Come posso aggiungere HTMLFragment al documento PDF?

 A: Nel passaggio 8, aggiungerai il`HtmlFragment` oggetto (`titel`) alla raccolta di paragrafi della pagina:

```csharp
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

#### D: Come posso salvare il documento PDF risultante?

 A: Dopo aver aggiunto il contenuto HTML e regolato i margini, utilizzare`Save` metodo del`Document` oggetto per salvare il documento PDF:

```csharp
doc.Save(dataDir);
```

#### D: Esiste un modo per verificare se il processo è andato a buon fine?

R: Certamente, nel passaggio 10 viene visualizzato un messaggio di successo insieme al percorso in cui è stato salvato il file PDF:

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

#### D: Qual è il messaggio più importante da trarre da questo tutorial?

R: Seguendo questo tutorial, hai imparato con successo come utilizzare il Document Object Model (DOM) in Aspose.PDF per .NET per aggiungere contenuto HTML a un documento PDF. Questa conoscenza ti consente di migliorare le tue capacità di generazione di PDF.