---
title: Dodaj adnotację lnk
linktitle: Dodaj adnotację lnk
second_title: Aspose.PDF dla .NET API Reference
description: Naucz się dodawać adnotacje atramentowe do plików PDF za pomocą Aspose.PDF dla platformy .NET dzięki temu wciągającemu przewodnikowi krok po kroku.
type: docs
weight: 20
url: /pl/net/annotations/addlnkannotation/
---
## Wstęp

Witamy w świecie manipulacji PDF z Aspose.PDF dla .NET! Jeśli chcesz ulepszyć swoje dokumenty PDF, czy to do użytku profesjonalnego, projektów osobistych, czy czegoś pomiędzy, jesteś we właściwym miejscu. Dzisiaj zagłębimy się w konkretną, ale praktyczną funkcję Aspose.PDF: dodawanie adnotacji atramentowej do plików PDF. Ta funkcjonalność może być niezwykle przydatna, gdy chcesz dodać do dokumentów notatki lub podpisy przypominające pismo odręczne, czyniąc je bardziej interaktywnymi i angażującymi.

## Wymagania wstępne

Zanim zagłębimy się w magię kodowania, upewnijmy się, że masz wszystko, czego potrzebujesz, aby zacząć:

1. .NET Framework: Upewnij się, że masz zainstalowany .NET na swoim komputerze. Ta biblioteka działa bezproblemowo z różnymi wersjami .NET, w tym .NET Core.
2.  Biblioteka Aspose.PDF: Musisz mieć bibliotekę Aspose.PDF dla .NET pobraną i odwołaną w swoim projekcie. Jeśli jeszcze tego nie zrobiłeś, możesz pobrać najnowszą wersję z[link do pobrania](https://releases.aspose.com/pdf/net/).
3. Edytor kodu: Możesz użyć dowolnego edytora kodu, jednak ze względu na łatwość obsługi aplikacji .NET zdecydowanie polecamy program Visual Studio.
4. Podstawowa znajomość języka C#: praktyczna znajomość języka C# pomoże Ci płynnie poruszać się po przykładach kodowania.
5. Konfigurowanie środowiska programistycznego: Upewnij się, że Twoje środowisko IDE jest skonfigurowane do obsługi projektów .NET i że w projekcie poprawnie odwołujesz się do biblioteki Aspose.PDF. 

Gdy spełnisz te wymagania wstępne, będziesz gotowy, aby zacząć dodawać adnotacje atramentowe do plików PDF!

## Importuj pakiety

Zanim przejdziemy do kodowania, zaimportujmy niezbędne pakiety. Na górze pliku C# dodaj następujące polecenia using:

```csharp
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
using System;
using System.Collections;
using System.Collections.Generic;
```

Dzięki temu uzyskasz dostęp do wszystkich klas i metod potrzebnych do pracy z adnotacjami w plikach PDF.

Teraz, gdy już przygotowaliśmy scenę, czas zakasać rękawy i przejść do konkretów! Rozłożymy każdy krok na czynniki pierwsze, aby upewnić się, że dokładnie rozumiesz, jak utworzyć i dodać adnotację atramentową do dokumentu PDF.

## Krok 1: Ustaw dokument i katalog

Pierwszą rzeczą, którą musisz zrobić, jest utworzenie dokumentu i ścieżki, w której chcesz zapisać plik wyjściowy. 

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
```
 Definiujemy zmienną`dataDir` , który wskazuje na katalog, w którym zostanie zapisany wynikowy plik PDF.`Document` Następnie obiekt zostaje utworzony i powstaje nowy dokument PDF gotowy do edycji.

## Krok 2: Dodaj stronę do dokumentu

Następnie należy dodać stronę do nowo utworzonego dokumentu.

```csharp
Page pdfPage = doc.Pages.Add();
```
Tutaj dodajemy nową stronę do naszego dokumentu. Każdy plik PDF potrzebuje co najmniej jednej strony, więc ten krok jest niezbędny.

## Krok 3: Zdefiniuj prostokąt rysunkowy

Zanim zaczniesz cokolwiek rysować, musisz określić, w którym miejscu strony chcesz umieścić adnotację.

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
```
 Tutaj tworzymy`Rectangle` obiekt, który określa obszar na stronie, w którym dodamy naszą adnotację atramentową. Ustawiamy jego wymiary tak, aby pasowały do całej strony, zaczynając od (0,0).

## Krok 4: Przygotuj punkty atramentowe

Teraz nadchodzi zabawna część — zdefiniowanie punktów, które składają się na Twoją adnotację tuszem. 

```csharp
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
```
Ten blok kodu tworzy listę tablic punktów, gdzie każda tablica reprezentuje zbiór punktów dla pociągnięcia tuszem. Tutaj definiujemy trzy punkty tworzące trójkąt; możesz dostosować współrzędne, aby pasowały do Twojego projektu.

## Krok 5: Utwórz adnotację atramentową

Mając już zdefiniowane punkty, czas na utworzenie właściwej adnotacji atramentowej.

```csharp
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList)
{
    Title = "XXX",
    Color = Aspose.Pdf.Color.LightBlue,
    CapStyle = CapStyle.Rounded
};
```
 Utworzyliśmy instancję`InkAnnotation`obiekt, przekazując stronę, prostokąt i punkty atramentu. Dodatkowo ustawiamy pewne właściwości, takie jak`Title`, `Color` , I`CapStyle`. Dostosuj je do swoich potrzeb!

## Krok 6: Ustaw obramowanie i krycie

Chcesz, aby Twoja adnotacja się wyróżniała? Nadajmy jej trochę stylu.

```csharp
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
```
Tutaj dodajemy obramowanie do adnotacji o określonej szerokości i ustawiamy jego krycie, dzięki czemu stanie się półprzezroczyste.

## Krok 7: Dodaj adnotację do strony

Teraz, gdy Twoja adnotacja jest już przygotowana, czas dodać ją do strony PDF.

```csharp
pdfPage.Annotations.Add(ia);
```
Ten wiersz dodaje adnotację atramentową, którą utworzyliśmy wcześniej, do zbioru adnotacji strony. 

## Krok 8: Zapisz dokument

Na koniec zapiszmy zmodyfikowany dokument.

```csharp
dataDir = dataDir + "AddInkAnnotation_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nInk annotation added successfully.\nFile saved at " + dataDir);
```
 Modyfikujemy nasze`dataDir` aby uwzględnić nazwę pliku wyjściowego i zapisać dokument. Wiadomość potwierdzająca jest drukowana na konsoli, aby poinformować Cię, że wszystko poszło gładko.

## Wniosek

masz! Udało Ci się dodać adnotację atramentową do dokumentu PDF za pomocą Aspose.PDF dla .NET. Ta prosta, ale skuteczna funkcja może ulepszyć Twoje dokumenty i uczynić je interaktywnymi. Niezależnie od tego, czy dodajesz podpisy, notatki czy rysunki, adnotacje atramentowe zapewniają wyjątkowy sposób na wzbogacenie treści.

## Najczęściej zadawane pytania

### Czym jest Aspose.PDF?
Aspose.PDF to biblioteka umożliwiająca tworzenie, edytowanie i konwertowanie dokumentów PDF w aplikacjach .NET.

### Czy mogę używać Aspose.PDF bezpłatnie?
 Tak! Aspose oferuje bezpłatną wersję próbną do oceny swoich produktów. Możesz ją pobrać[Tutaj](https://releases.aspose.com/).

### Czy można dodać wiele adnotacji atramentowych?
 Oczywiście! Możesz utworzyć wiele`InkAnnotation` obiekty i dodaj je do strony swojego dokumentu.

### Gdzie mogę znaleźć więcej przykładów?
 Możesz sprawdzić[dokumentacja](https://reference.aspose.com/pdf/net/) aby uzyskać szczegółowe instrukcje i przykłady.

### Co zrobić, jeśli potrzebuję wsparcia?
 Jeśli napotkasz jakiekolwiek problemy, możesz szukać pomocy na[forum wsparcia](https://forum.aspose.com/c/pdf/10).