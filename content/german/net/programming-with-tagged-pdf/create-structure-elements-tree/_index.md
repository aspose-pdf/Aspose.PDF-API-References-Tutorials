---
title: Strukturelementbaum erstellen
linktitle: Strukturelementbaum erstellen
second_title: Aspose.PDF für .NET API-Referenz
description: Erstellen Sie mit Aspose.PDF für .NET eine Struktur aus Baumelementen. Schritt-für-Schritt-Anleitung zum Erstellen eines strukturierten PDF-Dokuments.
type: docs
weight: 70
url: /de/net/programming-with-tagged-pdf/create-structure-elements-tree/
---
In dieser Schritt-für-Schritt-Anleitung erklären wir den Quellcode in C#, um mit Aspose.PDF für .NET eine Struktur aus Baumelementen zu erstellen. Wir zeigen Ihnen, wie Sie ein PDF-Dokument mit strukturierten Elementen erstellen und diese hierarchisch organisieren. Die Verwendung der Aspose.PDF-Bibliothek vereinfacht die Bearbeitung von PDF-Elementen erheblich und bietet erweiterte Funktionen für die Arbeit mit strukturierten Dokumenten.

## Schritt 1: Einrichten der Umgebung
 Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung mit Aspose.PDF für .NET eingerichtet haben. Stellen Sie außerdem sicher, dass Sie den Pfad zu Ihrem Dokumentenverzeichnis im`dataDir` Variable.

## Schritt 2: Erstellen eines PDF-Dokuments
 Zunächst erstellen wir ein neues PDF-Dokument mit dem`Document` Klasse bereitgestellt von Aspose.PDF. Hier ist der Code für diesen Schritt:

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen eines PDF-Dokuments
Document document = new Document();
```

## Schritt 3: Inhalte mit TaggedPdf nutzbar machen
 Die Aspose.PDF-Bibliothek ermöglicht das Arbeiten mit strukturierten PDF-Dokumenten unter Verwendung des Konzepts von Tagged PDF. Dazu benötigen wir einen Verweis auf das getaggte Inhaltselement mithilfe der`TaggedContent`Eigenschaft. Hier ist der Code für diesen Schritt:

```csharp
// Inhalte mit TaggedPdf bearbeiten
ITaggedContent taggedContent = document.TaggedContent;
```

## Schritt 4: Dokumenttitel und Sprache festlegen
 Bevor wir mit der Erstellung der Struktur der Elemente beginnen, müssen wir den Titel und die Sprache des Dokuments definieren. Dies kann mithilfe der`SetTitle` Und`SetLanguage` Methoden der`taggedContent` Objekt. Hier ist der Code für diesen Schritt:

```csharp
// Definieren Sie den Dokumenttitel und die Sprache
taggedContent.SetTitle("Structured PDF Document");
taggedContent.SetLanguage("fr-FR");
```

## Schritt 5: Logische Strukturelemente erstellen
Nachdem wir nun unser Dokument eingerichtet und den Titel und die Sprache festgelegt haben, können wir mit der Erstellung logischer Strukturelemente beginnen. Diese Elemente werden hierarchisch organisiert, um den Strukturbaum zu bilden. Hier ist der Code für diesen Schritt:

```csharp
// Abrufen des Stammstrukturelements (Dokument)
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
 Nachdem wir die Elementstruktur erstellt haben, können wir das PDF-Dokument speichern. Verwenden Sie dazu die`Save` Methode der`document` Objekt, um den Pfad und den Namen der zu speichernden PDF-Datei anzugeben. Hier ist der Code für diesen Schritt:

```csharp
// Speichern des getaggten PDF-Dokuments
document.Save(dataDir + "StructureElementsTree.pdf");
```

### Beispielquellcode zum Erstellen eines Strukturelementbaums mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// PDF-Dokument erstellen
Document document = new Document();
// Holen Sie sich Inhalte für die Arbeit mit TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// Titel und Sprache für Dokument festlegen
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
// Getaggtes PDF-Dokument speichern
document.Save(dataDir + "StructureElementsTree.pdf");

```

## Abschluss
Sie haben gelernt, wie Sie mit Aspose.PDF für .NET eine Struktur aus Baumelementen erstellen. Diese Anleitung hat Ihnen die erforderlichen Schritte gezeigt, um ein PDF-Dokument einzurichten, logische Strukturelemente zu erstellen und das endgültige Dokument zu speichern. Mit Aspose.PDF können Sie PDF-Elemente problemlos bearbeiten und strukturierte Dokumente erstellen.

### Häufig gestellte Fragen

#### F: Was ist der Zweck der Erstellung einer Struktur aus Baumelementen in einem PDF-Dokument mit Aspose.PDF für .NET?

A: Wenn Sie mit Aspose.PDF für .NET eine Struktur aus Baumelementen in einem PDF-Dokument erstellen, können Sie den Inhalt hierarchisch organisieren. Dieser strukturierte Ansatz verbessert die Zugänglichkeit, Navigation und Semantik des Dokuments und erleichtert Benutzern und unterstützenden Technologien die Interpretation und Interaktion mit dem Inhalt.

#### F: Wie erstellt der bereitgestellte C#-Code eine Struktur aus Baumelementen in einem PDF-Dokument?

A: Das Codebeispiel zeigt, wie man eine hierarchische Struktur logischer Elemente erstellt, indem man`SectElement`, `DivElement` , Und`ArtElement` Klassen, die von Aspose.PDF bereitgestellt werden. Diese Elemente sind als übergeordnete und untergeordnete Knoten organisiert und bilden eine baumartige Struktur innerhalb des Dokuments.

####  F: Wie funktioniert das`TaggedContent` property of the `Document` class contribute to creating a structured PDF document?

 A: Die`TaggedContent` -Eigenschaft bietet Zugriff auf die getaggten Inhaltsfunktionen des PDF-Dokuments. Auf diese Weise können Sie strukturierte Elemente erstellen und bearbeiten, ihre Beziehungen definieren und sie hierarchisch organisieren, wodurch die Struktur und Zugänglichkeit des Dokuments verbessert wird.

####  F: Warum ist es wichtig, den Titel und die Sprache des Dokuments mit dem`SetTitle` and `SetLanguage` methods?

 A: Festlegen des Titels und der Sprache des Dokuments mithilfe der`SetTitle` Und`SetLanguage` Methoden verbessern die Zugänglichkeit und Semantik des Dokuments. Sie helfen Benutzern und unterstützenden Technologien, den Zweck und die Sprache des Dokuments zu verstehen.

####  F: Wie sind`SectElement`, `DivElement`, and `ArtElement` used to create the structure tree?

 A: Diese Klassen repräsentieren verschiedene Arten von Strukturelementen.`SectElement` wird zum Erstellen von Abschnitten verwendet,`DivElement` für Unterteilungen innerhalb von Abschnitten und`ArtElement` für Grafiken oder Illustrationen. Indem Sie untergeordnete Elemente an übergeordnete Elemente anhängen, erstellen Sie eine hierarchische Struktur.

#### F: Welche Vorteile bietet die hierarchische Organisation von Elementen in einem PDF-Dokument?

A: Die hierarchische Organisation von Elementen verbessert die Dokumentorganisation, Navigation und Semantik. Benutzer und unterstützende Technologien können so die Struktur und Beziehungen des Inhalts verstehen und das allgemeine Benutzererlebnis verbessern.

####  F: Wie funktioniert das`Save` method ensure the preservation of the hierarchical structure in the tagged PDF document?

 A: Die`Save` Methode speichert das PDF-Dokument zusammen mit der hierarchischen Struktur, die mit dem`AppendChild` Methode. Dadurch wird sichergestellt, dass die Struktur erhalten bleibt und das Dokument zugänglich und gut organisiert ist.

#### F: Kann ich den Strukturbaum durch Hinzufügen anderer Arten logischer Elemente weiter anpassen?

A: Ja, Sie können den Strukturbaum weiter anpassen, indem Sie andere Arten logischer Elemente hinzufügen, die von Aspose.PDF bereitgestellt werden, wie z. B. Überschriften, Absätze, Abbildungen und mehr. Sie können mit verschiedenen Elementtypen experimentieren, um eine maßgeschneiderte Struktur zu erstellen.

#### F: Wie kann der erstellte strukturierte Baum die Zugänglichkeit und Benutzerfreundlichkeit von Dokumenten verbessern?

A: Der strukturierte Baum verbessert die Zugänglichkeit von Dokumenten, indem er dem Inhalt eine klare Hierarchie und semantische Bedeutung verleiht. Assistierende Technologien und Benutzer können die Struktur und Beziehungen des Dokuments effektiver navigieren, verstehen und interpretieren.

#### F: Wie kann ich dieses Wissen anwenden, um komplex strukturierte PDF-Dokumente für verschiedene Anwendungsfälle zu erstellen?

A: Sie können auf diesem Wissen aufbauen, indem Sie verschiedene Arten von Strukturelementen kombinieren und sie hierarchisch anordnen, um der gewünschten Inhaltsorganisation zu entsprechen. Dieser Ansatz ist für die Erstellung komplexer Dokumente wie Berichte, Artikel, Handbücher und mehr wertvoll.