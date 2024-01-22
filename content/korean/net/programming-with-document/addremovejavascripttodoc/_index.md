---
title: PDF 문서에 Javascript 제거 추가
linktitle: 문서에 자바스크립트 제거 추가
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 문서에 JavaScript를 추가하고 제거하는 방법을 알아보세요. 문서 수준 스크립팅을 위한 코드 튜토리얼이 포함된 단계별 가이드입니다.
type: docs
weight: 30
url: /ko/net/programming-with-document/addremovejavascripttodoc/
---
PDF 문서에 JavaScript를 추가하고 제거하기 위해 Aspose.PDF for .NET 라이브러리를 활용합니다. 이 강력한 라이브러리를 사용하면 .NET 응용 프로그램에서 PDF 파일을 조작할 수 있습니다. .NET용 Aspose.PDF를 사용하여 JavaScript를 추가하고 제거하려면 아래의 단계별 지침을 따르십시오.

## 1단계: 새 PDF 문서 만들기

 새 인스턴스를 생성하여 시작합니다.`Document` .NET용 Aspose.PDF에서 제공하는 클래스입니다. 이는 JavaScript를 추가할 PDF 문서로 사용됩니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
```

## 2단계: 문서 수준에서 JavaScript 추가

 문서 수준에서 JavaScript를 추가하려면`JavaScript` 의 재산`Document` 수업. JavaScript 사전의 키에 JavaScript 함수를 할당합니다.

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");
```

 이 튜토리얼에서는 두 개의 JavaScript 함수를 추가했습니다.`func1` 그리고`func2`, PDF 문서로.

## 3단계: 문서 수준 JavaScript 제거

 문서 수준에서 JavaScript를 제거하려면 PDF 문서를 로드하고`JavaScript`사전. 키를 반복하고 원하는 JavaScript 함수를 제거합니다.

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;

foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed");
```

 이 튜토리얼에서는`func1` PDF 문서의 JavaScript 기능.

## 4단계: 변경 사항 저장 및 확인

수정된 PDF 문서를 저장하고 변경 사항을 확인합니다.

```csharp
Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

이 코드는 수정된 PDF 문서를 저장하고 성공 메시지를 표시합니다.

### .NET용 Aspose.PDF를 사용하여 PDF 문서에서 Javascript 추가 제거에 대한 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");

// 문서 수준 JavaScript 제거
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
	Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
Console.WriteLine("=============================== ");

Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

## 결론

이 기사에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서에서 JavaScript를 추가하고 제거하는 방법에 대한 단계별 가이드를 제공했습니다. 지침을 따르고 제공된 코드 튜토리얼을 활용하면 JavaScript를 PDF 문서에 쉽게 통합하고 필요할 때 제거할 수 있습니다. JavaScript는 PDF 파일에서 동적 기능과 상호 작용을 활성화하여 사용자 경험을 향상시킵니다.


### PDF 문서에 자바스크립트 추가 제거에 대한 FAQ

#### Q: .NET용 Aspose.PDF이 무엇인가요?

A: .NET용 Aspose.PDF는 개발자가 .NET 애플리케이션에서 PDF 파일을 효과적으로 조작할 수 있게 해주는 강력한 라이브러리입니다. 프로그래밍 방식으로 PDF 문서 작업을 위한 광범위한 기능을 제공합니다.

#### Q: .NET용 Aspose.PDF를 사용하여 PDF 문서에 JavaScript를 어떻게 추가할 수 있나요?

 A: 다음을 사용하여 문서 수준에서 JavaScript를 추가할 수 있습니다.`JavaScript` 의 재산`Document` 수업. JavaScript 사전의 키에 JavaScript 함수를 할당하기만 하면 됩니다.

#### Q: .NET용 Aspose.PDF를 사용하여 PDF 문서에서 JavaScript를 제거할 수 있습니까?

 답변: 예, 다음 페이지에 액세스하여 PDF 문서에서 JavaScript를 제거할 수 있습니다.`JavaScript` 사전을 삭제하고 원하는 JavaScript 기능을 제거합니다.

#### Q: Aspose.PDF for .NET은 전문 프로젝트에 적합합니까?

A: 물론입니다. .NET용 Aspose.PDF는 PDF 조작 및 생성 작업을 위한 전문 프로젝트에서 널리 사용됩니다. 높은 성능과 안정적인 기능을 제공합니다.

#### Q: PDF 문서에 JavaScript를 추가하면 어떤 이점이 있습니까?

답변: PDF 문서에 JavaScript를 추가하면 대화형의 동적 PDF 파일을 만들 수 있습니다. 양식 유효성 검사를 구현하고, 계산을 수행하고, 다양한 상호 작용 기능을 추가하여 사용자 경험을 향상시킬 수 있습니다.