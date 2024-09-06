---
title: Imposta la data di scadenza nel file PDF
linktitle: Imposta la data di scadenza nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come impostare la data di scadenza in un file PDF utilizzando Aspose.PDF per .NET con questa guida dettagliata.
type: docs
weight: 300
url: /it/net/programming-with-document/setexpirydate/
---
Aspose.PDF per .NET è una potente libreria che fornisce varie funzionalità per lavorare con file PDF. Una di queste funzionalità è la possibilità di impostare una data di scadenza per un documento PDF. In questo tutorial, ti guideremo attraverso il processo di impostazione di una data di scadenza per un documento PDF utilizzando Aspose.PDF per .NET. 

## Passaggio 1: impostare il percorso della directory del documento

Prima di iniziare, dobbiamo impostare il percorso della directory in cui si trova il nostro documento PDF. Memorizzeremo questo percorso in una variabile chiamata "dataDir".

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: creazione di un nuovo documento PDF

 Per creare un nuovo documento PDF, dobbiamo creare un'istanza di un nuovo`Aspose.Pdf.Document` oggetto. Possiamo farlo usando il seguente codice:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Passaggio 3: aggiunta di una nuova pagina al documento PDF

Una volta creato il documento PDF, possiamo aggiungervi una nuova pagina. Possiamo farlo usando il seguente codice:

```csharp
doc.Pages.Add();
```

## Passaggio 4: aggiunta di testo al documento PDF

 Dopo aver aggiunto una pagina al documento PDF, possiamo aggiungere del testo utilizzando`Paragraphs` raccolta. Possiamo farlo usando il seguente codice:

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## Passaggio 5: impostazione della data di scadenza del PDF tramite JavaScript

Per impostare la data di scadenza del PDF, dobbiamo creare un oggetto JavaScript. Possiamo farlo usando il seguente codice:

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");

// Imposta JavaScript come azione di apertura PDF
doc.OpenAction = javaScript;
```

In questo codice impostiamo la data di scadenza a maggio 2017.

## Passaggio 6: Salvare il file PDF

 Dopo aver impostato la data di scadenza, devi salvare il file PDF. Per farlo, puoi usare il`Save` metodo del`Document` oggetto e passare il percorso in cui si desidera salvare il file PDF aggiornato.

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
// Salva documento PDF
doc.Save(dataDir);
```

### Esempio di codice sorgente per Imposta data di scadenza utilizzando Aspose.PDF per .NET

Ecco il codice sorgente di esempio completo per impostare la data di scadenza utilizzando Aspose.PDF per .NET:

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un'istanza dell'oggetto Documento
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Aggiungi pagina alla raccolta di pagine del file PDF
doc.Pages.Add();
// Aggiungi frammento di testo alla raccolta di paragrafi dell'oggetto pagina
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
// Crea un oggetto JavaScript per impostare la data di scadenza del PDF
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
// Imposta JavaScript come azione di apertura PDF
doc.OpenAction = javaScript;

dataDir = dataDir + "SetExpiryDate_out.pdf";
// Salva documento PDF
doc.Save(dataDir);
```

## Conclusione

Impostare una data di scadenza per un documento PDF usando Aspose.PDF per .NET è una funzionalità utile per garantire che il documento sia valido solo per un periodo specificato. Seguendo la guida passo passo e usando il codice sorgente C# fornito, gli sviluppatori possono facilmente impostare la data di scadenza e creare PDF con validità limitata nel tempo. Questa funzionalità può essere particolarmente utile per i documenti a cui è necessario accedere o che devono essere distribuiti per una durata limitata.

### FAQ per impostare la data di scadenza nel file PDF

#### D: Posso impostare una data di scadenza diversa per il documento PDF?

 A: Sì, puoi impostare una data di scadenza diversa per il documento PDF modificando il codice JavaScript nel passaggio 5. Nell'esempio fornito, la data di scadenza è impostata su maggio 2017. Per impostare una data di scadenza diversa, devi modificare il`year` E`month` variabili nel codice JavaScript all'anno e al mese desiderati.

#### D: Cosa succede quando il documento PDF è scaduto?

R: Quando il documento PDF è scaduto, come specificato nel codice JavaScript, il visualizzatore visualizzerà un messaggio di avviso che indica che il file è scaduto e che l'utente ne ha bisogno di uno nuovo. Questo messaggio di avviso verrà visualizzato quando il PDF viene aperto.

#### D: Posso usare un orario specifico per la data di scadenza invece che solo la data?

 A: Sì, puoi impostare un orario specifico per la data di scadenza nel codice JavaScript. Modificando il`expiry` variabile nel codice JavaScript per includere l'ora desiderata, è possibile impostare un'ora specifica per la data di scadenza.