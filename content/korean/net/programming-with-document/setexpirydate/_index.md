---
title: PDF 파일에 만료 날짜 설정
linktitle: PDF 파일에 만료 날짜 설정
second_title: .NET API 참조용 Aspose.PDF
description: 이 단계별 가이드를 통해 .NET용 Aspose.PDF를 사용하여 PDF 파일에 만료 날짜를 설정하는 방법을 알아보세요.
type: docs
weight: 300
url: /ko/net/programming-with-document/setexpirydate/
---
Aspose.PDF for .NET은 PDF 파일 작업을 위한 다양한 기능을 제공하는 강력한 라이브러리입니다. 그러한 기능 중 하나는 PDF 문서의 만료 날짜를 설정하는 기능입니다. 이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서의 만료 날짜를 설정하는 과정을 안내합니다. 

## 1단계: 문서 디렉터리 경로 설정

시작하기 전에 PDF 문서가 있는 디렉토리의 경로를 설정해야 합니다. 이 경로를 "dataDir"이라는 변수에 저장합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 새 PDF 문서 만들기

 새 PDF 문서를 만들려면 새 문서를 인스턴스화해야 합니다.`Aspose.Pdf.Document` 물체. 다음 코드를 사용하여 이를 수행할 수 있습니다.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## 3단계: PDF 문서에 새 페이지 추가

PDF 문서를 만든 후에는 새 페이지를 추가할 수 있습니다. 다음 코드를 사용하여 이를 수행할 수 있습니다.

```csharp
doc.Pages.Add();
```

## 4단계: PDF 문서에 텍스트 추가

PDF 문서에 페이지를 추가한 후 다음을 사용하여 텍스트를 추가할 수 있습니다.`Paragraphs` 수집. 다음 코드를 사용하여 이를 수행할 수 있습니다.

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## 5단계: JavaScript를 사용하여 PDF 만료일 설정

PDF 만료 날짜를 설정하려면 JavaScript 개체를 생성해야 합니다. 다음 코드를 사용하여 이를 수행할 수 있습니다.

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");

// JavaScript를 PDF 열기 작업으로 설정
doc.OpenAction = javaScript;
```

이 코드에서는 만료 날짜를 2017년 5월로 설정합니다.

## 6단계: PDF 파일 저장

 만료 날짜를 설정한 후에는 PDF 파일을 저장해야 합니다. 이렇게 하려면 다음을 사용할 수 있습니다.`Save` 의 방법`Document` 개체를 선택하고 업데이트된 PDF 파일을 저장할 경로를 전달합니다.

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
// PDF 문서 저장
doc.Save(dataDir);
```

### .NET용 Aspose.PDF를 사용하여 만료 날짜 설정에 대한 예제 소스 코드

다음은 .NET용 Aspose.PDF를 사용하여 만료 날짜를 설정하는 전체 예제 소스 코드입니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 객체 인스턴스화
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// PDF 파일의 페이지 모음에 페이지 추가
doc.Pages.Add();
// 페이지 개체의 단락 컬렉션에 텍스트 조각 추가
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
// PDF 만료 날짜를 설정하는 JavaScript 개체 만들기
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
// JavaScript를 PDF 열기 작업으로 설정
doc.OpenAction = javaScript;

dataDir = dataDir + "SetExpiryDate_out.pdf";
// PDF 문서 저장
doc.Save(dataDir);
```

## 결론

.NET용 Aspose.PDF를 사용하여 PDF 문서의 만료 날짜를 설정하는 것은 문서가 지정된 기간 동안만 유효한지 확인하는 데 유용한 기능입니다. 단계별 가이드를 따르고 제공된 C# 소스 코드를 사용하여 개발자는 쉽게 만료 날짜를 설정하고 시간 제한이 있는 유효성을 가진 PDF를 만들 수 있습니다. 이 기능은 제한된 기간 동안 액세스하거나 배포해야 하는 문서에 특히 유용할 수 있습니다.

### PDF 파일로 설정된 만료 날짜에 대한 FAQ

#### Q: PDF 문서에 대해 다른 만료 날짜를 설정할 수 있습니까?

 A: 예, 5단계에서 JavaScript 코드를 수정하여 PDF 문서의 만료 날짜를 다르게 설정할 수 있습니다. 제공된 예에서 만료 날짜는 2017년 5월로 설정되어 있습니다. 다른 만료 날짜를 설정하려면`year` 그리고`month` JavaScript 코드의 변수를 원하는 연도 및 월로 설정합니다.

#### Q: PDF 문서가 만료되면 어떻게 되나요?

답변: JavaScript 코드에 지정된 대로 PDF 문서가 만료되면 뷰어는 파일이 만료되었으며 사용자에게 새 파일이 필요하다는 경고 메시지를 표시합니다. 이 경고 메시지는 PDF를 열 때 표시됩니다.

#### Q: 만료일에 날짜만 사용하는 대신 특정 시간을 사용할 수 있나요?

 A: 예, JavaScript 코드에서 만료 날짜에 대한 특정 시간을 설정할 수 있습니다. 수정하여`expiry` 원하는 시간을 포함하도록 JavaScript 코드의 변수에 만료 날짜에 대한 특정 시간을 설정할 수 있습니다.