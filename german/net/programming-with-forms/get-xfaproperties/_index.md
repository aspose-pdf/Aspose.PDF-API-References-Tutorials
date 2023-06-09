---
title: Holen Sie sich XFAProperties
linktitle: Holen Sie sich XFAProperties
second_title: Aspose.PDF für .NET API-Referenz
description: Erhalten Sie mit Aspose.PDF für .NET ganz einfach XFA-Eigenschaften von Formularfeldern in Ihren PDF-Dokumenten.
type: docs
weight: 160
url: /de/net/programming-with-forms/get-xfaproperties/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET XFA-Eigenschaften von Formularfeldern in einem PDF-Dokument abrufen. Wir erklären Ihnen Schritt für Schritt den C#-Quellcode, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie sicher, dass Sie die erforderlichen Bibliotheken importiert und den Pfad zu Ihrem Dokumentenverzeichnis festgelegt haben:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden Sie das XFA-Formular

Laden Sie das XFA-Formular aus dem PDF-Dokument:

```csharp
Document doc = new Document(dataDir + "GetXFAProperties.pdf");
```

## Schritt 3: Feldnamen abrufen

XFA-Feldnamen abrufen:

```csharp
string[] names = doc.Form.XFA.FieldNames;
```

## Schritt 4: Feldwerte festlegen

Legen Sie Werte für XFA-Felder fest:

```csharp
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
```

## Schritt 5: Position der Felder ermitteln

Ermitteln Sie die Position der XFA-Felder:

```csharp
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["x"].Value);
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["y"].Value);
```

## Schritt 6: Speichern Sie das aktualisierte Dokument

Speichern Sie das aktualisierte PDF-Dokument:

```csharp
dataDir = dataDir + "Filled_XFA_out.pdf";
doc.Save(dataDir);
```

### Beispielquellcode für „Get XFAProperties“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Laden Sie das XFA-Formular
Document doc = new Document(dataDir + "GetXFAProperties.pdf");
string[] names = doc.Form.XFA.FieldNames;
// Feldwerte festlegen
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
// Feldposition abrufen
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["x"].Value);
// Feldposition abrufen
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["y"].Value);
dataDir = dataDir + "Filled_XFA_out.pdf";
// Speichern Sie das aktualisierte Dokument
doc.Save(dataDir);
Console.WriteLine("\nXFA fields properties retrieved successfully.\nFile saved at " + dataDir);
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET XFA-Eigenschaften von Formularfeldern in einem PDF-Dokument erhält. Wenn Sie diese Schritte befolgen, können Sie mit Aspose.PDF ganz einfach XFA-Feldinformationen, wie z. B. Positionen, aus PDF-Dokumenten extrahieren.