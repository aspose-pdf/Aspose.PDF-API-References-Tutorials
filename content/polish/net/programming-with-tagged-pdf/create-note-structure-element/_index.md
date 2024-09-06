---
title: Utwórz element struktury notatki
linktitle: Utwórz element struktury notatki
second_title: Aspose.PDF dla .NET API Reference
description: Przewodnik krok po kroku pokazujący, jak tworzyć ustrukturyzowane elementy notatek w dokumencie PDF przy użyciu Aspose.PDF dla platformy .NET.
type: docs
weight: 30
url: /pl/net/programming-with-tagged-pdf/create-note-structure-element/
---
W tym samouczku przedstawimy Ci przewodnik krok po kroku, jak utworzyć element struktury notatki w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Aspose.PDF to potężna biblioteka, która umożliwia programowe tworzenie, manipulowanie i konwertowanie dokumentów PDF. Korzystając z funkcji struktury oznaczonej zawartości Aspose.PDF, możesz dodawać ustrukturyzowane notatki do swojego dokumentu PDF.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:

1. Zainstalowano program Visual Studio z platformą .NET Framework.
2. Biblioteka Aspose.PDF dla .NET.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt w Visual Studio i dodaj odwołanie do biblioteki Aspose.PDF dla .NET. Możesz pobrać bibliotekę z oficjalnej strony internetowej Aspose i zainstalować ją na swoim komputerze.

## Krok 2: Zaimportuj niezbędne przestrzenie nazw

W pliku kodu C# zaimportuj przestrzenie nazw wymagane do uzyskania dostępu do klas i metod udostępnianych przez Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Krok 3: Tworzenie dokumentu PDF i zapisywanie elementów strukturalnych

Użyj poniższego kodu, aby utworzyć dokument PDF i dodać elementy strukturalne notatek:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample Grade Items");
taggedContent.SetLanguage("fr-FR");

ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);

NoteElement note1 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note1);
note1.SetText("Note with automatically generated ID. ");

NoteElement note2 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note2);
note2.SetText("Note with ID = 'note_002'.");
note2.SetId("note_002");

NoteElement note3 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note3);
note3.SetText("Note with ID = 'note_003'.");
note3.SetId("note_003");
```

Ten kod tworzy pusty dokument PDF i dodaje strukturalne elementy notatek do akapitu. Każda notatka jest tworzona przy użyciu metod dostarczonych przez Aspose.PDF.

## Krok 4: Zapisywanie dokumentu PDF

Użyj poniższego kodu, aby zapisać dokument PDF:

```csharp
document. Save(outFile);
```

Ten kod zapisuje dokument PDF ze strukturą elementów notatki do określonego pliku.

### Przykładowy kod źródłowy dla funkcji Create Note Structure Element przy użyciu Aspose.PDF dla .NET 

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
// Utwórz dokument PDF
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
// Dodaj element akapitu
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
// Dodaj notatkęElement
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
// Dodaj notatkęElement
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
// Dodaj notatkęElement
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
// Musi zostać zgłoszony wyjątek - Aspose.Pdf.Tagged.TaggedException: Element struktury o ID='note_002' już istnieje
//uwaga3.SetId("uwaga_002");
// Wynikowy dokument nie jest zgodny ze standardem PDF/UA, jeśli dla elementu struktury notatki użyto ClearId()
//uwaga 3.ClearId();
// Zapisz oznaczony dokument PDF
document.Save(outFile);
// Sprawdzanie zgodności PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Wniosek

W tym samouczku dowiedziałeś się, jak tworzyć elementy struktury notatek w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Ustrukturyzowane elementy notatek pozwalają na dodawanie dodatkowych, ustrukturyzowanych informacji do dokumentu PDF.

### Najczęściej zadawane pytania

#### P: Jaki jest cel tworzenia elementów struktury notatek w dokumencie PDF za pomocą Aspose.PDF dla platformy .NET?

A: Tworzenie elementów struktury notatek w dokumencie PDF przy użyciu Aspose.PDF dla .NET umożliwia dodawanie strukturalnych notatek do zawartości dokumentu. Notatki te mogą zawierać dodatkowy kontekst, wyjaśnienia lub odniesienia do określonych części zawartości.

#### P: W jaki sposób biblioteka Aspose.PDF pomaga w tworzeniu elementów struktury notatek w dokumencie PDF?

A: Aspose.PDF dla .NET to potężna biblioteka, która zapewnia funkcjonalności do tworzenia, manipulowania i konwertowania dokumentów PDF programowo. W tym samouczku funkcje struktury zawartości biblioteki są używane do tworzenia ustrukturyzowanych elementów notatek w zawartości dokumentu PDF.

#### P: Jakie są wymagania wstępne dotyczące tworzenia elementów struktury notatek w dokumencie PDF za pomocą Aspose.PDF dla platformy .NET?

O: Zanim zaczniesz, upewnij się, że masz zainstalowany program Visual Studio z platformą .NET Framework i że w projekcie znajduje się odwołanie do biblioteki Aspose.PDF dla platformy .NET.

#### P: W jaki sposób dostarczony kod C# tworzy elementy struktury notatek w treści dokumentu PDF?

A: Kod pokazuje, jak utworzyć dokument PDF, zdefiniować elementy strukturalne notatek i dodać je do akapitu. Każda notatka jest tworzona przy użyciu metod dostarczonych przez Aspose.PDF, co pozwala na włączenie strukturalnych notatek do treści.

#### P: Czy mogę dostosować zawartość i właściwości elementów struktury notatki, które tworzę?

A: Tak, możesz dostosować zawartość i właściwości elementów struktury notatek, korzystając z metod i właściwości udostępnianych przez bibliotekę Aspose.PDF. Kod pokazuje, jak ustawić tekst i ID elementów notatek, ale możesz je dalej dostosowywać w razie potrzeby.

#### P: W jaki sposób ustalana jest hierarchiczna relacja między elementami struktury notatki a zawartością dokumentu?

 A: Relacja hierarchiczna jest ustalana poprzez dodawanie elementów struktury notatek jako elementów podrzędnych innych elementów strukturalnych, takich jak akapity. W kodzie elementy notatek są dołączane do elementu akapitu za pomocą`AppendChild` metoda.

#### P: Czy mogę przypisać unikalne identyfikatory do elementów struktury notatek?

O: Tak, możesz przypisać unikalne identyfikatory do elementów struktury notatek, korzystając z`SetId` metoda. Kod pokazuje, jak ustawić identyfikatory elementów notatki na unikalne wartości.

#### P: Co się stanie, jeśli spróbuję przypisać duplikat identyfikatora do elementu struktury notatki?

A: Próba przypisania duplikatu ID do elementu struktury notatki spowoduje wyjątek. Kod podany w samouczku zawiera komentarz ilustrujący ten scenariusz.

#### P: Jak mogę zagwarantować zgodność ze standardem PDF/UA podczas tworzenia elementów struktury notatek?

 A: Kod podany w samouczku pokazuje, jak sprawdzić zgodność PDF/UA za pomocą`Validate` metoda. Walidując dokument pod kątem standardu PDF/UA, możesz upewnić się, że dodane elementy struktury notatek są zgodne z wytycznymi dostępności.

#### P: Czy mogę użyć tego podejścia, aby dodać elementy struktury notatek do istniejącego dokumentu PDF?

A: Tak, możesz zmodyfikować podane podejście, aby dodać elementy struktury notatki do istniejącego dokumentu PDF. Zamiast tworzyć nowy dokument, należy załadować istniejący dokument za pomocą Aspose.PDF, a następnie wykonać podobne kroki, aby dołączyć elementy notatki.
