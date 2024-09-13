---
title: Podpisz cyfrowo z znacznikiem czasu w pliku PDF
linktitle: Podpisz cyfrowo z znacznikiem czasu w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak cyfrowo podpisać plik PDF znacznikiem czasu za pomocą Aspose.PDF dla .NET. Ten przewodnik krok po kroku obejmuje wymagania wstępne, konfigurację certyfikatu, znaczniki czasu i wiele więcej.
type: docs
weight: 50
url: /pl/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
## Wstęp

Czy kiedykolwiek musiałeś podpisać cyfrowo plik PDF i dodać znacznik czasu dla dodatkowego bezpieczeństwa? Niezależnie od tego, czy pracujesz nad dokumentami prawnymi, umowami czy czymkolwiek, co wymaga bezpiecznego uwierzytelniania, podpis cyfrowy ze znacznikiem czasu dodaje dodatkową warstwę wiarygodności. W tym samouczku pokażemy, jak możesz użyć Aspose.PDF dla .NET, aby dodać podpis cyfrowy wraz ze znacznikiem czasu do swoich dokumentów PDF. Nie martw się, przeprowadzimy to krok po kroku!

## Wymagania wstępne

Zanim zagłębimy się w kod, musisz skonfigurować kilka rzeczy, aby móc kontynuować. Oto krótka lista kontrolna wymagań wstępnych, która pozwoli Ci zacząć:

-  Aspose.PDF dla biblioteki .NET: Będziesz potrzebować biblioteki Aspose.PDF dla .NET zainstalowanej w swoim projekcie. Możesz[pobierz najnowszą wersję tutaj](https://releases.aspose.com/pdf/net/) lub dodaj go do swojego projektu poprzez NuGet.
- Dokument PDF: Będziesz potrzebować przykładowego pliku PDF, aby z nim pracować. Upewnij się, że w katalogu projektu znajduje się plik, który chcesz podpisać.
-  Certyfikat cyfrowy (plik PFX): Upewnij się, że masz certyfikat cyfrowy (plik PFX).`.pfx` plik), aby cyfrowo podpisać dokument.
- Adres URL znacznika czasu: Jest to internetowa usługa znacznika czasu, która będzie wykorzystywana do dodawania znacznika czasu do podpisu cyfrowego. 
- Podstawowa znajomość języka C#: Nie musisz być ekspertem, ale znajomość podstaw języka C# pomoże Ci zrozumieć i dostosować kod.

Gdy już zaznaczysz wszystkie te pola, będziesz gotowy, aby zacząć kodować!

## Importuj pakiety

Aby rozpocząć, musisz zaimportować następujące przestrzenie nazw do swojego projektu C#. Dzięki temu masz dostęp do odpowiednich klas i funkcji Aspose.PDF.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Collections;
```

## Krok 1: Załaduj dokument PDF

Pierwszą rzeczą, którą musimy zrobić, jest załadowanie dokumentu PDF, który chcemy podpisać. Oto, jak to zrobić:

```csharp
// Zdefiniuj ścieżkę do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Załaduj dokument PDF
Document document = new Document(dataDir + @"DigitallySign.pdf");
```

 Ten krok jest dość prosty. Po prostu definiujemy ścieżkę do dokumentu, który chcemy podpisać.`Document` Klasa z Aspose.PDF zajmuje się ładowaniem pliku.

## Krok 2: Skonfiguruj podpis cyfrowy

Następnie utworzymy podpis cyfrowy przy użyciu klasy PKCS7 i załadujemy plik PFX. Ten plik PFX zawiera Twój certyfikat i klucz prywatny, które są niezbędne do podpisania dokumentu.

```csharp
// Ścieżka do pliku .pfx
string pfxFile = "YOUR DOCUMENTS DIRECTORY\\certificate.pfx";

// Zainicjuj obiekt podpisu
PdfFileSignature signature = new PdfFileSignature(document);

// Załaduj plik PFX z hasłem
PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
```

 W tym momencie mówisz Aspose, aby użył Twojego certyfikatu cyfrowego do podpisania dokumentu.`PKCS7`obiekt wykonuje za Ciebie całą pracę kryptograficzną, dzięki czemu nie musisz martwić się o szczegóły.

## Krok 3: Dodaj ustawienia znacznika czasu

Jednym z kluczowych elementów solidnego podpisu cyfrowego jest znacznik czasu. Zapewnia on, że podpis dokumentu można zweryfikować nawet po wygaśnięciu certyfikatu. Skonfigurujmy znacznik czasu za pomocą internetowego urzędu znaczników czasu.

```csharp
// Zdefiniuj ustawienia znacznika czasu
TimestampSettings timestampSettings = new TimestampSettings("https://twój_znacznik_czasu_url", "użytkownik:hasło");

// Dodaj ustawienia znacznika czasu do obiektu PKCS7
pkcs.TimestampSettings = timestampSettings;
```

Tutaj określasz adres URL dla usługi znaczników czasu, która automatycznie poda czas i datę do Twojego podpisu. Można to zrobić z uwierzytelnianiem lub bez niego.

## Krok 4: Określ lokalizację i wygląd podpisu

Teraz zdefiniujemy, gdzie podpis będzie się pojawiał w pliku PDF i jakie będą jego wymiary. Możesz dostosować położenie pola podpisu na stronie, a także jego rozmiar.

```csharp
//Zdefiniuj wygląd i lokalizację podpisu (strona 1, z określonym prostokątem)
System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
```

Tutaj definiujemy prostokąt, który umieszcza podpis na współrzędnych (100, 100) na pierwszej stronie pliku PDF, o szerokości 200 i wysokości 100. Możesz zmienić te wartości, aby dopasować je do swojego projektu.

## Krok 5: Podpisz dokument PDF

Gdy wszystko jest już skonfigurowane, nadszedł czas, aby zastosować podpis cyfrowy do pliku PDF. Ten krok łączy certyfikat, znacznik czasu i pozycjonowanie w jednym prostym poleceniu.

```csharp
// Podpisz dokument na pierwszej stronie
signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
```

Oto co się dzieje:
- 1: Oznacza to, że podpis powinien zostać umieszczony na pierwszej stronie.
- „Powód podpisu”: w tym miejscu możesz określić powód podpisania dokumentu.
- „Kontakt”: wprowadź dane kontaktowe osoby podpisującej.
- „Lokalizacja”: Określ lokalizację osoby podpisującej.
- prawda: Ta wartość logiczna wskazuje, czy podpis jest widoczny w dokumencie.
- rect: Prostokąt, który zdefiniowaliśmy wcześniej, określa rozmiar i pozycję podpisu.
- pkcs: Obiekt PKCS7 zawiera ustawienia certyfikatu cyfrowego i znacznika czasu.

## Krok 6: Zapisz podpisany plik PDF

Po podpisaniu dokumentu pozostaje tylko go zapisać. Możesz wybrać nową nazwę pliku, aby zachować zarówno wersję oryginalną, jak i podpisaną.

```csharp
// Zapisz podpisany dokument PDF
signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
```

Twój nowo podpisany i oznaczony znacznikiem czasu plik PDF został zapisany w określonym katalogu!

## Wniosek

I masz! Udało Ci się podpisać cyfrowo plik PDF znacznikiem czasu za pomocą Aspose.PDF dla .NET. Ten proces zapewnia autentyczność i integralność dokumentów, dając spokój ducha zarówno Tobie, jak i odbiorcy. Podpisy cyfrowe stają się coraz bardziej niezbędne w dzisiejszym cyfrowym świecie, więc opanowanie tego procesu jest zdecydowanie umiejętnością wartą posiadania.

## Najczęściej zadawane pytania

### Czy mogę użyć innego formatu pliku dla certyfikatu?  
Tak, ale samouczek skupia się na wykorzystaniu pliku PFX, który jest najpopularniejszym formatem certyfikatów cyfrowych.

### Czy aby zastosować znacznik czasu, muszę mieć połączenie z Internetem?  
Tak, ponieważ znacznik czasu jest pobierany z internetowej instytucji zajmującej się znacznikami czasu, potrzebny będzie dostęp do Internetu.

### Czy mogę podpisać wiele stron w pliku PDF?  
 Oczywiście! Możesz modyfikować`signature.Sign()` metoda umożliwiająca przeglądanie wielu stron lub pętli po wszystkich stronach.

### Co się stanie, jeśli hasło do pliku PFX będzie nieprawidłowe?  
Jeśli hasło będzie nieprawidłowe, pojawi się wyjątek, dlatego upewnij się, że zostało wprowadzone poprawnie.

### Czy mogę sprawić, że podpis będzie niewidoczny?  
 Tak, możesz przejść`false` do`Sign` parametr widoczności metody, który sprawia, że podpis staje się niewidoczny.