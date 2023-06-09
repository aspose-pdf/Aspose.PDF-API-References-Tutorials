---
title: Crea collegamento all'applicazione
linktitle: Crea collegamento all'applicazione
second_title: Aspose.PDF per riferimento API .NET
description: Crea facilmente collegamenti alle applicazioni nei tuoi file PDF con Aspose.PDF per .NET.
type: docs
weight: 20
url: /it/net/programming-with-links-and-actions/create-application-link/
---

La creazione di un collegamento all'applicazione in un documento PDF consente di creare collegamenti ad applicazioni esterne, come file eseguibili o URL. Con Aspose.PDF per .NET, puoi facilmente creare collegamenti alle app seguendo il seguente codice sorgente:

## Passaggio 1: importa le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco la direttiva di importazione necessaria:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Passaggio 2: imposta il percorso della cartella dei documenti

In questo passaggio, è necessario specificare il percorso della cartella contenente il file PDF a cui si desidera aggiungere un collegamento all'app. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel seguente codice con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 3: apri il documento PDF

Ora apriremo il documento PDF a cui vogliamo aggiungere un collegamento all'applicazione utilizzando il seguente codice:

```csharp
Document document = new Document(dataDir + "CreateApplicationLink.pdf");
```

## Passaggio 4: creare il collegamento all'applicazione

 In questo passaggio, creeremo il collegamento dell'applicazione utilizzando il file`LinkAnnotation` annotazione. Specificheremo le coordinate e l'area del collegamento, nonché l'azione di avvio dell'applicazione. Ecco il codice corrispondente:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new LaunchAction(document, dataDir + "CreateApplicationLink.pdf");
page.Annotations.Add(link);
```

## Passaggio 5: salvare il file aggiornato

Ora salviamo il file PDF aggiornato utilizzando l'estensione`Save` metodo del`document` oggetto. Ecco il codice corrispondente:

```csharp
dataDir = dataDir + "CreateApplicationLink_out.pdf";
document. Save(dataDir);
```

### Esempio di codice sorgente per Crea collegamento applicazione utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document document = new Document( dataDir + "CreateApplicationLink.pdf");
// Crea collegamento
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new LaunchAction(document, dataDir + "CreateApplicationLink.pdf");
page.Annotations.Add(link);
dataDir = dataDir + "CreateApplicationLink_out.pdf";
// Salva documento aggiornato
document.Save(dataDir);
Console.WriteLine("\nApplication link created successfully.\nFile saved at " + dataDir);
```

## Conclusione

Congratulazioni! Ora disponi di una guida dettagliata per la creazione di collegamenti alle app con Aspose.PDF per .NET. Puoi utilizzare questo codice per aggiungere collegamenti ad applicazioni esterne nei tuoi documenti PDF.

Assicurati di controllare la documentazione ufficiale di Aspose.PDF per ulteriori informazioni sulle funzionalità avanzate dei collegamenti interattivi.