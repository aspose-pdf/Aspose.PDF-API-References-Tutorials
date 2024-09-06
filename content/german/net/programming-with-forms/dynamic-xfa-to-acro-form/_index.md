---
title: Dynamisches XFA zu Acro-Formular
linktitle: Dynamisches XFA zu Acro-Formular
second_title: Aspose.PDF für .NET API-Referenz
description: Konvertieren Sie dynamische XFA-Formulare ganz einfach in standardmäßige AcroForm-Formulare mit Aspose.PDF für .NET.
type: docs
weight: 70
url: /de/net/programming-with-forms/dynamic-xfa-to-acro-form/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET ein dynamisches XFA-Formular in ein AcroForm konvertieren. Wir erklären Ihnen den C#-Quellcode Schritt für Schritt, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie zunächst sicher, dass Sie die erforderlichen Bibliotheken importiert haben, und legen Sie den Pfad zum Dokumentverzeichnis fest:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das dynamische XFA-Formular

Laden Sie das dynamische XFA-Formular:

```csharp
Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
```

## Schritt 3: Formulartyp als Standard-AcroForm festlegen

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
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dynamisches XFA-Formular laden
Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
// Legen Sie den Formularfeldtyp als Standard-AcroForm fest
document.Form.Type = FormType.Standard;
dataDir = dataDir + "Standard_AcroForm_out.pdf";
// Speichern Sie das resultierende PDF
document.Save(dataDir);
Console.WriteLine("\nDynamic XFA form converted to standard AcroForm successfully.\nFile saved at " + dataDir);
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET ein dynamisches XFA-Formular in ein standardmäßiges AcroForm-Formular konvertiert. Indem Sie diese Schritte befolgen, können Sie Ihre dynamischen XFATo-Formulare ganz einfach in AcroForms konvertieren, um sie häufiger zu verwenden.

### Häufig gestellte Fragen

#### F: Was ist der Unterschied zwischen einem dynamischen XFA-Formular und einem Standard-AcroForm?

A: Ein dynamisches XFA-Formular (XML Forms Architecture) ist ein PDF-Formulartyp, der XML-basierte Daten verwendet, um sein Layout und Verhalten zu definieren. XFA-Formulare werden häufig in interaktiven und datenintensiven Formularen verwendet. Ein Standard-AcroForm hingegen ist ein traditionellerer PDF-Formulartyp, der das PDF-Format selbst verwendet, um seine Struktur und sein Erscheinungsbild zu definieren. AcroForms werden von PDF-Viewern weitgehend unterstützt und können mit verschiedenen Anwendungen kompatibler sein.

#### F: Warum sollte ich ein dynamisches XFA-Formular in ein Standard-AcroForm konvertieren?

A: Die Konvertierung eines dynamischen XFA-Formulars in ein Standard-AcroForm kann in Szenarien nützlich sein, in denen XFA-Formulare nicht vollständig unterstützt werden oder wenn Sie eine größere Kompatibilität mit verschiedenen PDF-Viewern und -Anwendungen erreichen möchten. Standard-AcroForms werden im Allgemeinen plattform- und geräteübergreifend besser unterstützt.

#### F: Kann ich die Formularfelder ändern, nachdem ich ein dynamisches XFA-Formular in ein Standard-AcroForm konvertiert habe?

A: Ja, nachdem Sie ein dynamisches XFA-Formular in ein Standard-AcroForm konvertiert haben, können Sie die Formularfelder mit Aspose.PDF für .NET nach Bedarf ändern. Sie können neue Felder hinzufügen, ihre Eigenschaften ändern, Feldwerte festlegen und andere formularbezogene Vorgänge ausführen.

#### F: Gibt es irgendwelche Einschränkungen oder Überlegungen bei der Konvertierung dynamischer XFA-Formulare in standardmäßige AcroForms?

A: Ja, beim Konvertieren dynamischer XFA-Formulare in standardmäßige AcroForms müssen einige Einschränkungen berücksichtigt werden. XFA-Formulare können komplexe und dynamische Layouts aufweisen, einschließlich Funktionen wie dynamische Tabellen, sich wiederholende Abschnitte und Formularberechnungen, die beim Konvertierungsprozess möglicherweise nicht vollständig erhalten bleiben. Darüber hinaus sind einige spezifische Formularfeldeigenschaften, die nur für XFA-Formulare gelten, möglicherweise nicht in AcroForms anwendbar.

#### F: Kann ich mit Aspose.PDF für .NET ein Standard-AcroForm in ein dynamisches XFA-Formular konvertieren?

A: Aspose.PDF für .NET unterstützt derzeit die Konvertierung dynamischer XFA-Formulare in Standard-AcroForms, aber nicht die umgekehrte Konvertierung von Standard-AcroForms in dynamische XFA-Formulare. Die Konvertierung von Standard-AcroForms in dynamische XFA-Formulare erfordert komplexere Transformationen und wird möglicherweise nicht in allen Szenarien vollständig unterstützt.