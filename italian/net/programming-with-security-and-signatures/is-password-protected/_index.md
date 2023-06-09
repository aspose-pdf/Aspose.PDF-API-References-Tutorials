---
title: È protetto da password
linktitle: È protetto da password
second_title: Aspose.PDF per riferimento API .NET
description: Controlla facilmente se un documento PDF è protetto da password con Aspose.PDF per .NET.
type: docs
weight: 90
url: /it/net/programming-with-security-and-signatures/is-password-protected/
---

Spesso è importante sapere se un documento PDF è protetto da password prima di elaborarlo. Con Aspose.PDF per .NET, puoi facilmente verificare se un documento PDF è protetto utilizzando il seguente codice sorgente:

## Passaggio 1: importa le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco le direttive di importazione necessarie:

```csharp
using Aspose.Pdf;
```

## Passaggio 2: imposta il percorso della cartella dei documenti

 In questo passaggio, è necessario specificare il percorso della cartella contenente il file PDF che si desidera controllare. Sostituire`"YOUR DOCUMENTS DIRECTORY"` nel seguente codice con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 3: carica il documento PDF di origine

Ora caricheremo il documento PDF di origine e verificheremo se è protetto da password utilizzando il seguente codice:

```csharp
PdfFileInfo fileInfo = new PdfFileInfo(dataDir + @"IsPasswordProtected.pdf");
```

## Passaggio 4: controlla se il PDF è protetto

 In questo passaggio, determineremo se il documento PDF è protetto da password utilizzando il file`IsEncrypted` metodo del`PdfFileInfo` oggetto. Ecco il codice corrispondente:

```csharp
bool encrypted = fileInfo.IsEncrypted;
```

## Passaggio 5: visualizzare lo stato della crittografia

 Infine, possiamo visualizzare lo stato di crittografia corrente del PDF utilizzando il file`Console.WriteLine` metodo. Ecco il codice corrispondente:

```csharp
Console.WriteLine(encrypted.ToString());
```

Il messaggio visualizzato indicherà se il documento PDF è protetto da password o meno.

### Esempio di codice sorgente per Is Password Protected using Aspose.PDF for .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Carica il documento PDF di origine
PdfFileInfo fileInfo = new PdfFileInfo(dataDir+ @"IsPasswordProtected.pdf");
//Determina che il file PDF di origine è crittografato con password
bool encrypted = fileInfo.IsEncrypted;
// MessageBox visualizza lo stato corrente relativo alla crittografia PDf
Console.WriteLine(encrypted.ToString());
```

## Conclusione

Congratulazioni! Ora hai una guida passo passo per verificare se un documento PDF è protetto da password utilizzando Aspose.PDF per .NET. Puoi integrare questo codice nei tuoi progetti per eseguire operazioni specifiche a seconda dello stato di protezione del PDF.

Assicurati di controllare la documentazione ufficiale di Aspose.PDF per ulteriori informazioni sulla sicurezza avanzata dei documenti PDF e sulle funzionalità di gestione delle password.