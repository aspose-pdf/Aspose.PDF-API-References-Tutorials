---
title: Arabische Textfüllung
linktitle: Arabische Textfüllung
second_title: Aspose.PDF für .NET API-Referenz
description: Füllen Sie PDF-Formularfelder ganz einfach mit arabischem Text mit Aspose.PDF für .NET.
type: docs
weight: 20
url: /de/net/programming-with-forms/arabic-text-filling/
---

In diesem Tutorial lernen wir, wie man mit Aspose.PDF für .NET ein PDF-Formularfeld mit arabischem Text füllt. Aspose.PDF ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, PDF-Dokumente programmgesteuert zu bearbeiten. Wir führen Sie Schritt für Schritt durch den Prozess und erklären den C#-Quellcode, der zum Ausführen dieser Aufgabe erforderlich ist.

## Schritt 1: PDF-Formularinhalt laden

Zuerst müssen wir das PDF-Formular laden, das das auszufüllende Feld enthält. Wir beginnen mit der Definition des Pfads zu dem Verzeichnis, in dem sich das Formular befindet:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Als nächstes erstellen wir eine`FileStream` Objekt zum Lesen und Schreiben der Formulardatei:

```csharp
FileStream fs = new FileStream(dataDir + "FillFormField.pdf", FileMode.Open, FileAccess.ReadWrite);
```

 Als nächstes instanziieren wir a`Document` Objekt mithilfe des Streams, der die Formulardatei enthält:

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Schritt 2: Greifen Sie auf das TextBoxField-Feld zu

 Um das Formularfeld mit arabischem Text zu füllen, müssen wir auf den spezifischen Text zugreifen`TextBoxField` Feld, das wir ausfüllen möchten. In diesem Beispiel gehen wir davon aus, dass der Feldname „textbox1“ ist. Wir können die Feldreferenz mithilfe von abrufen`Form` Eigentum der`pdfDocument` Objekt:

```csharp
TextBoxField txtFld = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Schritt 3: Füllen Sie das Formularfeld mit arabischem Text

 Jetzt, wo wir das haben`TextBoxField` Referenz können wir ihm den arabischen Text zuordnen`Value` Eigentum:

```csharp
txtFld.Value = "يولد جميع الناس أحراراً متساوين في";
```

## Schritt 4: Speichern Sie das aktualisierte Dokument

Abschließend speichern wir das aktualisierte Dokument in einer neuen Datei:

```csharp
dataDir = dataDir + "ArabicTextFilling_out.pdf";
pdfDocument.Save(dataDir);
```

Wir zeigen außerdem eine Meldung an, die den Erfolg des Ausfüllens des arabischen Textes anzeigt:

```csharp
Console.WriteLine("\nArabic text successfully filled in the form field.\nFile saved in the following location: " + dataDir);
```

### Beispielquellcode für die arabische Textfüllung mit Aspose.Words für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Laden Sie den Inhalt des PDF-Formulars
FileStream fs = new FileStream(dataDir + "FillFormField.pdf", FileMode.Open, FileAccess.ReadWrite);
//Instanziieren Sie eine Dokumentinstanz mit einem Stream, der die Formulardatei enthält
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Erhalten Sie eine Referenz zu einem bestimmten TextBoxField
TextBoxField txtFld = pdfDocument.Form["textbox1"] as TextBoxField;
// Füllen Sie das Formularfeld mit arabischem Text aus
txtFld.Value = "يولد جميع الناس أحراراً متساوين في";
dataDir = dataDir + "ArabicTextFilling_out.pdf";
// Aktualisiertes Dokument speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nArabic text filled successfully in form field.\nFile saved at " + dataDir);
```

## Abschluss

In diesem Tutorial haben wir untersucht, wie man mit Aspose.PDF für .NET ein PDF-Formularfeld mit arabischem Text füllt. Wir gingen den Prozess Schritt für Schritt durch und erklärten den relevanten C#-Quellcode. Wenn Sie diese Anweisungen befolgen, können Sie arabische Textfüllfunktionen problemlos in Ihre .NET-Anwendungen integrieren. Wenn Sie weitere Fragen haben oder weitere Informationen benötigen, wenden Sie sich gerne an das Aspose.PDF-Supportteam oder schauen Sie sich die zusätzlichen Ressourcen unten an.