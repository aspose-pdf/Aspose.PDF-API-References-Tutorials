---
title: Werte aus allen Feldern im PDF-Dokument abrufen
linktitle: Werte aus allen Feldern im PDF-Dokument abrufen
second_title: Aspose.PDF für .NET API-Referenz
description: Mit Aspose.PDF für .NET erhalten Sie ganz einfach die Werte aller Formularfelder im PDF-Dokument.
type: docs
weight: 150
url: /de/net/programming-with-forms/get-values-from-all-fields/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET die Werte aller Formularfelder in einem PDF-Dokument abrufen. Wir erklären Ihnen den C#-Quellcode Schritt für Schritt, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie sicher, dass Sie die erforderlichen Bibliotheken importiert haben, und legen Sie den Pfad zu Ihrem Dokumentverzeichnis fest:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Öffnen Sie das Dokument

Öffnen Sie das PDF-Dokument:

```csharp
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
```

## Schritt 3: Werte für alle Felder abrufen

Durchlaufen Sie alle Formularfelder im Dokument und rufen Sie deren Namen und Werte ab:

```csharp
foreach(Field formField in pdfDocument.Form)
{
Console.WriteLine("Field name: {0} ", formField.PartialName);
Console.WriteLine("Value: {0}", formField.Value);
}
```

### Beispielquellcode zum Abrufen von Werten aus allen Feldern mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
// Werte aus allen Feldern abrufen
foreach (Field formField in pdfDocument.Form)
{
	Console.WriteLine("Field Name : {0} ", formField.PartialName);
	Console.WriteLine("Value : {0} ", formField.Value);
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET die Werte aller Formularfelder in einem PDF-Dokument abruft. Indem Sie diese Schritte befolgen, können Sie mit Aspose.PDF ganz einfach die Werte aller Formularfelder aus Ihren PDF-Dokumenten extrahieren.

### Häufig gestellte Fragen

#### F: Kann ich die Werte von Formularfeldern ändern, während ich sie mit Aspose.PDF für .NET abrufe?

 A: Ja, Sie können die Werte von Formularfeldern ändern, während Sie sie mit Aspose.PDF für .NET abrufen. Sobald Sie die`Field` -Objekt, das ein Formularfeld darstellt, können Sie dessen`Value`Eigenschaft durch den gewünschten Wert. Nachdem Sie die erforderlichen Änderungen vorgenommen haben, können Sie das aktualisierte PDF-Dokument speichern, um die Änderungen widerzuspiegeln.

#### F: Wie kann ich bestimmte Formularfelder basierend auf ihrem Typ (z. B. Textfelder, Kontrollkästchen) filtern und abrufen?

 A: Um bestimmte Formularfelder basierend auf ihrem Typ abzurufen, können Sie bedingte Anweisungen oder LINQ-Abfragen verwenden, um die relevanten Felder zu filtern. Sie können den Typ jedes Formularfelds anhand der`FieldType` -Eigenschaft und rufen Sie dann die Werte entsprechend ab.

#### F: Was passiert, wenn das PDF-Dokument keine Formularfelder hat?

 A: Wenn das PDF-Dokument keine Formularfelder enthält,`pdfDocument.Form` -Eigenschaft gibt eine leere Sammlung zurück. In solchen Fällen wird die Schleife zum Abrufen der Werte nicht ausgeführt und es werden keine Werte angezeigt.

#### F: Kann ich die Formularfeldwerte in einer bestimmten Reihenfolge extrahieren oder alphabetisch sortieren?

A: Die Reihenfolge, in der die Formularfelder abgerufen werden, hängt von der zugrunde liegenden Struktur des PDF-Dokuments ab. Aspose.PDF für .NET gibt die Formularfelder in der Reihenfolge zurück, in der sie dem Dokument hinzugefügt wurden. Wenn Sie die Formularfelder in einer bestimmten Reihenfolge anzeigen oder verarbeiten möchten, können Sie eine benutzerdefinierte Sortierlogik basierend auf Ihren Anforderungen implementieren.

#### F: Wie kann ich mit verschlüsselten PDF-Dokumenten mit passwortgeschützten Formularfeldern umgehen?

 A: Aspose.PDF für .NET bietet Funktionen zum Arbeiten mit verschlüsselten PDF-Dokumenten und passwortgeschützten Formularfeldern. Vor dem Laden des Dokuments können Sie das Passwort mithilfe des`pdfDocument.Password` -Eigenschaft, um auf das gesicherte PDF-Dokument und seine Formularfelder zuzugreifen.