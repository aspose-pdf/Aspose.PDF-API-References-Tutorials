---
title: Ottieni campi dalla regione nel file PDF
linktitle: Ottieni campi dalla regione nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Ottieni facilmente campi da una regione specifica nel file PDF con Aspose.PDF per .NET.
type: docs
weight: 130
url: /it/net/programming-with-forms/get-fields-from-region/
---
In questo tutorial, ti mostreremo come ottenere i campi di una regione specifica nel file PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Passaggio 1: preparazione

Assicurati di aver importato le librerie necessarie e di impostare il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: apri il file PDF

Apri il file PDF:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## Passaggio 3: crea un oggetto rettangolare per delimitare la regione

Crea un oggetto rettangolo per delimitare la regione in cui desideri ottenere i campi:

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## Passaggio 4: ottieni il modulo PDF

Ottieni il formato PDF del documento:

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## Passaggio 5: ottieni i campi nella regione rettangolare

Ottieni i campi situati nella regione rettangolare specificata:

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## Passaggio 6: visualizzare i nomi e i valori dei campi

Scorri i campi risultanti e visualizza i loro nomi e valori:

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### Codice sorgente di esempio per Ottieni campi dalla regione utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri il file pdf
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// Crea un oggetto rettangolo per ottenere i campi in quell'area
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// Ottieni il modulo PDF
Aspose.Pdf.Forms.Form form = doc.Form;
// Ottieni i campi nell'area rettangolare
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// Visualizza nomi e valori dei campi
foreach (Field field in fields)
{
	// Visualizza le proprietà di posizionamento delle immagini per tutti i posizionamenti
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## Conclusione

In questo tutorial, abbiamo imparato come ottenere i campi di una regione specifica in un documento PDF utilizzando Aspose.PDF per .NET. Seguendo questi passaggi, puoi facilmente estrarre i campi situati in una determinata area rettangolare del tuo documento PDF utilizzando Aspose.PDF.

### Domande frequenti

#### D: Posso utilizzare questo metodo per ottenere campi da un'area non rettangolare in un documento PDF?

 R: No, il metodo fornito`GetFieldsInRect` è specificamente progettato per recuperare i campi situati all'interno di un'area rettangolare in un documento PDF. Se devi estrarre campi da una regione non rettangolare, dovresti implementare una logica personalizzata per identificare ed estrarre i campi in base ad altri criteri, come le coordinate o i nomi dei campi.

#### D: Come posso modificare la dimensione o la posizione del rettangolo per ottenere campi da una regione diversa?

 R: Per ottenere campi da una regione diversa, puoi modificare il file`Aspose.Pdf.Rectangle` parametri dell'oggetto utilizzati per definire il rettangolo di delimitazione. IL`Rectangle` il costruttore accetta quattro parametri:`x`, `y`, `width` , E`height`che rappresentano le coordinate dell'angolo in alto a sinistra e le dimensioni del rettangolo. La regolazione di questi parametri modificherà la regione da cui vengono estratti i campi.

#### D: Cosa succede se non sono presenti campi all'interno dell'area rettangolare specificata?

 R: Se non sono presenti campi all'interno della regione rettangolare specificata, il file`GetFieldsInRect` il metodo restituirà un array vuoto. È possibile controllare la lunghezza dell'array per determinare se sono presenti campi all'interno della regione.

#### D: Posso ottenere campi da regioni sovrapposte in un documento PDF?

 R: Sì, puoi ottenere campi da regioni sovrapposte in un documento PDF creandone più`Aspose.Pdf.Rectangle` oggetti e chiamando il file`GetFieldsInRect` metodo per ciascuno di essi. Le regioni sovrapposte verranno gestite in modo indipendente e riceverai serie di campi separate per ciascuna regione.

#### D: È possibile ottenere campi da una pagina specifica o da più pagine nel documento PDF?

R: Sì, puoi ottenere campi da una pagina specifica o da più pagine in un documento PDF. Per raggiungere questo obiettivo è possibile caricare il documento PDF, accedere alle pagine desiderate utilizzando il file`doc.Pages` raccolta, quindi applicare il file`GetFieldsInRect` metodo alla regione specifica di ciascuna pagina.