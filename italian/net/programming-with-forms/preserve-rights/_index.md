---
title: Preservare i diritti
linktitle: Preservare i diritti
second_title: Aspose.PDF per riferimento API .NET
description: Conserva i diritti dei moduli nei tuoi documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 210
url: /it/net/programming-with-forms/preserve-rights/
---
In questo tutorial, ti mostreremo come preservare i diritti del modulo in un documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Passaggio 1: preparazione

Assicurati di aver importato le librerie necessarie e imposta il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: apri il documento

 Apri il documento PDF di origine utilizzando a`FileStream` con permesso di lettura e scrittura:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Passaggio 3: modifica i campi del modulo

Esamina tutti i campi del modulo nel documento e apporta le modifiche necessarie. In questo esempio, stiamo cambiando il valore di un campo modulo che ha "A1" nel suo nome:

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

Salva il documento PDF modificato:

```csharp
pdfDocument.Save();
```

##  Passaggio 5: chiudere il file`FileStream`

 Non dimenticare di chiudere il`FileStream` oggetto quando hai finito:

```csharp
fs. Close();
```

### Esempio di codice sorgente per Preserve Rights utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Leggi il modulo PDF di origine con FileAccess di lettura e scrittura.
// Abbiamo bisogno dell'autorizzazione ReadWrite perché dopo la modifica,
// Dobbiamo salvare i contenuti aggiornati nello stesso documento/file.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// Istanza documento istanza
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Ottieni valori da tutti i campi
foreach (Field formField in pdfDocument.Form)
{
	// Se il nome completo del campo contiene A1, eseguire l'operazione
	if (formField.FullName.Contains("A1"))
	{
		// Cast campo modulo come TextBox
		TextBoxField textBoxField = formField as TextBoxField;
		// Modifica il valore del campo
		textBoxField.Value = "Testing";
	}
}
// Salva il documento aggiornato in save FileStream
pdfDocument.Save();
// Chiudere l'oggetto File Stream
fs.Close();
```

## Conclusione

In questo tutorial, abbiamo imparato come preservare i diritti di un modulo in un documento PDF utilizzando Aspose.PDF per .NET. Seguendo questi passaggi, puoi accedere facilmente ai campi del modulo e apportare modifiche specifiche mantenendo i permessi di accesso e scrittura.


### FAQ

#### D: Posso preservare i diritti di campi modulo specifici senza influire su altri nel documento PDF?

 A: Sì, utilizzando il`FullName` proprietà dei campi modulo, è possibile scegliere come target campi modulo specifici per la conservazione lasciando inalterati gli altri.

#### D: Posso preservare i diritti di un modulo in un documento PDF protetto da password?

R: Sì, Aspose.PDF per .NET ti consente di conservare i diritti di un modulo anche nei documenti PDF protetti da password, purché tu fornisca la password corretta per accedere e modificare il file.

#### D: Cosa succede se tento di modificare i campi del modulo senza i diritti di accesso appropriati?

R: Se tenti di modificare i campi del modulo senza i diritti di accesso appropriati, le modifiche non verranno salvate nel documento PDF e potresti ricevere un'eccezione o un messaggio di errore.

#### D: Aspose.PDF per .NET è compatibile con tutte le versioni di .NET Framework?

R: Sì, Aspose.PDF per .NET è compatibile con tutte le versioni di .NET Framework, inclusi .NET Core e .NET Standard.

#### D: Posso conservare i diritti del modulo in un documento PDF a livello di codice in altri linguaggi di programmazione oltre a C#?

R: Sì, Aspose.PDF per .NET supporta vari linguaggi di programmazione, come VB.NET e ASP.NET, oltre a C#.