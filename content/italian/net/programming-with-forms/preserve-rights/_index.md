---
title: Preservare i diritti
linktitle: Preservare i diritti
second_title: Riferimento API Aspose.PDF per .NET
description: Mantieni i diritti sui moduli nei tuoi documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 210
url: /it/net/programming-with-forms/preserve-rights/
---
In questo tutorial, ti mostreremo come preservare i diritti di form in un documento PDF usando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Fase 1: Preparazione

Assicurati di aver importato le librerie necessarie e di aver impostato il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: aprire il documento

 Aprire il documento PDF di origine utilizzando un`FileStream` con autorizzazione di lettura e scrittura:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Passaggio 3: modifica i campi del modulo

Esamina tutti i campi del modulo nel documento e apporta le modifiche necessarie. In questo esempio, stiamo modificando il valore di un campo del modulo che ha "A1" nel nome:

```csharp
foreach(Field formField in pdfDocument.Form)
{
if (formField.FullName.Contains("A1"))
{
TextBoxField textBoxField = formField as TextBoxField;
textBoxField.Value = "Testing";
}
}
```

## Passaggio 4: salvare il documento aggiornato

Salvare il documento PDF modificato:

```csharp
pdfDocument.Save();
```

##  Passaggio 5: chiudere il`FileStream`

 Non dimenticare di chiudere il`FileStream` oggetto quando hai finito:

```csharp
fs. Close();
```

### Esempio di codice sorgente per Preserve Rights utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Leggi il modulo PDF sorgente con FileAccess di lettura e scrittura.
// Abbiamo bisogno del permesso ReadWrite perché dopo la modifica,
// Dobbiamo salvare i contenuti aggiornati nello stesso documento/file.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// Crea un'istanza del documento
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Ottieni valori da tutti i campi
foreach (Field formField in pdfDocument.Form)
{
	// Se il nome completo del campo contiene A1, eseguire l'operazione
	if (formField.FullName.Contains("A1"))
	{
		// Converti il campo del modulo in TextBox
		TextBoxField textBoxField = formField as TextBoxField;
		// Modifica il valore del campo
		textBoxField.Value = "Testing";
	}
}
// Salva il documento aggiornato in Save FileStream
pdfDocument.Save();
// Chiudere l'oggetto Flusso file
fs.Close();
```

## Conclusione

In questo tutorial, abbiamo imparato come preservare i diritti di un modulo in un documento PDF usando Aspose.PDF per .NET. Seguendo questi passaggi, puoi accedere facilmente ai campi del modulo e apportare modifiche specifiche preservando i permessi di accesso e scrittura.


### Domande frequenti

#### D: Posso preservare i diritti di specifici campi del modulo senza influire sugli altri nel documento PDF?

 A: Sì, utilizzando il`FullName` proprietà dei campi del modulo, è possibile selezionare campi specifici del modulo da conservare, lasciandone inalterati altri.

#### D: Posso preservare i diritti di un modulo in un documento PDF protetto da password?

R: Sì, Aspose.PDF per .NET consente di preservare i diritti di un modulo anche nei documenti PDF protetti da password, a condizione che venga specificata la password corretta per accedere al file e modificarlo.

#### D: Cosa succede se provo a modificare i campi di un modulo senza disporre dei diritti di accesso appropriati?

R: Se si tenta di modificare i campi del modulo senza i diritti di accesso appropriati, le modifiche non verranno salvate nel documento PDF e potrebbe essere visualizzato un'eccezione o un messaggio di errore.

#### D: Aspose.PDF per .NET è compatibile con tutte le versioni di .NET Framework?

R: Sì, Aspose.PDF per .NET è compatibile con tutte le versioni di .NET Framework, inclusi .NET Core e .NET Standard.

#### D: Posso preservare i diritti di modulo in un documento PDF a livello di programmazione in altri linguaggi di programmazione oltre a C#?

R: Sì, Aspose.PDF per .NET supporta vari linguaggi di programmazione, come VB.NET e ASP.NET, oltre a C#.