---
title: Wert aus Feld im PDF-Dokument abrufen
linktitle: Wert aus Feld im PDF-Dokument abrufen
second_title: Aspose.PDF für .NET API-Referenz
description: Mit Aspose.PDF für .NET können Sie ganz einfach den Wert eines Formularfelds in einem PDF-Dokument ermitteln.
type: docs
weight: 140
url: /de/net/programming-with-forms/get-value-from-field/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET den Wert eines Formularfelds ermitteln. Wir erklären Ihnen Schritt für Schritt den C#-Quellcode, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie sicher, dass Sie die erforderlichen Bibliotheken importiert und den Pfad zu Ihrem Dokumentenverzeichnis festgelegt haben:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Öffnen Sie das Dokument

Öffnen Sie das PDF-Dokument:

```csharp
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
```

## Schritt 3: Feld abrufen

Rufen Sie das gewünschte Formularfeld ab (in diesem Beispiel verwenden wir das Feld „textbox1“):

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Schritt 4: Feldwert abrufen

 Rufen Sie den Feldwert mithilfe von ab`Value` Eigentum:

```csharp
Console.WriteLine("PartialName: {0}", textBoxField.PartialName);
Console.WriteLine("Value: {0}", textBoxField.Value);
```

### Beispielquellcode für „Get Value From Field“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
// Holen Sie sich ein Feld
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Feldwert abrufen
Console.WriteLine("PartialName : {0} ", textBoxField.PartialName);
Console.WriteLine("Value : {0} ", textBoxField.Value);
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET den Wert eines Formularfelds ermittelt. Wenn Sie diese Schritte befolgen, können Sie mit Aspose.PDF ganz einfach den Wert eines bestimmten Formularfelds in Ihren PDF-Dokumenten extrahieren.

### FAQs

#### F: Kann ich den Wert eines Formularfelds ermitteln, ohne dessen Namen vorher zu kennen?

 A: Nein, Sie müssen den Namen oder Teilnamen des Formularfelds kennen, um seinen Wert mit Aspose.PDF für .NET zu erhalten. Der`pdfDocument.Form["fieldname"]` Die Syntax erfordert den genauen Namen oder Teilnamen des Formularfelds, um auf dessen Eigenschaften, einschließlich des Werts, zuzugreifen.

#### F: Was passiert, wenn das Formularfeld im PDF-Dokument nicht vorhanden ist?

 A: Wenn das Formularfeld im PDF-Dokument nicht vorhanden ist, wird das`pdfDocument.Form["fieldname"]` Die Syntax wird zurückgegeben`null` . Es ist wichtig, solche Fälle durch eine Überprüfung zu behandeln`null` bevor Sie auf die Eigenschaften des Formularfelds zugreifen, um Ausnahmen zu vermeiden.

#### F: Wie kann ich mit verschiedenen Arten von Formularfeldern (z. B. Kontrollkästchen, Optionsfeldern) umgehen, um deren Werte zu erhalten?

 A: Um verschiedene Arten von Formularfeldern zu verarbeiten, können Sie die entsprechenden Feldklassen verwenden, die in Aspose.PDF für .NET verfügbar sind. Verwenden Sie zum Beispiel`CheckBoxField` mit Kontrollkästchen arbeiten und`RadioButtonField`um mit Optionsfeldern zu arbeiten. Sobald Sie das richtige Feldobjekt haben, können Sie auf dessen Eigenschaften, einschließlich des Werts, zugreifen.

#### F: Kann ich die Werte mehrerer Formularfelder gleichzeitig abrufen?

A: Ja, Sie können die Werte mehrerer Formularfelder gleichzeitig abrufen, indem Sie die Formularfeldsammlung mithilfe einer Schleife oder LINQ-Abfragen durchlaufen. Auf diese Weise können Sie programmgesteuert auf den Wert jedes Formularfelds im PDF-Dokument zugreifen.

#### F: Ist es möglich, den Wert eines Formularfelds zu ändern und die Änderungen wieder im PDF-Dokument zu speichern?

 A: Ja, Sie können den Wert eines Formularfelds mit Aspose.PDF für .NET ändern und die Änderungen wieder im PDF-Dokument speichern. Nach der Aktualisierung der`Value` Eigenschaft des Formularfelds können Sie die verwenden`pdfDocument.Save()` Methode zum Speichern der Änderungen am ursprünglichen PDF-Dokument.