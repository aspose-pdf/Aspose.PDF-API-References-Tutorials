---
title: Ottieni campi dalla regione nel file PDF
linktitle: Ottieni campi dalla regione nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Ottieni facilmente campi da una regione specifica in un file PDF con Aspose.PDF per .NET.
type: docs
weight: 130
url: /it/net/programming-with-forms/get-fields-from-region/
---
In questo tutorial, ti mostreremo come ottenere i campi di una regione specifica in un file PDF usando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Fase 1: Preparazione

Assicurati di aver importato le librerie necessarie e di aver impostato il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: aprire il file PDF

Aprire il file PDF:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## Passaggio 3: creare un oggetto rettangolare per delimitare la regione

Crea un oggetto rettangolo per delimitare la regione in cui vuoi ottenere i campi:

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## Passaggio 4: Ottieni il modulo PDF

Ottieni il formato PDF del documento:

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## Passaggio 5: ottenere i campi nella regione rettangolare

Ottieni i campi situati nella regione rettangolare specificata:

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## Passaggio 6: visualizzare i nomi e i valori dei campi

Scorrere i campi risultanti e visualizzarne i nomi e i valori:

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### Esempio di codice sorgente per ottenere campi dalla regione utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri file pdf
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// Crea un oggetto rettangolo per ottenere i campi in quell'area
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// Ottieni il modulo PDF
Aspose.Pdf.Forms.Form form = doc.Form;
// Ottieni i campi nell'area rettangolare
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// Visualizza i nomi e i valori dei campi
foreach (Field field in fields)
{
	// Visualizza le proprietà di posizionamento delle immagini per tutti i posizionamenti
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## Conclusione

In questo tutorial, abbiamo imparato come ottenere i campi di una regione specifica in un documento PDF usando Aspose.PDF per .NET. Seguendo questi passaggi, puoi facilmente estrarre i campi situati in una determinata area rettangolare del tuo documento PDF usando Aspose.PDF.

### Domande frequenti

#### D: Posso usare questo metodo per ottenere campi da un'area non rettangolare in un documento PDF?

 A: No, il metodo fornito`GetFieldsInRect` è specificamente progettato per recuperare i campi situati all'interno di una regione rettangolare in un documento PDF. Se hai bisogno di estrarre campi da una regione non rettangolare, dovrai implementare una logica personalizzata per identificare ed estrarre i campi in base ad altri criteri, come coordinate o nomi di campo.

#### D: Come posso modificare le dimensioni o la posizione del rettangolo per ottenere campi da una regione diversa?

 A: Per ottenere campi da una regione diversa, puoi modificare il`Aspose.Pdf.Rectangle` parametri dell'oggetto utilizzati per definire il rettangolo di delimitazione. Il`Rectangle` il costruttore accetta quattro parametri:`x`, `y`, `width` , E`height`che rappresentano le coordinate dell'angolo in alto a sinistra e le dimensioni del rettangolo. La regolazione di questi parametri cambierà la regione da cui vengono estratti i campi.

#### D: Cosa succede se non ci sono campi all'interno dell'area rettangolare specificata?

 A: Se non ci sono campi all'interno della regione rettangolare specificata, il`GetFieldsInRect` restituirà un array vuoto. Puoi controllare la lunghezza dell'array per determinare se ci sono campi all'interno della regione.

#### D: Posso ottenere campi da aree sovrapposte in un documento PDF?

 A: Sì, puoi ottenere campi da regioni sovrapposte in un documento PDF creando più`Aspose.Pdf.Rectangle` oggetti e chiamando il`GetFieldsInRect` metodo per ognuno di essi. Le regioni sovrapposte saranno gestite in modo indipendente e riceverai array separati di campi per ogni regione.

#### D: È possibile ottenere campi da una pagina specifica o da più pagine del documento PDF?

R: Sì, puoi ottenere campi da una pagina specifica o da più pagine in un documento PDF. Per ottenere questo, puoi caricare il documento PDF, accedere alle pagine desiderate utilizzando`doc.Pages` raccolta, e quindi applicare il`GetFieldsInRect` metodo alla regione specifica di ogni pagina.