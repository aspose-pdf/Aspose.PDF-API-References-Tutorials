---
title: Füllen Sie XFAFields
linktitle: Füllen Sie XFAFields
second_title: Aspose.PDF für .NET API-Referenz
description: Füllen Sie mit Aspose.PDF für .NET ganz einfach XFA-Felder in Ihre PDF-Dokumente.
type: docs
weight: 90
url: /de/net/programming-with-forms/fill-xfafields/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie XFA-Felder mit Aspose.PDF für .NET füllen. Wir erklären Ihnen Schritt für Schritt den C#-Quellcode, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie zunächst sicher, dass Sie die erforderlichen Bibliotheken importiert haben und legen Sie den Pfad zum Dokumentenverzeichnis fest:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das XFA-Formular

Laden Sie das XFA-Formular:

```csharp
Document doc = new Document(dataDir + "FillXFAFields.pdf");
```

## Schritt 3: XFA-Feldnamen abrufen

Rufen Sie die XFA-Feldnamen des Formulars ab:

```csharp
string[] names = doc.Form.XFA.FieldNames;
```

## Schritt 4: Feldwerte festlegen

Legen Sie die XFA-Feldwerte mit den zuvor erhaltenen Namen fest:

```csharp
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
```

## Schritt 5: Speichern Sie das aktualisierte Dokument

Speichern Sie das aktualisierte PDF-Dokument:

```csharp
dataDir = dataDir + "Filled_XFA_out.pdf";
doc.Save(dataDir);
```

### Beispielquellcode für Fill XFAFields mit Aspose.Words für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Laden Sie das XFA-Formular
Document doc = new Document(dataDir + "FillXFAFields.pdf");
//Rufen Sie Namen von XFA-Formularfeldern ab
string[] names = doc.Form.XFA.FieldNames;
// Feldwerte festlegen
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
dataDir = dataDir + "Filled_XFA_out.pdf";
// Speichern Sie das aktualisierte Dokument
doc.Save(dataDir);
Console.WriteLine("\nXFA fields filled successfully.\nFile saved at " + dataDir);
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man XFA-Felder mit Aspose.PDF für .NET füllt. Wenn Sie diese Schritte befolgen, können Sie mit Aspose.PDF ganz einfach die Werte von XFA-Feldern in Ihren PDF-Dokumenten ändern.