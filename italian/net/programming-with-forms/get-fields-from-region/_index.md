---
title: Ottieni campi dalla regione nel file PDF
linktitle: Ottieni campi dalla regione nel file PDF
second_title: Aspose.PDF per riferimento API .NET
description: Ottieni facilmente campi da una regione specifica nel file PDF con Aspose.PDF per .NET.
type: docs
weight: 130
url: /it/net/programming-with-forms/get-fields-from-region/
---
In questo tutorial, ti mostreremo come ottenere i campi di una regione specifica nel file PDF usando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Passaggio 1: preparazione

Assicurati di aver importato le librerie necessarie e imposta il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: apri il file PDF

Apri il file PDF:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## Passaggio 3: creare un oggetto rettangolo per delimitare la regione

Crea un oggetto rettangolo per delimitare la regione in cui desideri ottenere i campi:

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## Passaggio 4: ottenere il modulo PDF

Ottieni il modulo PDF del documento:

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## Passaggio 5: ottieni i campi nella regione rettangolare

Ottieni i campi situati nell'area rettangolare specificata:

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

### Esempio di codice sorgente per Ottieni campi dalla regione utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri file pdf
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// Crea un oggetto rettangolo per ottenere campi in quell'area
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// Ottieni il modulo PDF
Aspose.Pdf.Forms.Form form = doc.Form;
// Ottieni campi nell'area rettangolare
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// Visualizza i nomi e i valori dei campi
foreach (Field field in fields)
{
	// Visualizza le proprietà del posizionamento dell'immagine per tutti i posizionamenti
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## Conclusione

In questo tutorial, abbiamo imparato come ottenere i campi di una regione specifica in un documento PDF utilizzando Aspose.PDF per .NET. Seguendo questi passaggi, puoi facilmente estrarre i campi situati in una data area rettangolare del tuo documento PDF usando Aspose.PDF.

### FAQ

#### D: Posso utilizzare questo metodo per ottenere campi da un'area non rettangolare in un documento PDF?

 A: No, il metodo fornito`GetFieldsInRect` è specificamente progettato per recuperare i campi situati all'interno di un'area rettangolare in un documento PDF. Se devi estrarre i campi da un'area non rettangolare, devi implementare una logica personalizzata per identificare ed estrarre i campi in base ad altri criteri, ad esempio le coordinate o i nomi dei campi.

#### D: Come posso modificare la dimensione o la posizione del rettangolo per ottenere campi da una regione diversa?

 R: Per ottenere campi da una regione diversa, puoi modificare il file`Aspose.Pdf.Rectangle` i parametri dell'oggetto utilizzati per definire il rettangolo di delimitazione. IL`Rectangle` costruttore prende quattro parametri:`x`, `y`, `width` , E`height`che rappresentano le coordinate dell'angolo in alto a sinistra e le dimensioni del rettangolo. La regolazione di questi parametri cambierà la regione da cui vengono estratti i campi.

#### D: Cosa succede se non ci sono campi all'interno dell'area rettangolare specificata?

 R: Se non ci sono campi all'interno dell'area rettangolare specificata, il`GetFieldsInRect` metodo restituirà un array vuoto. È possibile controllare la lunghezza dell'array per determinare se sono presenti campi all'interno della regione.

#### D: Posso ottenere campi da regioni sovrapposte in un documento PDF?

 R: Sì, puoi ottenere campi da regioni sovrapposte in un documento PDF creando più campi`Aspose.Pdf.Rectangle` oggetti e chiamando il`GetFieldsInRect` metodo per ciascuno di essi. Le regioni sovrapposte verranno gestite in modo indipendente e riceverai matrici di campi separate per ciascuna regione.

#### D: È possibile ottenere campi da una pagina specifica o da più pagine nel documento PDF?

R: Sì, puoi ottenere campi da una pagina specifica o da più pagine in un documento PDF. Per ottenere ciò, è possibile caricare il documento PDF, accedere alle pagine desiderate utilizzando il file`doc.Pages` raccolta e quindi applicare il`GetFieldsInRect` metodo all'area specifica di ciascuna pagina.