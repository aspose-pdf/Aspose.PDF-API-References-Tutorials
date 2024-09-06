---
title: Rechte wahren
linktitle: Rechte wahren
second_title: Aspose.PDF für .NET API-Referenz
description: Bewahren Sie mit Aspose.PDF für .NET die Formularrechte in Ihren PDF-Dokumenten.
type: docs
weight: 210
url: /de/net/programming-with-forms/preserve-rights/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET Formularrechte in einem PDF-Dokument beibehalten. Wir erklären Ihnen den C#-Quellcode Schritt für Schritt, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie sicher, dass Sie die erforderlichen Bibliotheken importiert haben, und legen Sie den Pfad zu Ihrem Dokumentverzeichnis fest:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Öffnen Sie das Dokument

 Öffnen Sie das PDF-Quelldokument mit einem`FileStream` mit Lese- und Schreibberechtigung:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Schritt 3: Formularfelder bearbeiten

Gehen Sie alle Formularfelder im Dokument durch und nehmen Sie die erforderlichen Änderungen vor. In diesem Beispiel ändern wir den Wert eines Formularfelds, dessen Name „A1“ enthält:

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

## Schritt 4: Speichern Sie das aktualisierte Dokument

Speichern Sie das geänderte PDF-Dokument:

```csharp
pdfDocument.Save();
```

##  Schritt 5: Schließen Sie die`FileStream`

 Vergessen Sie nicht, die`FileStream` Objekt, wenn Sie fertig sind:

```csharp
fs. Close();
```

### Beispielquellcode für „Preserve Rights“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Lesen Sie das Quell-PDF-Formular mit den Dateizugriffsrechten „Lesen“ und „Schreiben“.
// Wir benötigen die Lese-/Schreibberechtigung, da nach der Änderung
// Wir müssen den aktualisierten Inhalt im selben Dokument/derselben Datei speichern.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// Dokumentinstanz instantiieren
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Werte aus allen Feldern abrufen
foreach (Field formField in pdfDocument.Form)
{
	// Wenn der vollständige Name des Felds A1 enthält, führen Sie den Vorgang aus
	if (formField.FullName.Contains("A1"))
	{
		// Formularfeld als TextBox umwandeln
		TextBoxField textBoxField = formField as TextBoxField;
		// Feldwert ändern
		textBoxField.Value = "Testing";
	}
}
// Speichern Sie das aktualisierte Dokument im FileStream
pdfDocument.Save();
// Schließen Sie das File Stream-Objekt
fs.Close();
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie Sie mit Aspose.PDF für .NET die Rechte eines Formulars in einem PDF-Dokument bewahren. Indem Sie diese Schritte befolgen, können Sie problemlos auf Formularfelder zugreifen und bestimmte Änderungen vornehmen, während Zugriffs- und Schreibberechtigungen erhalten bleiben.


### Häufig gestellte Fragen

#### F: Kann ich die Rechte bestimmter Formularfelder beibehalten, ohne andere im PDF-Dokument zu beeinträchtigen?

 A: Ja, mit dem`FullName` der Formularfelder können Sie bestimmte Formularfelder zur Beibehaltung auswählen und andere unverändert lassen.

#### F: Kann ich die Rechte eines Formulars in einem passwortgeschützten PDF-Dokument bewahren?

A: Ja, mit Aspose.PDF für .NET können Sie die Rechte eines Formulars auch in passwortgeschützten PDF-Dokumenten wahren, solange Sie für den Zugriff auf die Datei und deren Änderung das richtige Passwort angeben.

#### F: Was passiert, wenn ich versuche, Formularfelder zu ändern, ohne über die entsprechenden Zugriffsrechte zu verfügen?

A: Wenn Sie versuchen, Formularfelder ohne die entsprechenden Zugriffsrechte zu ändern, werden die Änderungen nicht im PDF-Dokument gespeichert und Sie erhalten möglicherweise eine Ausnahme oder eine Fehlermeldung.

#### F: Ist Aspose.PDF für .NET mit allen Versionen von .NET Framework kompatibel?

A: Ja, Aspose.PDF für .NET ist mit allen Versionen von .NET Framework kompatibel, einschließlich .NET Core und .NET Standard.

#### F: Kann ich Formularrechte in einem PDF-Dokument programmgesteuert in anderen Programmiersprachen als C# beibehalten?

A: Ja, Aspose.PDF für .NET unterstützt neben C# verschiedene Programmiersprachen wie VB.NET und ASP.NET.