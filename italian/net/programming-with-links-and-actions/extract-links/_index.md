---
title: Estrai link
linktitle: Estrai link
second_title: Aspose.PDF per riferimento API .NET
description: Estrai facilmente collegamenti da un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 50
url: /it/net/programming-with-links-and-actions/extract-links/
---

L'estrazione dei collegamenti da un documento PDF consente di recuperare tutti i collegamenti ipertestuali presenti nel documento. Con Aspose.PDF per .NET, puoi facilmente estrarre questi collegamenti seguendo il seguente codice sorgente:

## Passaggio 1: importare le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco la direttiva di importazione necessaria:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

## Passaggio 2: imposta il percorso della cartella dei documenti

 In questo passaggio, è necessario specificare il percorso della cartella contenente il file PDF da cui si desidera estrarre i collegamenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel seguente codice con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 3: apri il documento PDF

 Apriremo il documento PDF utilizzando il file`Document` classe. Ecco il codice corrispondente:

```csharp
Document document = new Document(dataDir + "ExtractLinks.pdf");
```

## Passaggio 4: estrarre i collegamenti

 In questo passaggio, estrarremo i collegamenti presenti nel documento PDF utilizzando il file`AnnotationSelector` classe. Ecco il codice corrispondente:

```csharp
Page page = document.Pages[1];
AnnotationSelector selector = new AnnotationSelector(new LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
page. Accept(selector);
IList<Annotation> list = selector. Selected;
Annotation annotation = (Annotation)list[0];
```

## Passaggio 5: salvare il documento aggiornato

Ora salviamo il file PDF aggiornato utilizzando l'estensione`Save` metodo del`document` oggetto. Ecco il codice corrispondente:

```csharp
dataDir = dataDir + "ExtractLinks_out.pdf";
document. Save(dataDir);
```

### Esempio di codice sorgente per estrarre collegamenti utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document document = new Document(dataDir+ "ExtractLinks.pdf");
// Estrai azioni
Page page = document.Pages[1];
AnnotationSelector selector = new AnnotationSelector(new LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
page.Accept(selector);
IList<Annotation> list = selector.Selected;
Annotation annotation = (Annotation)list[0];
dataDir = dataDir + "ExtractLinks_out.pdf";
// Salva documento aggiornato
document.Save(dataDir);
Console.WriteLine("\nLinks extracted successfully.\nFile saved at " + dataDir);
```

## Conclusione

Congratulazioni! Ora hai una guida passo-passo per estrarre collegamenti da un documento PDF utilizzando Aspose.PDF per .NET. Puoi utilizzare questo codice per recuperare tutti i collegamenti ipertestuali presenti nel documento.

Assicurati di controllare la documentazione ufficiale di Aspose.PDF per ulteriori informazioni sulle funzionalità avanzate di estrazione dei collegamenti.