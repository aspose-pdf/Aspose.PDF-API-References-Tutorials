---
title: Determina la password corretta
linktitle: Determina la password corretta
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come determinare la password corretta per un file PDF con Aspose.PDF per .NET.
type: docs
weight: 30
url: /it/net/programming-with-security-and-signatures/determine-correct-password/
---

In questo tutorial, ti guideremo attraverso il processo di determinazione della password corretta per un file PDF utilizzando Aspose.PDF per .NET. Questa funzione consente di verificare se un file PDF è protetto da password e trovare la password corretta da un elenco predefinito.

## Passaggio 1: prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

- Conoscenza base del linguaggio di programmazione C#
- Installazione di Visual Studio sul tuo computer
- Libreria Aspose.PDF per .NET installata

## Passaggio 2: configurazione dell'ambiente

Per iniziare, segui questi passaggi per configurare il tuo ambiente di sviluppo:

1. Apri Visual Studio e crea un nuovo progetto C#.
2. Importa gli spazi dei nomi richiesti nel tuo file di codice:

```csharp
using Aspose.Pdf;
```

## Passaggio 3: caricamento del file PDF di origine

Il primo passo è caricare il file PDF di origine che vuoi verificare. In questo esempio, supponiamo di avere un file PDF denominato "IsPasswordProtected.pdf" nella directory specificata.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
```

Assicurati di sostituire i segnaposto con le posizioni effettive del tuo file PDF.

## Passaggio 4: determinare la crittografia del PDF di origine

 Dopo aver caricato il file PDF di origine, puoi determinare se è crittografato utilizzando il file`IsEncrypted` metodo del`PdfFileInfo` oggetto.

```csharp
Console.WriteLine("The file is password protected: " + info.IsEncrypted);
```

Questa dichiarazione mostra se il file PDF è protetto da password o meno.

## Passaggio 5: trovare la password corretta

Successivamente, cercheremo la password corretta utilizzando un elenco predefinito di password. Esaminiamo ogni password nell'elenco e proviamo a caricare il documento PDF con quella password.

```csharp
String[] passwords = new String[5] { "test", "test1", "test2", "test3", "sample" };
for (int passwordcount = 0; passwordcount < passwords.Length; passwordcount++)
{
try
{
Document doc = new Document(dataDir + "IsPasswordProtected.pdf", passwords[passwordcount]);
if (doc.Pages.Count > 0)
Console.WriteLine("The document contains " + doc.Pages.Count + " pages.");
}
catch (InvalidPasswordException)
{
Console.WriteLine("The password " + passwords[passwordcount] + " is not correct.");
}
}
```

Questo ciclo verifica ogni parola di passaggio dall'elenco. Se la password è corretta, viene visualizzato il numero di pagine nel documento. In caso contrario, viene visualizzato un messaggio che indica che la password non è corretta.


### Esempio di codice sorgente per determinare la password corretta utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";            
// Carica il file PDF di origine
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
// Determina se il PDF di origine è crittografato
Console.WriteLine("File is password protected " + info.IsEncrypted);
String[] passwords = new String[5] { "test", "test1", "test2", "test3", "sample" };
for (int passwordcount = 0; passwordcount < passwords.Length; passwordcount++)
{
	try
	{
		Document doc = new Document(dataDir + "IsPasswordProtected.pdf", passwords[passwordcount]);
		if (doc.Pages.Count > 0)
			Console.WriteLine("Number of Page in document are = " + doc.Pages.Count);
	}
	catch (InvalidPasswordException)
	{
		Console.WriteLine("Password = " + passwords[passwordcount] + "  is not correct");
	}
}
```

## Conclusione

Congratulazioni! Hai determinato con successo la password corretta per un file PDF utilizzando Aspose.PDF per .NET. Questo tutorial ha coperto il processo passo dopo passo, dalla verifica della crittografia dei file alla ricerca della password corretta da un elenco predefinito. Ora puoi utilizzare questa funzione per controllare e trovare la password corretta dei tuoi file PDF.