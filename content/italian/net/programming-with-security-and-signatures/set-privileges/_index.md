---
title: Imposta i privilegi nel file PDF
linktitle: Imposta i privilegi nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Imposta facilmente i privilegi di accesso nel file PDF con Aspose.PDF per .NET.
type: docs
weight: 100
url: /it/net/programming-with-security-and-signatures/set-privileges/
---
Spesso è necessario impostare privilegi di accesso specifici nel file PDF. Con Aspose.PDF per .NET, puoi facilmente impostare i privilegi di accesso utilizzando il seguente codice sorgente:

## Passaggio 1: importa le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco le direttive di importazione necessarie:

```csharp
using Aspose.Pdf;
```

## Passaggio 2: imposta il percorso della cartella dei documenti

 In questo passaggio, devi specificare il percorso della cartella contenente il file PDF che desideri modificare. Sostituire`"YOUR DOCUMENTS DIRECTORY"`nel seguente codice con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 3: carica il file PDF di origine

Ora caricheremo il file PDF sorgente utilizzando il seguente codice:

```csharp
using (Document document = new Document(dataDir + "input.pdf"))
```

## Passaggio 4: imposta i privilegi di accesso

 In questo passaggio istanziaremo il file`DocumentPrivilege` oggetto per impostare i privilegi di accesso desiderati. È possibile applicare restrizioni su tutti i privilegi utilizzando`DocumentPrivilege.ForbidAll` . Ad esempio, se desideri consentire solo la lettura dello schermo, puoi impostare`AllowScreenReaders` A`true`. Ecco il codice corrispondente:

```csharp
DocumentPrivilege documentPrivilege = DocumentPrivilege.ForbidAll;
documentPrivilege.AllowScreenReaders = true;
```

## Passaggio 5: crittografa e salva il documento

 Infine, possiamo crittografare il documento PDF con una password utente e proprietario utilizzando`Encrypt` e specificando l'algoritmo di crittografia desiderato. Quindi salviamo il documento aggiornato. Ecco il codice corrispondente:

```csharp
document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
document.Save(dataDir + "SetPrivileges_out.pdf");
```

### Codice sorgente di esempio per Imposta privilegi utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Carica un file PDF di origine
using (Document document = new Document(dataDir + "input.pdf"))
{
	// Istanziare l'oggetto Privilegi documento
	// Applicare restrizioni su tutti i privilegi
	DocumentPrivilege documentPrivilege = DocumentPrivilege.ForbidAll;
	// Consenti solo la lettura dello schermo
	documentPrivilege.AllowScreenReaders = true;
	// Crittografare il file con la password Utente e Proprietario.
	// È necessario impostare la password, in modo che una volta che l'utente visualizza il file con la password utente,
	// È abilitata solo l'opzione di lettura dello schermo
	document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
	// Salva documento aggiornato
	document.Save(dataDir + "SetPrivileges_out.pdf");
}
```

## Conclusione

Congratulazioni! Ora hai una guida passo passo per impostare i privilegi di accesso per un documento PDF utilizzando Aspose.PDF per .NET. Puoi utilizzare questo codice per applicare restrizioni specifiche e proteggere i tuoi file PDF secondo necessità.

Assicurati di controllare la documentazione ufficiale Aspose.PDF per ulteriori informazioni sulla sicurezza avanzata dei documenti PDF e sulle funzionalità di gestione dei privilegi di accesso.

### Domande frequenti sull'impostazione dei privilegi nel file PDF

#### D: Perché dovrei impostare i privilegi di accesso in un file PDF?

R: L'impostazione dei privilegi di accesso ti consente di controllare il modo in cui gli utenti interagiscono con i tuoi documenti PDF. Puoi limitare azioni come stampa, copia e modifica per migliorare la sicurezza dei documenti.

#### D: Come posso trarre vantaggio dall'impostazione dei privilegi di accesso utilizzando Aspose.PDF per .NET?

R: Aspose.PDF per .NET fornisce un modo semplice per implementare i privilegi di accesso, dandoti il potere di personalizzare le autorizzazioni utente e proteggere i contenuti sensibili.

#### D: Posso applicare privilegi diversi a utenti diversi?

R: Sì, puoi impostare privilegi di accesso specifici per diversi gruppi di utenti, consentendoti di ottimizzare l'accesso ai documenti in base ai ruoli utente.

#### D: Quali sono alcuni privilegi di accesso comuni che posso impostare?

R: I privilegi di accesso comuni includono consentire o vietare azioni quali la stampa, la copia di testo o immagini, la modifica del documento e la compilazione dei campi del modulo.

#### D: In che modo l'impostazione dei privilegi di lettura dello schermo migliora l'accessibilità dei documenti?

R: L'abilitazione del privilegio di lettura dello schermo garantisce che gli utenti possano accedere al contenuto del PDF utilizzando lettori di schermo, migliorando l'accessibilità per le persone ipovedenti.

#### D: Posso impostare la protezione tramite password insieme ai privilegi di accesso?

R: Assolutamente sì, puoi crittografare il tuo documento PDF con password applicando i privilegi di accesso. Ciò fornisce un ulteriore livello di sicurezza.

#### D: Esiste un modo per revocare i privilegi di accesso dopo averli applicati?

R: Una volta applicati i privilegi di accesso e crittografato il documento, gli utenti avranno bisogno della password appropriata per accedere al contenuto. I privilegi possono essere modificati alterando il codice sorgente.

#### D: Ci sono considerazioni sulle prestazioni quando si impostano i privilegi di accesso?

R: L'impatto sulle prestazioni è minimo, poiché le impostazioni dei privilegi di accesso vengono applicate durante la crittografia, che è un processo rapido.

#### D: Posso applicare i privilegi di accesso a un documento PDF esistente?

R: Sì, puoi utilizzare Aspose.PDF per .NET per applicare i privilegi di accesso sia ai documenti PDF nuovi che a quelli esistenti.