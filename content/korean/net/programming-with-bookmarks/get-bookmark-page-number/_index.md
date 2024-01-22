---
title: PDF 파일에서 북마크 페이지 번호 가져오기
linktitle: PDF 파일에서 북마크 페이지 번호 가져오기
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일의 북마크 페이지 번호를 쉽게 얻을 수 있습니다.
type: docs
weight: 60
url: /ko/net/programming-with-bookmarks/get-bookmark-page-number/
---
PDF 파일의 북마크와 연관된 페이지 번호를 검색하면 탐색에 유용할 수 있습니다. .NET용 Aspose.PDF를 사용하면 다음 소스 코드에 따라 북마크의 페이지 번호를 쉽게 얻을 수 있습니다.

## 1단계: 필수 라이브러리 가져오기

시작하기 전에 C# 프로젝트에 필요한 라이브러리를 가져와야 합니다. 필요한 import 지시문은 다음과 같습니다.

```csharp
using Aspose.Pdf.Facades;
```

## 2단계: 문서 폴더 경로 설정

 이 단계에서는 북마크 페이지 번호를 추출하려는 PDF 파일이 포함된 폴더의 경로를 지정해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"`다음 코드에 문서 폴더의 실제 경로를 입력하세요.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3단계: 북마크 편집기 만들기

 이제 우리는`PdfBookmarkEditor` 문서의 북마크를 조작하는 개체입니다. 다음 코드를 사용하세요.

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

## 4단계: PDF 파일 열기

 이 단계에서는 다음을 사용하여 PDF 파일을 엽니다.`BindPdf` 북마크 편집기의 방법. 해당 코드는 다음과 같습니다.

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

## 5단계: 북마크 추출

 이제 다음을 사용하여 문서에서 북마크를 추출하겠습니다.`ExtractBookmarks` 북마크 편집기의 방법. 해당 코드는 다음과 같습니다.

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

## 6단계: 북마크 탐색 및 페이지 번호 가져오기

 마지막으로 추출된 북마크를 반복하고 다음을 사용하여 각 북마크와 연관된 페이지 번호를 얻습니다.`foreach` 고리. 해당 코드는 다음과 같습니다.

```csharp
foreach (Bookmark bookmark in bookmarks)
{
     string strLevelSeprator = string.Empty;
     for (int i = 1; i < bookmark.Level; i++)
     {
         strLevelSeprator += "----";
     }
     Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
     Console.WriteLine("{0}Page number: {1}", strLevelSeprator, bookmark.PageNumber);
     Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

### .NET용 Aspose.PDF를 사용하여 북마크 페이지 번호 가져오기의 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// PDFBookmarkEditor 만들기
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
// PDF 파일 열기
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
// 북마크 추출
Aspose.Pdf.Facades.Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
foreach (Aspose.Pdf.Facades.Bookmark bookmark in bookmarks)
{
	string strLevelSeprator = string.Empty;
	for (int i = 1; i < bookmark.Level; i++)
	{
		strLevelSeprator += "----";
	}
	Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
	Console.WriteLine("{0}Page Number: {1}", strLevelSeprator, bookmark.PageNumber);
	Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

## 결론

축하합니다! 이제 .NET용 Aspose.PDF를 사용하여 북마크 페이지 번호를 얻는 방법에 대한 단계별 가이드가 있습니다. 이 코드를 사용하여 PDF 문서의 각 책갈피와 관련된 탐색 정보를 검색할 수 있습니다.

고급 북마크 조작 기능에 대한 자세한 내용은 공식 Aspose.PDF 문서를 확인하세요.

### PDF 파일에서 북마크 페이지 번호 가져오기에 대한 FAQ

#### Q: PDF 파일의 북마크란 무엇입니까?

A: PDF 파일의 북마크는 사용자가 문서 내의 특정 섹션이나 페이지로 빠르게 이동할 수 있는 탐색 보조 도구입니다. 관련 콘텐츠에 대한 바로가기를 제공하여 사용자 경험을 향상시킵니다.

#### Q: PDF 파일에서 북마크 페이지 번호를 검색하려는 이유는 무엇입니까?

A: 북마크 페이지 번호를 검색하면 사용자가 문서를 더욱 효과적으로 탐색할 수 있으며 각 북마크가 어디로 연결되는지 명확하게 표시할 수 있습니다. 이는 여러 섹션이 포함된 긴 문서에 특히 유용합니다.

#### Q: C# 프로젝트에 필요한 라이브러리를 어떻게 가져오나요?

A: C# 프로젝트에 필요한 라이브러리를 가져오려면 다음 가져오기 지시문을 사용하세요.

```csharp
using Aspose.Pdf.Facades;
```

이 지시문을 사용하면 Aspose.PDF for .NET에서 제공하는 클래스와 메서드를 활용할 수 있습니다.

#### Q: 문서 폴더의 경로를 어떻게 지정합니까?

 A: 제공된 소스 코드에서`"YOUR DOCUMENT DIRECTORY"`북마크 페이지 번호를 추출하려는 PDF 파일이 포함된 폴더의 실제 경로를 사용합니다. 이렇게 하면 코드가 대상 PDF 파일을 찾을 수 있습니다.

#### Q: 북마크 편집기는 어떻게 생성하나요?

A: 북마크 편집기를 만들려면 다음 코드를 사용하세요.

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

#### Q: 북마크 조작을 위해 PDF 파일을 어떻게 열 수 있나요?

A: 북마크 정보를 추출하기 위해 PDF 파일을 열려면 다음 코드를 사용하십시오.

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

 바꾸다`"GetBookmarks.pdf"` 실제 파일 이름으로.

#### Q: PDF 파일에서 북마크를 어떻게 추출합니까?

 A: PDF 파일에서 북마크를 추출하려면`ExtractBookmarks` 북마크 편집기 방법:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

#### Q: 북마크 페이지 번호를 검색하고 표시하려면 어떻게 해야 합니까?

 A: 다음을 사용하여 추출된 북마크를 반복합니다.`foreach` 루프를 실행하고 액세스합니다.`PageNumber` 연관된 페이지 번호를 검색하고 표시하려면 각 책갈피의 속성을 사용하세요.

```csharp
foreach (Bookmark bookmark in bookmarks)
{
    Console.WriteLine("Title: " + bookmark.Title);
    Console.WriteLine("Page Number: " + bookmark.PageNumber);
    Console.WriteLine("Page Action: " + bookmark.Action);
}
```

#### Q: 이 접근 방식을 사용하여 책갈피 속성을 수정할 수 있습니까?

 A: 이 튜토리얼은 북마크 페이지 번호 검색에 중점을 두고 있지만 동일한 페이지 번호를 사용하여 다른 북마크 속성을 수정할 수 있습니다.`Bookmark`개체 및 관련 속성.

#### Q: 북마크 정보 추출 후 업데이트된 PDF 파일을 어떻게 저장하나요?

A: 북마크 추출은 원본 PDF 파일을 수정하지 않습니다. 변경 사항을 저장하려면 Aspose.PDF for .NET에서 제공하는 다른 방법을 사용하면 됩니다.