---
title: Utwórz element struktury notatki
linktitle: Utwórz element struktury notatki
second_title: Aspose.PDF z dokumentacją API .NET
description: Przewodnik krok po kroku dotyczący tworzenia uporządkowanych notatek w dokumencie PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 30
url: /pl/net/programming-with-tagged-pdf/create-note-structure-element/
---
W tym samouczku przedstawimy krok po kroku, jak utworzyć element struktury notatki w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Aspose.PDF to potężna biblioteka, która umożliwia programowe tworzenie, manipulowanie i konwertowanie dokumentów PDF. Korzystając z funkcji zaznaczonej struktury treści w Aspose.PDF, możesz dodawać uporządkowane notatki do swojego dokumentu PDF.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:

1. Visual Studio zainstalowany z platformą .NET.
2. Biblioteka Aspose.PDF dla .NET.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt w Visual Studio i dodaj odwołanie do biblioteki Aspose.PDF dla .NET. Możesz pobrać bibliotekę z oficjalnej strony Aspose i zainstalować ją na swoim komputerze.

## Krok 2: Zaimportuj niezbędne przestrzenie nazw

W pliku kodu C# zaimportuj przestrzenie nazw wymagane do uzyskania dostępu do klas i metod dostarczonych przez Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Krok 3: Tworzenie dokumentu PDF i elementów strukturalnych notatki

Użyj poniższego kodu, aby utworzyć dokument PDF i dodać elementy strukturalne notatki:

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

Ten kod tworzy pusty dokument PDF i dodaje do akapitu elementy uporządkowanej notatki. Każda notatka jest tworzona przy użyciu metod dostarczonych przez Aspose.PDF.

## Krok 4: Zapisywanie dokumentu PDF

Użyj poniższego kodu, aby zapisać dokument PDF:

```csharp
document. Save(outFile);
```

Ten kod zapisuje dokument PDF z elementami struktury notatki w określonym pliku.

### Przykładowy kod źródłowy narzędzia Utwórz element struktury notatki przy użyciu Aspose.PDF dla .NET 

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
// Dodaj element notatki
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
// Dodaj element notatki
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
// Dodaj element notatki
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
// Należy zgłosić wyjątek — Aspose.Pdf.Tagged.TaggedException: Element struktury o identyfikatorze ID='note_002' już istnieje
//notatka3.SetId("notatka_002");
// Dokument wynikowy nie jest zgodny z formatem PDF/UA, jeśli w elemencie struktury notatki użyto funkcji ClearId().
//notatka3.WyczyśćId();
// Zapisz oznaczony dokument PDF
document.Save(outFile);
// Sprawdzanie zgodności z PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Wniosek

W tym samouczku nauczyłeś się tworzyć elementy struktury notatek w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Strukturalne elementy notatek umożliwiają dodanie dodatkowych, uporządkowanych informacji do dokumentu PDF.

### Często zadawane pytania

#### P: Jaki jest cel tworzenia elementów struktury notatek w dokumencie PDF przy użyciu Aspose.PDF dla .NET?

Odp.: Tworzenie elementów struktury notatek w dokumencie PDF przy użyciu Aspose.PDF dla .NET umożliwia dodawanie uporządkowanych notatek do zawartości dokumentu. Notatki te mogą zawierać dodatkowy kontekst, wyjaśnienia lub odniesienia do określonych części treści.

#### P: W jaki sposób biblioteka Aspose.PDF pomaga w tworzeniu elementów struktury notatek w dokumencie PDF?

Odp.: Aspose.PDF dla .NET to potężna biblioteka zapewniająca funkcje umożliwiające programowe tworzenie, manipulowanie i konwertowanie dokumentów PDF. W tym samouczku funkcje struktury zaznaczonej zawartości biblioteki służą do tworzenia uporządkowanych elementów notatek w treści dokumentu PDF.

#### P: Jakie są wymagania wstępne dotyczące tworzenia elementów struktury notatek w dokumencie PDF przy użyciu Aspose.PDF dla .NET?

O: Zanim zaczniesz, upewnij się, że masz zainstalowany program Visual Studio ze środowiskiem .NET i że w projekcie znajduje się odwołanie do biblioteki Aspose.PDF dla .NET.

#### P: W jaki sposób dostarczony kod C# tworzy elementy struktury notatek w treści dokumentu PDF?

Odp.: Kod demonstruje, jak utworzyć dokument PDF, zdefiniować elementy strukturalne notatki i dodać je do akapitu. Każda notatka jest tworzona przy użyciu metod dostarczonych przez Aspose.PDF, co pozwala na włączenie notatek strukturalnych do treści.

#### P: Czy mogę dostosować zawartość i właściwości tworzonych przeze mnie elementów struktury nut?

O: Tak, możesz dostosować zawartość i właściwości elementów struktury nut, korzystając z metod i właściwości udostępnianych przez bibliotekę Aspose.PDF. Kod pokazuje, jak ustawić tekst i identyfikator elementów notatki, ale w razie potrzeby można je dodatkowo dostosować.

#### P: W jaki sposób ustanawiana jest hierarchiczna relacja pomiędzy elementami struktury notatki a treścią dokumentu?

 Odpowiedź: Relacja hierarchiczna jest ustanawiana poprzez dodanie elementów struktury notatki jako dzieci innych elementów strukturalnych, takich jak akapity. W kodzie elementy notatki są dołączane do elementu akapitu za pomocą`AppendChild` metoda.

#### P: Czy mogę przypisać unikalne identyfikatory do elementów struktury notatki?

Odp.: Tak, możesz przypisać unikalne identyfikatory elementom struktury notatki za pomocą`SetId` metoda. Kod demonstruje, jak ustawić identyfikatory elementów notatki na unikalne wartości.

#### P: Co się stanie, jeśli spróbuję przypisać zduplikowany identyfikator do elementu struktury notatki?

Odpowiedź: Próba przypisania zduplikowanego identyfikatora do elementu struktury notatki spowoduje wyjątek. Kod podany w samouczku zawiera komentarz ilustrujący ten scenariusz.

#### P: Jak mogę zapewnić zgodność z PDF/UA podczas tworzenia elementów struktury notatek?

 O: Kod podany w samouczku pokazuje, jak sprawdzić zgodność z PDF/UA za pomocą pliku`Validate` metoda. Walidując dokument pod kątem standardu PDF/UA, możesz mieć pewność, że dodane elementy struktury notatki są zgodne z wytycznymi dostępności.

#### P: Czy mogę zastosować tę metodę, aby dodać elementy struktury notatki do istniejącego dokumentu PDF?

Odp.: Tak, możesz zmodyfikować podane podejście, aby dodać elementy struktury notatki do istniejącego dokumentu PDF. Zamiast tworzyć nowy dokument, załadujesz istniejący dokument za pomocą Aspose.PDF, a następnie wykonaj podobne kroki, aby dołączyć elementy notatki.
