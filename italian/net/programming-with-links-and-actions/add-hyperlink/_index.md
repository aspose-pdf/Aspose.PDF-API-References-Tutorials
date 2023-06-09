---
title: Aggiungi collegamento ipertestuale
linktitle: Aggiungi collegamento ipertestuale
second_title: Aspose.PDF per riferimento API .NET
description: Aggiungi facilmente collegamenti ipertestuali interattivi nei tuoi file PDF con Aspose.PDF per .NET.
type: docs
weight: 10
url: /it/net/programming-with-links-and-actions/add-hyperlink/
---

L'aggiunta di collegamenti ipertestuali in un documento PDF consente di creare collegamenti ipertestuali interattivi ad altre pagine, siti Web o destinazioni nel documento. Con Aspose.PDF per .NET, puoi facilmente aggiungere collegamenti ipertestuali seguendo il seguente codice sorgente:

## Passaggio 1: importa le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco la direttiva di importazione necessaria:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

## Passaggio 2: imposta il percorso della cartella dei documenti

 In questo passaggio, è necessario specificare il percorso della cartella contenente il file PDF a cui si desidera aggiungere un collegamento ipertestuale. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel seguente codice con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 3: apri il documento PDF

Ora apriremo il documento PDF a cui vogliamo aggiungere un collegamento ipertestuale utilizzando il seguente codice:

```csharp
Document document = new Document(dataDir + "AddHyperlink.pdf");
```

## Passaggio 4: creare un collegamento

 In questo passaggio, creeremo un collegamento ipertestuale utilizzando il file`LinkAnnotation` annotazione. Specifichiamo i dati di contatto e l'area del collegamento, il tipo di collegamento e il contenuto del collegamento. Ecco il codice corrispondente:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
Border border = new Border(link);
border. Width = 0;
link. Border = border;
link. Action = new GoToURIAction("www.aspose.com");
page.Annotations.Add(link);
```

## Passaggio 5: aggiungi testo aggiuntivo

 Oltre al collegamento ipertestuale, possiamo anche aggiungere del testo aggiuntivo utilizzando il file`FreeTextAnnotation` annotazione. Specificheremo le coordinate, l'aspetto del testo e il contenuto del testo. Ecco il codice corrispondente:

```csharp
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System .Drawing.Color.Blue));
textAnnotation.Contents = "Link to Aspose website";
textAnnotation. Border = border;
document.Pages[1].Annotations.Add(textAnnotation);
```

## Passaggio 6: salvare il file aggiornato

Ora salviamo il file PDF aggiornato utilizzando l'estensione`Save` metodo del`document` oggetto. Ecco il codice corrispondente:

```csharp
dataDir = dataDir + "AddHyperlink_out.pdf";
document. Save(dataDir);
```

### Esempio di codice sorgente per Aggiungi collegamento ipertestuale utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document document = new Document(dataDir + "AddHyperlink.pdf");
// Crea collegamento
Page page = document.Pages[1];
//Crea oggetto annotazione collegamento
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
// Crea un oggetto bordo per LinkAnnotation
Border border = new Border(link);
// Imposta il valore della larghezza del bordo su 0
border.Width = 0;
// Imposta il bordo per LinkAnnotation
link.Border = border;
// Specificare il tipo di collegamento come URI remoto
link.Action = new GoToURIAction("www.aspose.com");
// Aggiungi l'annotazione del collegamento alla raccolta di annotazioni della prima pagina del file PDF
page.Annotations.Add(link);
// Crea annotazioni di testo libero
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System.Drawing.Color.Blue));
// Stringa da aggiungere come testo libero
textAnnotation.Contents = "Link to Aspose website";
// Imposta il bordo per l'annotazione di testo libero
textAnnotation.Border = border;
// Aggiungi l'annotazione di testo libero alla raccolta di annotazioni della prima pagina del documento
document.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddHyperlink_out.pdf";
// Salva documento aggiornato
document.Save(dataDir);
Console.WriteLine("\nHyperlink added successfully.\nFile saved at " + dataDir);            
```

## Conclusione

Congratulazioni! Ora hai una guida passo passo per aggiungere collegamenti ipertestuali con Aspose.PDF per .NET. Puoi utilizzare questo codice per creare collegamenti interattivi nei tuoi documenti PDF.