---
title: Determina l'interruzione di riga nel file PDF
linktitle: Determina l'interruzione di riga nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come determinare le interruzioni di riga nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 130
url: /it/net/programming-with-text/determine-line-break/
---
Questo tutorial ti guiderà attraverso il processo di determinazione delle interruzioni di riga nel file PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato sul tuo computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito Web ufficiale di Aspose o utilizzare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa gli spazi dei nomi richiesti
Nel file di codice in cui desideri determinare le interruzioni di riga, aggiungi le seguenti direttive using nella parte superiore del file:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Passaggio 3: imposta la directory dei documenti
 Nel codice, individua la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i tuoi documenti.

## Passaggio 4: crea una nuova istanza del documento
 Istanziarne uno nuovo`Document` oggetto aggiungendo la seguente riga di codice:

```csharp
Document doc = new Document();
```

## Passaggio 5: aggiungi una pagina al documento
 Aggiungi una nuova pagina al documento utilizzando il file`Add` metodo del`Pages`collezione. Nel codice fornito, la nuova pagina viene assegnata alla variabile`page`.

```csharp
Page page = doc.Pages.Add();
```

## Passaggio 6: aggiungi frammenti di testo con interruzioni di riga
Crea un ciclo per aggiungere più frammenti di testo alla pagina, ciascuno contenente un paragrafo con interruzioni di riga.

```csharp
for (int i = 0; i < 4; i++)
{
     TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
     text.TextState.FontSize = 20;
     page.Paragraphs.Add(text);
}
```

## Passaggio 7: salva il documento PDF ed estrai le informazioni sull'interruzione di riga
 Salvare il documento PDF utilizzando il file`Save` metodo del`Document` oggetto. Quindi, estrai le informazioni sull'interruzione di riga utilizzando il file`GetNotifications` metodo della pagina desiderata.

```csharp
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

### Codice sorgente di esempio per Determinare l'interruzione di riga utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.");
	text.TextState.FontSize = 20;
	page.Paragraphs.Add(text);
}
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

## Conclusione
Hai determinato con successo le interruzioni di riga in un documento PDF utilizzando Aspose.PDF per .NET. Le informazioni sull'interruzione di riga sono state estratte e salvate in un file di testo.

### Domande frequenti

#### D: Qual è l'obiettivo principale di questo tutorial?

R: Questo tutorial è incentrato sulla guida dell'utente attraverso il processo di determinazione delle interruzioni di riga in un file PDF utilizzando la libreria Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari per raggiungere questo obiettivo.

#### D: Quali spazi dei nomi devo importare per questo tutorial?

R: Nel file di codice in cui desideri determinare le interruzioni di riga, importa i seguenti spazi dei nomi all'inizio del file:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### D: Come posso specificare la directory dei documenti?

 A: Nel codice, trova la riga`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

#### D: Come posso creare una nuova istanza del documento?

 R: Nel passaggio 4 creerai un'istanza di new`Document` oggetto utilizzando il codice fornito.

#### D: Come faccio ad aggiungere una pagina al documento?

 R: Nel passaggio 5, aggiungerai una nuova pagina al documento utilizzando il file`Add` metodo del`Pages` collezione.

#### D: Come posso aggiungere frammenti di testo con interruzioni di riga?

R: Nel passaggio 6 creerai un ciclo per aggiungere più frammenti di testo alla pagina, ciascuno contenente un paragrafo con interruzioni di riga.

#### D: Come posso salvare il documento PDF ed estrarre le informazioni sulle interruzioni di riga?

 R: Nel passaggio 7, salverai il documento PDF utilizzando il file`Save` metodo del`Document` oggetto. Quindi, estrarrai le informazioni sull'interruzione di riga utilizzando il file`GetNotifications` metodo della pagina desiderata e salvarlo in un file di testo.

#### D: Qual è lo scopo delle informazioni sulle interruzioni di riga estratte?

R: Le informazioni sulle interruzioni di riga estratte forniscono dettagli sulle interruzioni di riga e sulle notifiche presenti nel documento PDF. Ciò può essere utile per analizzare e comprendere come sono strutturati testo e paragrafi all'interno del documento.

#### D: Qual è il punto principale di questo tutorial?

R: Seguendo questo tutorial, hai imparato come determinare le interruzioni di riga in un documento PDF utilizzando Aspose.PDF per .NET. È possibile utilizzare queste conoscenze per estrarre e analizzare a livello di codice le informazioni sulle interruzioni di riga dai file PDF.