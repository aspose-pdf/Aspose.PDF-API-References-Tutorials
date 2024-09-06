---
title: Formulare im PDF-Dokument reduzieren
linktitle: Formulare im PDF-Dokument reduzieren
second_title: Aspose.PDF für .NET API-Referenz
description: Mit Aspose.PDF für .NET können Sie Formulare in PDF-Dokumenten ganz einfach reduzieren.
type: docs
weight: 100
url: /de/net/programming-with-forms/flatten-forms/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie Formulare mit Aspose.PDF für .NET abflachen. Wir erklären Ihnen den C#-Quellcode Schritt für Schritt, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie zunächst sicher, dass Sie die erforderlichen Bibliotheken importiert haben, und legen Sie den Pfad zum Dokumentverzeichnis fest:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Quell-PDF-Formular laden

Laden Sie das Quell-PDF-Formular:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Schritt 3: Die Formulare glätten

Überprüfen Sie zunächst, ob das Dokument Formularfelder enthält. Wenn ja, durchlaufen Sie jedes Feld und wenden Sie die Abflachung an:

```csharp
if (doc.Form.Fields.Count() > 0)
{
foreach (var item in doc.Form.Fields)
{
item. Flatten();
}
}
```

## Schritt 4: Speichern Sie das aktualisierte Dokument

Speichern Sie das aktualisierte PDF-Dokument:

```csharp
dataDir = dataDir + "FlattenForms_out.pdf";
doc.Save(dataDir);
```

### Beispielquellcode für Flatten Forms mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Quell-PDF-Formular laden
Document doc = new Document(dataDir + "input.pdf");
// Formulare abflachen
if (doc.Form.Fields.Count() > 0)
{
	foreach (var item in doc.Form.Fields)
	{
		item.Flatten();
	}
}
dataDir = dataDir + "FlattenForms_out.pdf";
// Speichern des aktualisierten Dokuments
doc.Save(dataDir);
Console.WriteLine("\nForms flattened successfully.\nFile saved at " + dataDir);
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man Formulare mit Aspose.PDF für .NET verfeinert. Indem Sie diese Schritte befolgen, können Sie Formulare in Ihren PDF-Dokumenten problemlos verfeinern, Felder nicht mehr editierbar machen und Anmerkungen mit dem Dokumentinhalt zusammenführen.

### Häufig gestellte Fragen

#### F: Was bedeutet „Formulare abflachen“ in Aspose.PDF für .NET?

A: Das Reduzieren von Formularen in Aspose.PDF für .NET bezieht sich auf den Vorgang, Formularfelder in einem PDF-Dokument nicht mehr editierbar zu machen und Anmerkungen (wie Formularfelder, Anmerkungen und digitale Signaturen) mit dem Inhalt des Dokuments zu verschmelzen. Sobald Formulare reduziert sind, können Benutzer die Formularfelder nicht mehr ändern und das visuelle Erscheinungsbild der Formularfelder wird Teil des statischen Inhalts des PDF-Dokuments.

#### F: Kann ich den Abflachungsprozess rückgängig machen und die Formularfelder wieder bearbeitbar machen?

A: Nein, sobald die Formularfelder abgeflacht sind, ist der Vorgang mit Aspose.PDF für .NET irreversibel. Durch das Abflachen wird das Erscheinungsbild der Formularfelder dauerhaft mit dem Inhalt des PDFs verschmolzen, und die einzelnen Formularfeldelemente sind nicht mehr zugänglich oder bearbeitbar.

#### F: Wann sollte ich Formulare in einem PDF-Dokument reduzieren?

A: Das Reduzieren von Formularen ist nützlich, wenn Sie das visuelle Erscheinungsbild von Formularfeldern und Anmerkungen in einem PDF-Dokument beibehalten und gleichzeitig verhindern möchten, dass Benutzer die Daten ändern. Dies wird häufig getan, wenn Sie ein PDF-Dokument mit vorab ausgefüllten Formulardaten oder Anmerkungen freigeben möchten, die von den Empfängern nicht geändert werden sollen.

#### F: Wirkt sich das Reduzieren von Formularen auf andere Anmerkungen aus, beispielsweise auf digitale Signaturen?

A: Ja, durch das Reduzieren von Formularen werden alle Anmerkungen, einschließlich digitaler Signaturen, mit dem Inhalt der PDF-Datei zusammengeführt. Sobald die Formulare reduziert sind, werden alle vorhandenen digitalen Signaturen zu einem dauerhaften Bestandteil des Dokuments und können von Benutzern weder geändert noch entfernt werden.

#### F: Kann ich bestimmte Formularfelder selektiv reduzieren und andere bearbeitbar lassen?

A: Ja, Sie können in einem PDF-Dokument gezielt bestimmte Formularfelder reduzieren, während andere bearbeitbar bleiben. Anstatt den Code zum Reduzieren aller Formularfelder zu verwenden, können Sie sich dafür entscheiden, nur die gewünschten Formularfelder basierend auf ihren Namen oder anderen Kriterien zu reduzieren.