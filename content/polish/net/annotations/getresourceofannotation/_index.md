---
title: Pobierz zasób adnotacji
linktitle: Pobierz zasób adnotacji
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak pobrać zasób adnotacji za pomocą Aspose.PDF dla .NET, korzystając z tego przewodnika krok po kroku.
type: docs
weight: 90
url: /pl/net/annotations/getresourceofannotation/
---
Przykład pokazuje, jak uzyskać zasób adnotacji za pomocą Aspose.PDF dla .NET. Aby uzyskać zasób adnotacji przy użyciu Aspose.PDF dla .NET, wykonaj następujące kroki:

## Krok 1: Ustaw ścieżkę katalogu, w którym znajduje się dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Otwórz dokument PDF zawierający adnotację, której zasób chcesz uzyskać.

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## Krok 3: Utwórz adnotację.

```csharp
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
```

## Krok 4: Dodaj adnotację do strony w dokumencie.

```csharp
doc.Pages[1].Annotations.Add(sa);
```

## Krok 5: Zapisz dokument.

```csharp
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Krok 6: Otwórz zmodyfikowany dokument.

```csharp
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Krok 7: Uzyskaj akcję adnotacji.

```csharp
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
```

## Krok 7: Uzyskaj wersję akcji.

```csharp
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
```

## Krok 8: Pobierz klip multimedialny.

```csharp
MediaClip clip = (rendition as MediaRendition).MediaClip;
```

## Krok 9: Uzyskaj specyfikację pliku.

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## Krok 10: Przeczytaj dane nośnika.

```csharp
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
   ms.Write(buffer, 0, read);
}
```

## Krok 11: Wydrukuj nazwę wersji i operacji renderowania.

```csharp
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

Wykonując poniższe kroki, możesz łatwo uzyskać zasób adnotacji w dokumencie PDF przy użyciu Aspose.PDF dla .NET.

### Przykładowy kod źródłowy dla Pobierz zasób adnotacji przy użyciu Aspose.PDF dla .NET:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument
Document doc = new Document(dataDir + "AddAnnotation.pdf");
//Utwórz adnotację
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
doc.Pages[1].Annotations.Add(sa);
// Zapisz dokument
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
// Otwórz dokument
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
//Pobierz akcję adnotacji
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
//Pobierz wersję akcji renderowania
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
// Klip multimedialny
MediaClip clip = (rendition as MediaRendition).MediaClip;
FileSpecification data = (clip as MediaClipData).Data;
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
//Dane nośników są dostępne w FileSpecification.Contents
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
ms.Write(buffer, 0, read);
}
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

## Wniosek

W tym samouczku omówiliśmy, jak uzyskać zasób określonej adnotacji z dokumentu PDF przy użyciu Aspose.PDF dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem i korzystając z dostarczonego kodu źródłowego C#, programiści mogą łatwo uzyskać dostęp do adnotacji i zarządzać nimi, w tym adnotacjami dotyczącymi wersji, w swoich dokumentach PDF.

### Często zadawane pytania

#### P: Co to jest wersja w kontekście adnotacji PDF?

Odp.: W kontekście adnotacji w formacie PDF wersja jest prezentacją treści multimedialnych. Umożliwia osadzanie multimediów, takich jak audio lub wideo, w dokumencie PDF. Adnotacja dotycząca wersji określa media, które mają być prezentowane i sposób ich odtwarzania.

#### P: Czy mogę uzyskać nazwę pliku multimedialnego powiązanego z adnotacją dotyczącą wersji?

O: Tak, możesz uzyskać nazwę pliku multimedialnego powiązanego z adnotacją dotyczącą wersji, używając Aspose.PDF dla .NET. Dostęp do nazwy pliku multimedialnego można uzyskać poprzez`FileSpecification` z`MediaClip` obiekt.

#### P: Czy Aspose.PDF dla .NET może wyodrębnić pliki multimedialne z adnotacji dotyczącej wersji?

O: Tak, Aspose.PDF dla .NET może wyodrębnić dane multimedialne z adnotacji dotyczącej wersji, która zawiera treść audio lub wideo, i zapisać je jako osobny plik.

#### P: Jak mogę uzyskać dostęp do danych multimedialnych adnotacji dotyczącej wersji?

 O: Dostęp do danych multimedialnych adnotacji dotyczących wersji można uzyskać poprzez`FileSpecification.Contents` własność`MediaClipData` obiekt.

#### P: Czy mogę modyfikować multimedia powiązane z adnotacją dotyczącą wersji przy użyciu Aspose.PDF dla .NET?

Odp.: Aspose.PDF dla .NET zapewnia metody dostępu i modyfikowania danych multimedialnych powiązanych z adnotacją dotyczącą wersji. Możesz zaktualizować lub zastąpić plik multimedialny używany w adnotacji dotyczącej wersji.