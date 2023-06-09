---
title: Crittografare
linktitle: Crittografare
second_title: Aspose.PDF per riferimento API .NET
description: Crittografa in modo sicuro i tuoi file PDF con Aspose.PDF per .NET.
type: docs
weight: 60
url: /it/net/programming-with-security-and-signatures/encrypt/
---

La crittografia dei file PDF è un'importante misura di sicurezza per proteggere le informazioni riservate. Con Aspose.PDF per .NET puoi facilmente crittografare i tuoi file PDF utilizzando il seguente codice sorgente:

## Passaggio 1: importa le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco le direttive di importazione necessarie:

```csharp
using Aspose.Pdf;
```

## Passaggio 2: imposta il percorso della cartella dei documenti

 In questo passaggio, è necessario specificare il percorso della cartella contenente il file PDF da crittografare. Sostituire`"YOUR DOCUMENTS DIRECTORY"` nel seguente codice con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 3: apri il documento PDF

Successivamente, devi aprire il documento PDF che desideri crittografare. Utilizzare il seguente codice per caricare il documento:

```csharp
Document document = new Document(dataDir + "Encrypt.pdf");
```

## Passaggio 4: crittografa il PDF

Ora puoi crittografare il PDF usando il seguente codice:

```csharp
document. Encrypt("user", "owner", 0, CryptoAlgorithm.RC4x128);
```

In questo esempio, utilizziamo l'algoritmo di crittografia RC4x128 con le password "utente" e "proprietario". È possibile modificare queste impostazioni secondo necessità.

## Passaggio 5: eseguire il backup del PDF crittografato

Infine, puoi salvare il PDF crittografato nella posizione specificata utilizzando il seguente codice:

```csharp
dataDir = dataDir + "Encrypt_out.pdf";
document. Save(dataDir);
```

Assicurati di specificare il percorso e il nome file desiderati per il PDF crittografato.

### Esempio di codice sorgente per Encrypt utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Apri documento
Document document = new Document(dataDir+ "Encrypt.pdf");
// Crittografa PDF
document.Encrypt("user", "owner", 0, CryptoAlgorithm.RC4x128);
dataDir = dataDir + "Encrypt_out.pdf";
// Salva PDF aggiornato
document.Save(dataDir);
Console.WriteLine("\nPDF file encrypted successfully.\nFile saved at " + dataDir);
```

## Conclusione

Congratulazioni! Ora hai una panoramica dettagliata della crittografia dei file PDF utilizzando Aspose.PDF per .NET. Puoi incorporare questo codice nei tuoi progetti per proteggere facilmente i tuoi file PDF.

Assicurati di controllare la documentazione ufficiale di Aspose.PDF per ulteriori informazioni sulla crittografia avanzata e sulle funzionalità di sicurezza.