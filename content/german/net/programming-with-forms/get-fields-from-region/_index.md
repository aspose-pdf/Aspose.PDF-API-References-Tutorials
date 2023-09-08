---
title: Holen Sie sich Felder aus der Region in eine PDF-Datei
linktitle: Holen Sie sich Felder aus der Region in eine PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Mit Aspose.PDF für .NET können Sie ganz einfach Felder aus einer bestimmten Region in einer PDF-Datei abrufen.
type: docs
weight: 130
url: /de/net/programming-with-forms/get-fields-from-region/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET die Felder einer bestimmten Region in einer PDF-Datei abrufen. Wir erklären Ihnen Schritt für Schritt den C#-Quellcode, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie sicher, dass Sie die erforderlichen Bibliotheken importiert und den Pfad zu Ihrem Dokumentenverzeichnis festgelegt haben:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Öffnen Sie die PDF-Datei

Öffnen Sie die PDF-Datei:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## Schritt 3: Erstellen Sie ein rechteckiges Objekt, um den Bereich zu begrenzen

Erstellen Sie ein rechteckiges Objekt, um den Bereich zu begrenzen, in dem Sie die Felder erhalten möchten:

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## Schritt 4: Besorgen Sie sich das PDF-Formular

Holen Sie sich das PDF-Formular des Dokuments:

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## Schritt 5: Holen Sie sich die Felder im rechteckigen Bereich

Rufen Sie die Felder ab, die sich im angegebenen rechteckigen Bereich befinden:

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## Schritt 6: Feldnamen und Werte anzeigen

Durchlaufen Sie die resultierenden Felder und zeigen Sie deren Namen und Werte an:

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### Beispielquellcode für „Felder aus Region abrufen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// PDF-Datei öffnen
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// Erstellen Sie ein rechteckiges Objekt, um Felder in diesem Bereich abzurufen
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// Holen Sie sich das PDF-Formular
Aspose.Pdf.Forms.Form form = doc.Form;
// Holen Sie sich Felder im rechteckigen Bereich
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// Feldnamen und -werte anzeigen
foreach (Field field in fields)
{
	// Bildplatzierungseigenschaften für alle Platzierungen anzeigen
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET die Felder einer bestimmten Region in einem PDF-Dokument abruft. Wenn Sie diese Schritte befolgen, können Sie mit Aspose.PDF ganz einfach die Felder extrahieren, die sich in einem bestimmten rechteckigen Bereich Ihres PDF-Dokuments befinden.

### FAQs

#### F: Kann ich diese Methode verwenden, um Felder aus einem nicht rechteckigen Bereich in einem PDF-Dokument abzurufen?

 A: Nein, die bereitgestellte Methode`GetFieldsInRect` wurde speziell zum Abrufen von Feldern entwickelt, die sich innerhalb eines rechteckigen Bereichs in einem PDF-Dokument befinden. Wenn Sie Felder aus einem nicht rechteckigen Bereich extrahieren müssen, müssen Sie eine benutzerdefinierte Logik implementieren, um die Felder anhand anderer Kriterien wie Feldkoordinaten oder Namen zu identifizieren und zu extrahieren.

#### F: Wie kann ich die Größe oder Position des Rechtecks ändern, um Felder aus einer anderen Region zu erhalten?

 A: Um Felder aus einer anderen Region zu erhalten, können Sie diese ändern`Aspose.Pdf.Rectangle` Die Parameter des Objekts, die zum Definieren des umgrenzenden Rechtecks verwendet werden. Der`Rectangle` Der Konstruktor benötigt vier Parameter:`x`, `y`, `width` , Und`height`die die Koordinaten der oberen linken Ecke und die Abmessungen des Rechtecks darstellen. Durch Anpassen dieser Parameter wird die Region geändert, aus der Felder extrahiert werden.

#### F: Was passiert, wenn innerhalb des angegebenen rechteckigen Bereichs keine Felder vorhanden sind?

 A: Wenn innerhalb des angegebenen rechteckigen Bereichs keine Felder vorhanden sind, wird die`GetFieldsInRect` Die Methode gibt ein leeres Array zurück. Sie können die Länge des Arrays überprüfen, um festzustellen, ob innerhalb der Region Felder vorhanden sind.

#### F: Kann ich Felder aus überlappenden Bereichen in einem PDF-Dokument abrufen?

 A: Ja, Sie können Felder aus überlappenden Bereichen in einem PDF-Dokument erhalten, indem Sie mehrere erstellen`Aspose.Pdf.Rectangle` Objekte und Aufruf der`GetFieldsInRect` Methode für jeden von ihnen. Überlappende Regionen werden unabhängig voneinander behandelt und Sie erhalten für jede Region separate Feldarrays.

#### F: Ist es möglich, Felder von einer bestimmten Seite oder mehreren Seiten im PDF-Dokument abzurufen?

A: Ja, Sie können Felder von einer bestimmten Seite oder mehreren Seiten in einem PDF-Dokument abrufen. Um dies zu erreichen, können Sie das PDF-Dokument laden und über das auf die gewünschten Seiten zugreifen`doc.Pages` Sammlung, und wenden Sie dann die an`GetFieldsInRect` -Methode auf den spezifischen Bereich jeder Seite anwenden.