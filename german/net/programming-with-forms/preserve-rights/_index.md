---
title: Rechte bewahren
linktitle: Rechte bewahren
second_title: Aspose.PDF für .NET API-Referenz
description: Behalten Sie Formularrechte in Ihren PDF-Dokumenten mit Aspose.PDF für .NET.
type: docs
weight: 210
url: /de/net/programming-with-forms/preserve-rights/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET Formularrechte in einem PDF-Dokument bewahren. Wir erklären Ihnen Schritt für Schritt den C#-Quellcode, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie sicher, dass Sie die erforderlichen Bibliotheken importiert und den Pfad zu Ihrem Dokumentenverzeichnis festgelegt haben:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Öffnen Sie das Dokument

 Öffnen Sie das PDF-Quelldokument mit a`FileStream` mit Lese- und Schreibberechtigung:

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

##  Schritt 5: Schließen Sie das`FileStream`

 Vergessen Sie nicht, das zu schließen`FileStream` Objekt, wenn Sie fertig sind:

```csharp
fs. Close();
```

### Beispielquellcode für Preserve Rights mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Lesen Sie das Quell-PDF-Formular mit FileAccess oder Read and Write.
// Wir benötigen die ReadWrite-Berechtigung, da nach der Änderung
// Wir müssen die aktualisierten Inhalte im selben Dokument/in derselben Datei speichern.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// Dokumentinstanz instanziieren
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Holen Sie sich Werte aus allen Feldern
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
// Speichern Sie das aktualisierte Dokument in Save FileStream
pdfDocument.Save();
// Schließen Sie das File Stream-Objekt
fs.Close();
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET die Rechte eines Formulars in einem PDF-Dokument beibehält. Wenn Sie diese Schritte befolgen, können Sie problemlos auf Formularfelder zugreifen und spezifische Änderungen vornehmen, während Sie gleichzeitig Zugriffs- und Schreibberechtigungen behalten.


### FAQs

#### F: Kann ich die Rechte bestimmter Formularfelder beibehalten, ohne dass sich dies auf andere im PDF-Dokument auswirkt?

 A: Ja, indem Sie das verwenden`FullName` Eigenschaft der Formularfelder können Sie bestimmte Formularfelder gezielt beibehalten, während andere davon unberührt bleiben.

#### F: Kann ich die Rechte eines Formulars in einem passwortgeschützten PDF-Dokument beibehalten?

A: Ja, mit Aspose.PDF für .NET können Sie die Rechte eines Formulars auch in passwortgeschützten PDF-Dokumenten bewahren, solange Sie das richtige Passwort angeben, um auf die Datei zuzugreifen und sie zu ändern.

#### F: Was passiert, wenn ich versuche, Formularfelder ohne die entsprechenden Zugriffsrechte zu ändern?

A: Wenn Sie versuchen, Formularfelder ohne die entsprechenden Zugriffsrechte zu ändern, werden die Änderungen nicht im PDF-Dokument gespeichert und Sie erhalten möglicherweise eine Ausnahme oder eine Fehlermeldung.

#### F: Ist Aspose.PDF für .NET mit allen Versionen von .NET Framework kompatibel?

A: Ja, Aspose.PDF für .NET ist mit allen Versionen von .NET Framework kompatibel, einschließlich .NET Core und .NET Standard.

#### F: Kann ich Formularrechte in einem PDF-Dokument programmgesteuert in anderen Programmiersprachen als C# beibehalten?

A: Ja, Aspose.PDF für .NET unterstützt neben C# auch verschiedene Programmiersprachen wie VB.NET und ASP.NET.