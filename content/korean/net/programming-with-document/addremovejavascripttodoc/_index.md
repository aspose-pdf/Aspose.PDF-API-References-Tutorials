---
title: PDF 문서에 Javascript 추가 및 제거
linktitle: 문서에 Javascript 추가 및 제거
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 문서에 JavaScript를 추가하고 제거하는 방법을 알아보세요. 문서 수준 스크립팅을 위한 코드 튜토리얼이 포함된 단계별 가이드입니다.
type: docs
weight: 30
url: /ko/net/programming-with-document/addremovejavascripttodoc/
---
## 소개

이 가이드에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에 JavaScript를 삽입하는 방법과 필요한 경우 제거하는 방법을 살펴보겠습니다. 이 튜토리얼을 마치면 PDF에서 JavaScript를 손쉽게 조작하는 방법을 명확하게 이해하게 될 것입니다.

## 필수 조건

코드를 자세히 살펴보기 전에 먼저 설정해야 할 몇 가지 사항이 있습니다.

1.  .NET용 Aspose.PDF: 프로젝트에 Aspose.PDF for .NET 라이브러리가 설치되어 있어야 합니다. 아직 설치되어 있지 않으면 라이브러리를 가져오세요.[.NET용 Aspose.PDF 다운로드 페이지](https://releases.aspose.com/pdf/net/).
2. IDE 또는 텍스트 편집기: Visual Studio와 같은 .NET 호환 IDE를 사용할 수 있습니다.
3. 기본 C# 지식: 이 튜토리얼에서는 사용자가 C#에 익숙하고 PDF 조작에 익숙하다고 가정합니다.
4. 라이센스: 제한을 피하기 위해 유효한 라이센스를 적용해야 합니다. 임시 라이센스는 다음에서 얻을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).

## 패키지 가져오기

Aspose.PDF for .NET을 사용하려면 프로젝트에 필요한 네임스페이스를 가져와야 합니다. 방법은 다음과 같습니다.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
using System.Collections;
```

 이 두 네임스페이스는 필수적입니다.`Aspose.Pdf` PDF 문서 작업을 할 수 있습니다.`System.Collections` JavaScript 키를 처리하는 데 사용됩니다.

PDF에 JavaScript를 추가하고 제거하는 전체 과정을 쉽게 따라할 수 있는 단계로 나누어 보겠습니다.

## 1단계: 새 PDF 문서 초기화

가장 먼저 해야 할 일은 새 PDF 문서를 만드는 것입니다. 이 문서는 JavaScript를 추가하기 위한 빈 캔버스 역할을 할 것입니다.

```csharp
Document doc = new Document();
doc.Pages.Add();
```

 여기서 우리는 새로운 것을 초기화하고 있습니다`Document` 객체를 만들고 빈 페이지를 추가합니다. 이것을 PDF의 기초로 생각하세요.

## 2단계: PDF에 JavaScript 추가

이제 문서가 있으니 JavaScript를 추가할 차례입니다. PDF의 JavaScript는 알림이나 양식 검증과 같은 사용자 지정 동작을 추가하는 데 사용할 수 있습니다.

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
```

이 코드 조각에서는 두 개의 JavaScript 함수를 추가합니다.`func1` 그리고`func2` ) PDF로. 이러한 기능은 필요에 따라 다양한 작업을 수행할 수 있습니다. 여기서는 플레이스홀더 함수인`hello()`.

## 3단계: JavaScript로 PDF 저장

원하는 JavaScript를 추가한 후에는 PDF를 저장할 시간입니다.

```csharp
doc.Save(dataDir + "AddJavascript.pdf");
```

 이렇게 하면 JavaScript를 사용하여 문서가 다음 이름으로 저장됩니다.`AddJavascript.pdf` 지정된 디렉토리에서 (`dataDir`).

## 4단계: 기존 PDF에서 JavaScript 로드 및 보기

기존 PDF 내의 JavaScript 기능을 확인하거나 수정해야 한다고 가정해 보겠습니다. 첫 번째 단계는 PDF 파일을 로드하고 JavaScript 키에 액세스하는 것입니다.

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
```

 기존 것을 로딩 중입니다`AddJavascript.pdf` 그리고 JavaScript 키를 목록에 저장합니다.`Keys` 속성은 문서에 첨부된 모든 JavaScript 함수의 이름을 반환합니다.

## 5단계: JavaScript 함수 표시

다음으로, JavaScript 함수를 반복하여 문서에서 어떤 기능을 사용할 수 있는지 살펴보겠습니다.

```csharp
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}
```

이렇게 하면 각 JavaScript 함수 이름과 해당 코드가 콘솔에 출력됩니다. 현재 문서에 어떤 함수가 있는지 확인하고 싶을 때 유용합니다.

## 6단계: PDF에서 JavaScript 제거

 이제 특정 JavaScript 함수를 제거하고 싶다고 가정해 보겠습니다.`func1`. 이를 수행하는 방법은 다음과 같습니다.

```csharp
doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
```

 그만큼`Remove` 이 메서드는 JavaScript 함수의 이름을 인수로 받아서 문서에서 삭제합니다.

## 7단계: JavaScript 제거 확인

 JavaScript를 제거한 후 나머지 기능을 다시 인쇄하여 확인할 수 있습니다.`func1` 성공적으로 삭제되었습니다.

```csharp
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}
Console.WriteLine("Javascript added/removed successfully.");
```

코드의 마지막 부분은 모든 것이 제자리에 있고 JavaScript 함수가 올바르게 업데이트되었는지 확인합니다.

## 결론

축하합니다! 방금 Aspose.PDF for .NET을 사용하여 PDF 문서에서 JavaScript를 추가하고 제거하는 방법을 배웠습니다. 이 강력한 기능은 동적 메시지 추가에서 사용자 정의 계산 또는 검증 수행에 이르기까지 다양한 작업에 활용할 수 있습니다. PDF 내에서 JavaScript를 조작하면 사용자 경험을 크게 향상시킬 수 있습니다.

## 자주 묻는 질문

### 하나의 PDF에 여러 개의 JavaScript 기능을 추가할 수 있나요?
 물론입니다! 다음을 사용하여 필요한 만큼 많은 JavaScript 함수를 추가할 수 있습니다.`doc.JavaScript` 수집.

### 존재하지 않는 JavaScript 함수를 제거하려고 하면 어떻게 되나요?
 해당 기능이 존재하지 않으면`Remove` 이 방법은 오류를 발생시키지는 않지만, 아무것도 제거하지도 않습니다.

### PDF를 여는 즉시 JavaScript를 실행할 수 있나요?
네! JavaScript를 구성하여 문서를 열거나 버튼을 클릭하는 등 특정 트리거에서 실행되도록 할 수 있습니다.

### PDF에 JavaScript를 추가한 후에 편집할 수 있나요?
네, 기존 PDF를 로드하고, JavaScript에 액세스하고, 코드를 수정한 다음 문서를 다시 저장할 수 있습니다.

### JavaScript를 제거하면 나머지 PDF 콘텐츠에 영향을 미칩니까?
아니요, JavaScript를 제거하면 스크립트에만 영향을 미칩니다. PDF의 내용은 변경되지 않습니다.