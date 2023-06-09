---
title: Ist passwortgeschützt
linktitle: Ist passwortgeschützt
second_title: Aspose.PDF für .NET API-Referenz
description: Überprüfen Sie ganz einfach, ob ein PDF-Dokument mit Aspose.PDF für .NET passwortgeschützt ist.
type: docs
weight: 90
url: /de/net/programming-with-security-and-signatures/is-password-protected/
---

Oft ist es wichtig zu wissen, ob ein PDF-Dokument vor der Verarbeitung passwortgeschützt ist. Mit Aspose.PDF für .NET können Sie mithilfe des folgenden Quellcodes ganz einfach überprüfen, ob ein PDF-Dokument geschützt ist:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier sind die notwendigen Importanweisungen:

```csharp
using Aspose.Pdf;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

 In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, der die PDF-Datei enthält, die Sie überprüfen möchten. Ersetzen`"YOUR DOCUMENTS DIRECTORY"` Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 3: Laden Sie das PDF-Quelldokument

Jetzt laden wir das Quell-PDF-Dokument und prüfen mit dem folgenden Code, ob es passwortgeschützt ist:

```csharp
PdfFileInfo fileInfo = new PdfFileInfo(dataDir + @"IsPasswordProtected.pdf");
```

## Schritt 4: Überprüfen Sie, ob das PDF geschützt ist

 In diesem Schritt ermitteln wir mithilfe des Passworts, ob das PDF-Dokument passwortgeschützt ist`IsEncrypted` Methode der`PdfFileInfo` Objekt. Hier ist der entsprechende Code:

```csharp
bool encrypted = fileInfo.IsEncrypted;
```

## Schritt 5: Verschlüsselungsstatus anzeigen

 Abschließend können wir mit dem den aktuellen Verschlüsselungsstatus des PDFs anzeigen`Console.WriteLine` Methode. Hier ist der entsprechende Code:

```csharp
Console.WriteLine(encrypted.ToString());
```

Die angezeigte Meldung gibt an, ob das PDF-Dokument passwortgeschützt ist oder nicht.

### Beispielquellcode für „Ist passwortgeschützt“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Laden Sie das Quell-PDF-Dokument
PdfFileInfo fileInfo = new PdfFileInfo(dataDir+ @"IsPasswordProtected.pdf");
//Stellen Sie fest, dass die Quell-PDF-Datei mit einem Passwort verschlüsselt ist
bool encrypted = fileInfo.IsEncrypted;
// MessageBox zeigt den aktuellen Status zur PDF-Verschlüsselung an
Console.WriteLine(encrypted.ToString());
```

## Abschluss

Herzlichen Glückwunsch! Jetzt haben Sie eine Schritt-für-Schritt-Anleitung, um mit Aspose.PDF für .NET zu überprüfen, ob ein PDF-Dokument passwortgeschützt ist. Sie können diesen Code in Ihre eigenen Projekte integrieren, um je nach Schutzstatus des PDFs bestimmte Vorgänge auszuführen.

Weitere Informationen zu erweiterten PDF-Dokumentsicherheits- und Passwortverwaltungsfunktionen finden Sie unbedingt in der offiziellen Aspose.PDF-Dokumentation.