---
title: Kennwort ändern
linktitle: Kennwort ändern
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie das Passwort eines PDF-Dokuments mit Aspose.PDF für .NET ändern.
type: docs
weight: 10
url: /de/net/programming-with-security-and-signatures/change-password/
---

In diesem Tutorial führen wir Sie durch den Prozess der Änderung des Passworts eines PDF-Dokuments mit Aspose.PDF für .NET. Mit der Bibliothek können Sie eine vorhandene PDF-Datei öffnen, ihr Passwort ändern und die aktualisierte Version speichern. Diese Funktion ist praktisch, wenn Sie Ihre PDF-Dokumente durch Ändern des Passworts schützen müssen.

## Schritt 1: Anforderungen

Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Grundkenntnisse der Programmiersprache C#
- Visual Studio ist auf Ihrem Computer installiert
- Aspose.PDF für .NET-Bibliothek installiert

## Schritt 2: Einrichten der Umgebung

Führen Sie zunächst die folgenden Schritte aus, um Ihre Entwicklungsumgebung einzurichten:

1. Öffnen Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Installieren Sie die Aspose.PDF für .NET-Bibliothek mit NuGet Package Manager.
3. Importieren Sie die erforderlichen Namespaces in Ihre Codedatei:

```csharp
using Aspose.Pdf;
```

## Schritt 3: Laden des PDF-Dokuments

Der erste Schritt besteht darin, das PDF-Dokument zu laden, für das Sie das Passwort ändern möchten. In diesem Beispiel gehen wir davon aus, dass Sie im angegebenen Verzeichnis eine PDF-Datei mit dem Namen „ChangePassword.pdf“ haben.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document document = new Document(dataDir + "ChangePassword.pdf", "owner");
```

## Schritt 4: Passwort ändern

 Sobald Sie das PDF-Dokument geladen haben, können Sie dessen Passwort mit ändern`ChangePasswords`Methode. Die Methode erfordert drei Parameter: das aktuelle Besitzerpasswort, das neue Benutzerpasswort und das neue Besitzerpasswort.

```csharp
document.ChangePasswords("owner", "newuser", "newowner");
```

Stellen Sie sicher, dass Sie die Platzhalter durch die tatsächlichen Passwörter ersetzen, die Sie festlegen möchten.

## Schritt 5: Speichern der aktualisierten PDF-Datei

 Nachdem Sie das Passwort geändert haben, müssen Sie das aktualisierte PDF-Dokument speichern. Geben Sie den Pfad der Ausgabedatei an und verwenden Sie die`Save` Methode zum Speichern des Dokuments.

```csharp
dataDir = dataDir + "ChangePassword_out.pdf";
document. Save(dataDir);
Console.WriteLine("\nPDF file password changed successfully.\nFile saved at " + dataDir);
```

Das aktualisierte PDF wird am angegebenen Speicherort gespeichert.

### Beispielquellcode für „Passwort ändern“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Dokument öffnen
Document document = new Document(dataDir+ "ChangePassword.pdf", "owner");
// Kennwort ändern
document.ChangePasswords("owner", "newuser", "newowner");
dataDir = dataDir + "ChangePassword_out.pdf";
// Aktualisiertes PDF speichern
document.Save(dataDir);
Console.WriteLine("\nPDF file password changed successfully.\nFile saved at " + dataDir);
```

## Abschluss

Glückwunsch! Sie haben das Passwort eines PDF-Dokuments mit Aspose.PDF für .NET erfolgreich geändert. Dieses Tutorial behandelt den schrittweisen Prozess vom Laden des Dokuments bis zum Speichern der aktualisierten Version. Sie können diese Funktion jetzt nutzen, um Ihre PDF-Dateien mit neuen Passwörtern zu sichern.