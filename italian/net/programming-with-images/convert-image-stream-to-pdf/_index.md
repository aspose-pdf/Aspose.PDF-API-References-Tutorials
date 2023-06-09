---
title: Converti flusso di immagini in PDF
linktitle: Converti flusso di immagini in PDF
second_title: Aspose.PDF per riferimento API .NET
description: Converti facilmente un flusso di immagini in un file PDF con Aspose.PDF per .NET.
type: docs
weight: 70
url: /it/net/programming-with-images/convert-image-stream-to-pdf/
---

Questa guida ti guiderà passo dopo passo su come convertire un flusso di immagini in un file PDF utilizzando Aspose.PDF per .NET. Assicurati di aver già configurato il tuo ambiente e procedi nel seguente modo:

## Passaggio 1: definire la directory dei documenti

 Prima di iniziare, assicurati di impostare la directory corretta per i documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso della directory in cui si trova l'immagine.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: creare un'istanza di un oggetto Document

 In questo passaggio, istanziamo a`Document` oggetto utilizzando il costruttore vuoto del`Aspose.Pdf.Document` classe.

```csharp
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

## Passaggio 3: aggiungi una pagina al documento PDF

 Aggiungere una pagina al documento PDF utilizzando il file`Add` metodo del`Pages` oggetto di`pdf1`.

```csharp
Aspose.Pdf.Page sec = pdf1.Pages.Add();
```

## Passaggio 4: leggere il flusso di immagini

 In questo passaggio creeremo un file`FileStream` oggetto per leggere il file immagine dal flusso.

```csharp
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
```

## Passaggio 5: leggere l'immagine in un array di byte

 Leggere l'immagine dal flusso e memorizzarla in un array di byte utilizzando il file`Read` metodo del`fs` oggetto.

```csharp
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
```

## Passaggio 6: creare un oggetto MemoryStream dall'array di byte

 Creare un`MemoryStream` oggetto dall'array di byte contenente l'immagine.

```csharp
MemoryStream ms = new MemoryStream(data);
```

## Passaggio 7: creare un oggetto immagine

 In questo passaggio, creeremo un file`Image` oggetto utilizzando il`Aspose.Pdf.Image` classe. Specificare il flusso dell'immagine utilizzando il file`ImageStream` proprietà e passare il`ms` oggetto che abbiamo creato in precedenza.

```csharp
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
imageht. ImageStream = ms;
```

## Passaggio 8: aggiungere l'oggetto Immagine alla raccolta Paragrafi

 Aggiungi il`imageht` opporsi al`Paragraphs` raccolta del`sec` sezione.

```csharp
sec.Paragraphs.Add(imageht);
```

## Passaggio 9: salvare il documento PDF

 Salvare il documento PDF utilizzando il file`Save` metodo del`pdf1` oggetto. Specificare il percorso di output del file PDF.

```csharp
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
```

## Passaggio 10: chiudere l'oggetto MemoryStream

 Chiudi il`ms` oggetto utilizzando il`Close` metodo per liberare le risorse.

```csharp
ms. Close();
```

### Codice sorgente di esempio per Converti flusso di immagini in PDF utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Crea un'istanza di Document chiamando il suo costruttore vuoto
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Aggiungi una pagina nel documento pdf
Aspose.Pdf.Page sec = pdf1.Pages.Add();
// Crea un oggetto FileStream per leggere il file imag
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
// Leggere l'immagine nell'array Byte
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
// Crea un oggetto MemoryStream dall'array Byte dell'immagine
MemoryStream ms = new MemoryStream(data);
// Crea un oggetto immagine
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
// Specificare l'origine dell'immagine come MemoryStream
imageht.ImageStream = ms;
// Aggiungi l'oggetto immagine nella raccolta Paragrafi della sezione
sec.Paragraphs.Add(imageht);
// Salva il Pdf
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
// Chiudere l'oggetto MemoryStream
ms.Close();
```

## Conclusione

Congratulazioni! Hai convertito con successo un flusso di immagini in un file PDF utilizzando Aspose.PDF per .NET. Il file PDF generato viene salvato nella directory specificata. Ora puoi utilizzare questo file PDF nei tuoi progetti o applicazioni.