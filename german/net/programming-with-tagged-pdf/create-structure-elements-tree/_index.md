---
title: Erstellen Sie einen Strukturelementbaum
linktitle: Erstellen Sie einen Strukturelementbaum
second_title: Aspose.PDF für .NET API-Referenz
description: Erstellen Sie mit Aspose.PDF für .NET eine Struktur aus Baumelementen. Schritt-für-Schritt-Anleitung zum Erstellen eines strukturierten PDF-Dokuments.
type: docs
weight: 70
url: /de/net/programming-with-tagged-pdf/create-structure-elements-tree/
---
In dieser Schritt-für-Schritt-Anleitung erklären wir den Quellcode in C#, um mit Aspose.PDF für .NET eine Struktur aus Baumelementen zu erstellen. Wir zeigen Ihnen, wie Sie ein PDF-Dokument mit strukturierten Elementen erstellen und diese hierarchisch organisieren. Die Verwendung der Aspose.PDF-Bibliothek vereinfacht die Bearbeitung von PDF-Elementen erheblich und bietet erweiterte Funktionen für die Arbeit mit strukturierten Dokumenten.

## Schritt 1: Einrichten der Umgebung
Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung mit Aspose.PDF für .NET eingerichtet haben. Stellen Sie außerdem sicher, dass Sie den Pfad zu Ihrem Dokumentenverzeichnis festgelegt haben`dataDir` Variable.

## Schritt 2: Erstellen eines PDF-Dokuments
 Zunächst erstellen wir ein neues PDF-Dokument mit`Document` Klasse bereitgestellt von Aspose.PDF. Hier ist der Code für diesen Schritt:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie ein PDF-Dokument
Document document = new Document();
```

## Schritt 3: Inhalte mit TaggedPdf zum Laufen bringen
 Die Aspose.PDF-Bibliothek ermöglicht die Arbeit mit strukturierten PDF-Dokumenten unter Verwendung des Konzepts von Tagged PDF. Dazu müssen wir mithilfe des Dokuments einen Verweis auf das getaggte Inhaltselement erhalten`TaggedContent` Eigentum. Hier ist der Code für diesen Schritt:

```csharp
// Bringen Sie Inhalte mit TaggedPdf zum Einsatz
ITaggedContent taggedContent = document.TaggedContent;
```

## Schritt 4: Dokumenttitel und Sprache festlegen
 Bevor wir mit der Erstellung der Struktur der Elemente beginnen, müssen wir den Titel und die Sprache des Dokuments definieren. Dies kann mit der erfolgen`SetTitle` Und`SetLanguage` Methoden der`taggedContent` Objekt. Hier ist der Code für diesen Schritt:

```csharp
// Definieren Sie den Titel und die Sprache des Dokuments
taggedContent.SetTitle("Structured PDF Document");
taggedContent.SetLanguage("fr-FR");
```

## Schritt 5: Logische Strukturelemente erstellen
Nachdem wir nun unser Dokument eingerichtet und Titel und Sprache festgelegt haben, können wir mit der Erstellung logischer Strukturelemente beginnen. Diese Elemente werden hierarchisch organisiert, um den Strukturbaum zu bilden. Hier ist der Code für diesen Schritt:

```csharp
// Erhalten Sie das Stammstrukturelement (Dokument)
StructureElement rootElement = taggedContent.RootElement;

// Erstellen Sie die logische Struktur
SectElement sect1 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect1);

SectElement sect2 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect2);

DivElement div11 = taggedContent.CreateDivElement();
sect1.AppendChild(div11);

DivElement div12 = taggedContent.CreateDivElement();
sect1.AppendChild(div12);

ArtElement art21 = taggedContent.CreateArtElement();
sect2.AppendChild(art21);

ArtElement art22

  = taggedContent.CreateArtElement();
sect2.AppendChild(art22);

DivElement div211 = taggedContent.CreateDivElement();
art21.AppendChild(div211);

DivElement div212 = taggedContent.CreateDivElement();
art21.AppendChild(div212);

DivElement div221 = taggedContent.CreateDivElement();
art22.AppendChild(div221);

DivElement div222 = taggedContent.CreateDivElement();
art22.AppendChild(div222);

SectElement sect3 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect3);

DivElement div31 = taggedContent.CreateDivElement();
sect3.AppendChild(div31);
```

## Schritt 6: Speichern des getaggten PDF-Dokuments
 Nachdem wir die Elementstruktur erstellt haben, können wir das PDF-Dokument speichern. Benutzen Sie die`Save` Methode der`document` -Objekt, um den Pfad und Namen der zu speichernden PDF-Datei anzugeben. Hier ist der Code für diesen Schritt:

```csharp
// Speichern Sie das getaggte PDF-Dokument
document.Save(dataDir + "StructureElementsTree.pdf");
```

### Beispielquellcode für „Strukturelementbaum erstellen“ mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Erstellen Sie ein PDF-Dokument
Document document = new Document();
// Holen Sie sich Inhalte für die Arbeit mit TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// Legen Sie Titel und Sprache für Documentt fest
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
// Stammstrukturelement abrufen (Dokument)
StructureElement rootElement = taggedContent.RootElement;
// Erstellen Sie eine logische Struktur
SectElement sect1 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect1);
SectElement sect2 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect2);
DivElement div11 = taggedContent.CreateDivElement();
sect1.AppendChild(div11);
DivElement div12 = taggedContent.CreateDivElement();
sect1.AppendChild(div12);
ArtElement art21 = taggedContent.CreateArtElement();
sect2.AppendChild(art21);
ArtElement art22 = taggedContent.CreateArtElement();
sect2.AppendChild(art22);
DivElement div211 = taggedContent.CreateDivElement();
art21.AppendChild(div211);
DivElement div212 = taggedContent.CreateDivElement();
art21.AppendChild(div212);
DivElement div221 = taggedContent.CreateDivElement();
art22.AppendChild(div221);
DivElement div222 = taggedContent.CreateDivElement();
art22.AppendChild(div222);
SectElement sect3 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect3);
DivElement div31 = taggedContent.CreateDivElement();
sect3.AppendChild(div31);
// Markiertes PDF-Dokument speichern
document.Save(dataDir + "StructureElementsTree.pdf");

```

## Abschluss
Sie haben gelernt, wie Sie mit Aspose.PDF für .NET eine Struktur aus Baumelementen erstellen. Dieser Leitfaden hat Ihnen die Schritte gezeigt, die zum Einrichten eines PDF-Dokuments, zum Erstellen logischer Strukturelemente und zum Speichern des endgültigen Dokuments erforderlich sind. Mit Aspose.PDF können Sie PDF-Elemente einfach bearbeiten und strukturierte Dokumente erstellen.
