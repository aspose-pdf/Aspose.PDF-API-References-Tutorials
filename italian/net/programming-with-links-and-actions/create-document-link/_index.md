---
title: Crea collegamento documento
linktitle: Crea collegamento documento
second_title: Aspose.PDF per riferimento API .NET
description: Crea facilmente collegamenti ad altri documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 30
url: /it/net/programming-with-links-and-actions/create-document-link/
---

Il collegamento a un altro documento in un file PDF consente di creare collegamenti cliccabili che reindirizzano gli utenti ad altri documenti PDF. Con Aspose.PDF per .NET, puoi facilmente creare tali collegamenti seguendo il seguente codice sorgente:

## Passaggio 1: importa le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco la direttiva di importazione necessaria:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Passaggio 2: imposta il percorso della cartella dei documenti

 In questo passaggio, è necessario specificare il percorso della cartella contenente il file PDF a cui si desidera aggiungere un collegamento a un altro documento. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel seguente codice con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 3: apri il documento PDF

Ora apriremo il documento PDF al quale vogliamo aggiungere il collegamento ad un altro documento utilizzando il seguente codice:

```csharp
Document document = new Document(dataDir + "CreateDocumentLink.pdf");
```

## Passaggio 4: creare il collegamento a un altro documento

 In questo passaggio, creeremo il collegamento a un altro documento utilizzando il file`LinkAnnotation` annotazione. Specificheremo le coordinate e l'area del collegamento, nonché l'azione di navigazione verso un documento esterno. Ecco il codice corrispondente:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
```

## Passaggio 5: salvare il file aggiornato

Ora salviamo il file PDF aggiornato utilizzando l'estensione`Save` metodo del`document` oggetto. Ecco il codice corrispondente:

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document. Save(dataDir);
```

### Esempio di codice sorgente per Crea collegamento documento utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document document = new Document(dataDir+ "CreateDocumentLink.pdf");
// Crea collegamento
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
dataDir = dataDir + "CreateDocumentLink_out.pdf";
// Salva documento aggiornato
document.Save(dataDir);
Console.WriteLine("\nDocument link created successfully.\nFile saved at " + dataDir);            
```

## Conclusione

Congratulazioni! Ora hai una guida passo passo per il collegamento ad altri documenti con Aspose.PDF per .NET. Puoi utilizzare questo codice per creare collegamenti cliccabili nei tuoi file PDF, reindirizzando gli utenti ad altri documenti.

Assicurati di controllare la documentazione ufficiale di Aspose.PDF per ulteriori informazioni sulle funzionalità avanzate dei collegamenti interattivi.