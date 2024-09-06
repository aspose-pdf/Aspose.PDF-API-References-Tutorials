---
title: Korrektes Passwort in PDF-Datei ermitteln
linktitle: Korrektes Passwort in PDF-Datei ermitteln
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET das richtige Kennwort in einer PDF-Datei ermitteln.
type: docs
weight: 30
url: /de/net/programming-with-security-and-signatures/determine-correct-password/
---
In diesem Tutorial führen wir Sie durch den Prozess zur Ermittlung des richtigen Passworts in einer PDF-Datei mit Aspose.PDF für .NET. Mit dieser Funktion können Sie überprüfen, ob eine PDF-Datei kennwortgeschützt ist, und das richtige Passwort aus einer vordefinierten Liste finden.

## Schritt 1: Voraussetzungen

Stellen Sie zunächst sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Grundkenntnisse der Programmiersprache C#
- Installieren von Visual Studio auf Ihrem Computer
- Aspose.PDF-Bibliothek für .NET installiert

## Schritt 2: Umgebung einrichten

Führen Sie zunächst die folgenden Schritte aus, um Ihre Entwicklungsumgebung einzurichten:

1. Öffnen Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Importieren Sie die erforderlichen Namespaces in Ihre Codedatei:

```csharp
using Aspose.Pdf;
```

## Schritt 3: Quell-PDF-Datei laden

Der erste Schritt besteht darin, die Quell-PDF-Datei hochzuladen, die Sie überprüfen möchten. In diesem Beispiel gehen wir davon aus, dass Sie eine PDF-Datei mit dem Namen „IsPasswordProtected.pdf“ im angegebenen Verzeichnis haben.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
```

Achten Sie darauf, die Platzhalter durch die tatsächlichen Speicherorte Ihrer PDF-Datei zu ersetzen.

## Schritt 4: Quell-PDF-Verschlüsselung bestimmen

 Nachdem Sie die PDF-Quelldatei hochgeladen haben, können Sie anhand der`IsEncrypted` Methode der`PdfFileInfo` Objekt.

```csharp
Console.WriteLine("The file is password protected: " + info.IsEncrypted);
```

Diese Anweisung zeigt an, ob die PDF-Datei passwortgeschützt ist oder nicht.

## Schritt 5: Das richtige Passwort finden

Als nächstes suchen wir anhand einer vordefinierten Liste von Passwörtern nach dem richtigen Passwort. Wir gehen jedes Passwort in der Liste durch und versuchen, das PDF-Dokument mit diesem Passwort zu laden.

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

Diese Schleife prüft jedes Wort von pass aus der Liste. Wenn das Passwort richtig ist, wird die Anzahl der Seiten im Dokument angezeigt. Andernfalls wird eine Meldung angezeigt, dass das Passwort nicht richtig ist.


### Beispiel-Quellcode zum Bestimmen des richtigen Passworts mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";            
// PDF-Quelldatei laden
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
//Ermitteln Sie, ob die Quell-PDF verschlüsselt ist
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

## Abschluss

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich das richtige Passwort für eine PDF-Datei ermittelt. Dieses Tutorial behandelte den schrittweisen Prozess, von der Überprüfung der Dateiverschlüsselung bis zum Finden des richtigen Passworts aus einer vordefinierten Liste. Jetzt können Sie diese Funktion verwenden, um das richtige Passwort Ihrer PDF-Dateien zu überprüfen und zu finden.

### FAQs zum Ermitteln des richtigen Passworts in einer PDF-Datei

#### F: Was ist der Zweck dieses Tutorials?

A: Dieses Tutorial soll Sie durch den Prozess der Ermittlung des richtigen Passworts für eine PDF-Datei mit Aspose.PDF für .NET führen. Mit dieser Funktion können Sie überprüfen, ob eine PDF-Datei kennwortgeschützt ist, und versuchen, das richtige Passwort aus einer vordefinierten Liste zu finden.

#### F: Welche Voraussetzungen müssen vor dem Start erfüllt sein?

A: Bevor Sie beginnen, stellen Sie sicher, dass Sie über grundlegende Kenntnisse der Programmiersprache C# verfügen, Visual Studio auf Ihrem Computer installiert ist und die Aspose.PDF-Bibliothek für .NET installiert ist.

#### F: Wie richte ich die Entwicklungsumgebung ein?

A: Befolgen Sie die angegebenen Schritte, um Ihre Entwicklungsumgebung einzurichten, einschließlich der Erstellung eines neuen C#-Projekts in Visual Studio und des Importierens der erforderlichen Namespaces.

#### F: Wie stelle ich fest, ob eine PDF-Datei verschlüsselt ist?

 A: Verwenden Sie die`PdfFileInfo` Klasse, um die Quell-PDF-Datei zu binden. Verwenden Sie dann die`IsEncrypted`Eigenschaft, um zu bestimmen, ob die PDF-Datei kennwortgeschützt ist.

#### F: Wie finde ich das richtige Passwort für eine PDF-Datei?

A: Nachdem Sie festgestellt haben, dass die PDF-Datei verschlüsselt ist, können Sie versuchen, das richtige Passwort mithilfe einer vordefinierten Liste von Passwörtern zu finden. Der bereitgestellte Beispielcode zeigt, wie Sie die Liste durchlaufen, jedes Passwort ausprobieren und feststellen, ob das Passwort richtig ist.

#### F: Was passiert, wenn das richtige Passwort gefunden wird?

A: Wenn das richtige Passwort gefunden wird, zeigt der Beispielcode die Anzahl der Seiten im PDF-Dokument an.

#### F: Was ist, wenn das Passwort nicht korrekt ist?

 A: Wenn das Passwort nicht korrekt ist, wird der Beispielcode das`InvalidPasswordException` und es wird eine Meldung angezeigt, dass das Kennwort nicht korrekt ist.

#### F: Kann ich eine andere Passwortliste verwenden?

 A: Ja, Sie können die`passwords` Array im Beispielcode, um die Passwörter einzuschließen, die Sie testen möchten.

#### F: Woher weiß ich, dass das Passwort erfolgreich ermittelt wurde?

A: Wenn der Beispielcode das PDF-Dokument erfolgreich mit einem Passwort lädt und die Seitenzahl anzeigt, bedeutet dies, dass das richtige Passwort ermittelt wurde.

#### F: Wie kann ich die Sicherheit meiner Passwörter während des Tests gewährleisten?

A: Seien Sie vorsichtig, wenn Sie eine vordefinierte Liste von Passwörtern verwenden, und vermeiden Sie die Verwendung sensibler oder vertraulicher Passwörter zu Testzwecken. Entfernen oder ändern Sie außerdem den Testcode, bevor Sie Ihre Anwendung bereitstellen.