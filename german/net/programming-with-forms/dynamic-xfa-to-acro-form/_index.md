---
title: Dynamisches XFA-zu-Acro-Formular
linktitle: Dynamisches XFA-zu-Acro-Formular
second_title: Aspose.PDF für .NET API-Referenz
description: Konvertieren Sie dynamische XFA-Formulare ganz einfach in Standard-AcroForm-Formulare mit Aspose.PDF für .NET.
type: docs
weight: 70
url: /de/net/programming-with-forms/dynamic-xfa-to-acro-form/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET ein dynamisches XFA-Formular in ein AcroForm konvertieren. Wir erklären Ihnen Schritt für Schritt den C#-Quellcode, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie zunächst sicher, dass Sie die erforderlichen Bibliotheken importiert haben und legen Sie den Pfad zum Dokumentenverzeichnis fest:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das dynamische XFA-Formular

Laden Sie das dynamische XFA-Formular:

```csharp
Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
```

## Schritt 3: Legen Sie den Formulartyp als Standard-AcroForm fest

Legen Sie den Formulartyp als Standard-AcroForm fest:

```csharp
document.Form.Type = FormType.Standard;
```

## Schritt 4: Speichern Sie das resultierende PDF

Speichern Sie das resultierende PDF:

```csharp
dataDir = dataDir + "Standard_AcroForm_out.pdf";
document. Save(dataDir);
```

### Beispielquellcode für Dynamic XFA To Acro Form mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Laden Sie ein dynamisches XFA-Formular
Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
// Legen Sie den Formularfeldtyp als Standard-AcroForm fest
document.Form.Type = FormType.Standard;
dataDir = dataDir + "Standard_AcroForm_out.pdf";
// Speichern Sie das resultierende PDF
document.Save(dataDir);
Console.WriteLine("\nDynamic XFA form converted to standard AcroForm successfully.\nFile saved at " + dataDir);
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET ein dynamisches XFA-Formular in ein Standard-AcroForm-Formular umwandelt. Wenn Sie diese Schritte befolgen, können Sie Ihre dynamischen XFATo-Formulare für eine häufigere Verwendung ganz einfach in AcroForms konvertieren.