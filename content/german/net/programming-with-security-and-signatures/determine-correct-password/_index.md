---
title: Bestimmen Sie das richtige Passwort in der PDF-Datei
linktitle: Bestimmen Sie das richtige Passwort in der PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET das richtige Passwort in einer PDF-Datei ermitteln.
type: docs
weight: 30
url: /de/net/programming-with-security-and-signatures/determine-correct-password/
---
In diesem Tutorial führen wir Sie durch den Prozess der Ermittlung des richtigen Passworts in einer PDF-Datei mit Aspose.PDF für .NET. Mit dieser Funktion können Sie überprüfen, ob eine PDF-Datei passwortgeschützt ist, und das richtige Passwort aus einer vordefinierten Liste finden.

## Schritt 1: Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Grundkenntnisse der Programmiersprache C#
- Installieren von Visual Studio auf Ihrem Computer
- Aspose.PDF-Bibliothek für .NET installiert

## Schritt 2: Umgebungseinrichtung

Führen Sie zunächst die folgenden Schritte aus, um Ihre Entwicklungsumgebung einzurichten:

1. Öffnen Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Importieren Sie die erforderlichen Namespaces in Ihre Codedatei:

```csharp
using Aspose.Pdf;
```

## Schritt 3: Laden der Quell-PDF-Datei

Der erste Schritt besteht darin, die Quell-PDF-Datei hochzuladen, die Sie überprüfen möchten. In diesem Beispiel gehen wir davon aus, dass Sie im angegebenen Verzeichnis eine PDF-Datei mit dem Namen „IsPasswordProtected.pdf“ haben.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
```

Ersetzen Sie die Platzhalter unbedingt durch die tatsächlichen Speicherorte Ihrer PDF-Datei.

## Schritt 4: Bestimmen Sie die Quell-PDF-Verschlüsselung

Sobald Sie die Quell-PDF-Datei hochgeladen haben, können Sie mithilfe von feststellen, ob sie verschlüsselt ist`IsEncrypted` Methode der`PdfFileInfo` Objekt.

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

Diese Schleife testet jedes Passwort aus der Liste. Wenn das Passwort korrekt ist, wird die Anzahl der Seiten im Dokument angezeigt. Andernfalls wird eine Meldung angezeigt, dass das Passwort nicht korrekt ist.


### Beispielquellcode für die Bestimmung des richtigen Passworts mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";            
// Laden Sie die PDF-Quelldatei
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
// Stellen Sie fest, ob das Quell-PDF verschlüsselt ist
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

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich das richtige Passwort für eine PDF-Datei ermittelt. Dieses Tutorial behandelt den schrittweisen Prozess, von der Überprüfung der Dateiverschlüsselung bis zum Finden des richtigen Passworts aus einer vordefinierten Liste. Jetzt können Sie diese Funktion verwenden, um das richtige Passwort für Ihre PDF-Dateien zu überprüfen und zu finden.

### FAQs zum Ermitteln des richtigen Passworts in einer PDF-Datei

#### F: Was ist der Zweck dieses Tutorials?

A: Dieses Tutorial soll Sie durch den Prozess der Ermittlung des richtigen Passworts für eine PDF-Datei mit Aspose.PDF für .NET führen. Mit dieser Funktion können Sie überprüfen, ob eine PDF-Datei passwortgeschützt ist, und versuchen, das richtige Passwort aus einer vordefinierten Liste zu finden.

#### F: Welche Voraussetzungen sind vor dem Start erforderlich?

A: Bevor Sie beginnen, stellen Sie sicher, dass Sie über grundlegende Kenntnisse der Programmiersprache C# verfügen, Visual Studio auf Ihrem Computer installiert haben und die Aspose.PDF-Bibliothek für .NET installiert ist.

#### F: Wie richte ich die Entwicklungsumgebung ein?

A: Befolgen Sie die bereitgestellten Schritte, um Ihre Entwicklungsumgebung einzurichten, einschließlich der Erstellung eines neuen C#-Projekts in Visual Studio und des Imports der erforderlichen Namespaces.

#### F: Wie kann ich feststellen, ob eine PDF-Datei verschlüsselt ist?

 A: Benutzen Sie die`PdfFileInfo` Klasse zum Binden der Quell-PDF-Datei. Dann verwenden Sie die`IsEncrypted` -Eigenschaft, um festzustellen, ob die PDF-Datei kennwortgeschützt ist.

#### F: Wie finde ich das richtige Passwort für eine PDF-Datei?

A: Nachdem Sie festgestellt haben, dass die PDF-Datei verschlüsselt ist, können Sie versuchen, das richtige Passwort mithilfe einer vordefinierten Liste von Passwörtern zu finden. Der bereitgestellte Beispielcode zeigt, wie Sie die Liste durchlaufen, jedes Kennwort ausprobieren und feststellen, ob das Kennwort korrekt ist.

#### F: Was passiert, wenn das richtige Passwort gefunden wird?

A: Wenn das richtige Passwort gefunden wird, zeigt der Beispielcode die Anzahl der Seiten im PDF-Dokument an.

#### F: Was passiert, wenn das Passwort nicht korrekt ist?

 A: Wenn das Passwort nicht korrekt ist, wird der Beispielcode dies abfangen`InvalidPasswordException` und zeigen Sie eine Meldung an, dass das Passwort nicht korrekt ist.

#### F: Kann ich eine andere Liste von Passwörtern verwenden?

 A: Ja, Sie können das ändern`passwords` Array im Beispielcode, um die Passwörter einzuschließen, die Sie testen möchten.

#### F: Woher weiß ich, dass das Passwort erfolgreich ermittelt wurde?

A: Wenn der Beispielcode das PDF-Dokument erfolgreich mit einem Passwort lädt und die Anzahl der Seiten anzeigt, bedeutet dies, dass das richtige Passwort ermittelt wurde.

#### F: Wie kann ich beim Testen die Sicherheit meiner Passwörter gewährleisten?

A: Seien Sie vorsichtig, wenn Sie eine vordefinierte Liste von Passwörtern verwenden, und vermeiden Sie die Verwendung sensibler oder vertraulicher Passwörter zu Testzwecken. Entfernen oder ändern Sie außerdem den Testcode, bevor Sie Ihre Anwendung bereitstellen.