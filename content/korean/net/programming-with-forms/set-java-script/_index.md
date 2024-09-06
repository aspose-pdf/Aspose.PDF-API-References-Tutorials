---
title: 자바 스크립트 설정
linktitle: 자바 스크립트 설정
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일의 양식 필드에 JavaScript를 설정하는 방법을 알아보세요.
type: docs
weight: 270
url: /ko/net/programming-with-forms/set-java-script/
---
이 가이드에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서의 폼 필드에서 JavaScript를 정의하는 방법을 단계별로 설명합니다. 텍스트 필드에서 특정 작업을 수행하도록 JavaScript 동작을 구성하는 방법을 보여드리겠습니다.

## 필수 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

- 시스템에 .NET 개발 환경이 설치되어 있습니다.
- .NET용 Aspose.PDF 라이브러리. Aspose 공식 웹사이트에서 다운로드할 수 있습니다.

## 1단계: 문서 디렉토리 구성

 첫 번째 단계는 작업하려는 PDF 파일이 있는 문서 디렉토리를 구성하는 것입니다. 다음을 사용할 수 있습니다.`dataDir` 디렉토리 경로를 지정하는 변수입니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 반드시 교체하세요`"YOUR DOCUMENTS DIRECTORY"` 문서 디렉토리의 실제 경로를 포함합니다.

## 2단계: 입력 PDF 파일 로드

 이 단계에서는 다음을 사용하여 입력 PDF 파일을 로드합니다.`Document` Aspose 클래스.PDF.

```csharp
// 입력 PDF 파일 로드
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

입력 PDF 파일이 지정된 문서 디렉토리에 있는지 확인하세요.

## 3단계: TextBox 필드 액세스

 특정 텍스트 필드에 JavaScript를 적용하려면 먼저 해당 필드에 액세스해야 합니다. 이 예에서 텍스트 필드가 "textbox1"이라고 가정합니다. 다음을 사용합니다.`doc.Form["textbox1"]` 해당되는 것을 얻는 방법`TextBoxField` 물체.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

지정된 텍스트 필드가 입력 PDF 파일에 있는지 확인하세요.

## 4단계: JavaScript 작업 구성

 이제 텍스트 필드에 액세스했으므로 이 필드와 관련된 JavaScript 동작을 구성할 수 있습니다. 이 예에서는 두 가지 동작을 사용합니다.`OnModifyCharacter` 그리고`OnFormat` . 이러한 작업은 다음을 사용하여 정의됩니다.`JavascriptAction` 사물.

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

귀하의 요구 사항에 맞게 JavaScript 동작을 사용자 정의하세요.

## 5단계: 초기 필드 값 설정

결과 PDF를 저장하기 전에 텍스트 필드에 대한 초기 값을 설정할 수 있습니다. 이 예에서 필드에 대한 값 "123"을 설정합니다.

```csharp
field.Value = "123";
```

귀하의 요구 사항에 맞게 이 값을 사용자 정의하세요.

## 6단계: 결과 PDF 저장

 이제 텍스트 필드와 JavaScript 작업 설정이 완료되었으므로 다음을 사용하여 결과 PDF를 저장할 수 있습니다.`Save` 의 방법`Document` 수업.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// 결과 PDF 저장
doc.Save(dataDir);
```

생성된 PDF의 전체 경로와 파일 이름을 지정하세요.


### .NET용 Aspose.PDF를 사용하여 Java Script를 설정하기 위한 샘플 소스 코드 
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 입력 PDF 파일 로드
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
// 점 뒤 2자리
// 구분자 없음
// Neg 스타일 = 마이너스
// 화폐 없음
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
// 초기 필드 값 설정
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
// 결과 PDF 저장
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## 결론

이 가이드에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서의 폼 필드에 JavaScript를 설정하는 방법을 알아보았습니다. 설명된 단계를 따르면 텍스트 필드에서 다양한 작업을 수행하도록 JavaScript 동작을 사용자 지정할 수 있습니다. .NET용 Aspose.PDF의 기능을 더 탐색하여 PDF 파일을 조작할 가능성을 확장하세요.


### 자주 묻는 질문

#### 질문: Aspose.PDF for .NET을 사용하여 체크박스, 라디오 버튼 등의 다른 폼 요소에 JavaScript를 추가할 수 있나요?

 A: 네, Aspose.PDF for .NET을 사용하면 체크박스, 라디오 버튼, 드롭다운 목록을 포함한 다양한 폼 요소에 JavaScript를 추가할 수 있습니다. 다음을 사용할 수 있습니다.`JavascriptAction` 다양한 폼 요소에 대한 JavaScript 동작을 정의하는 클래스입니다.

#### 질문: JavaScript를 사용하여 양식 필드에서 사용자 입력의 유효성을 검사할 수 있나요?

 A: 네, JavaScript를 사용하여 양식 필드에서 사용자 입력을 검증할 수 있습니다. 다음과 같은 JavaScript 동작을 정의하여`OnBlur` 또는`OnKeystroke` 양식 필드의 경우, 입력된 데이터의 유효성을 검사하고 필요한 경우 오류 메시지를 표시할 수 있습니다.

#### 질문: Aspose.PDF for .NET을 사용하여 복잡한 JavaScript 함수를 실행할 수 있나요?

 A: 네, Aspose.PDF for .NET을 사용하여 복잡한 JavaScript 함수를 실행할 수 있습니다. 사용자 정의 JavaScript 함수를 정의하고 이를 호출할 수 있는 유연성이 있습니다.`JavascriptAction`.

#### 질문: .NET용 Aspose.PDF는 이 튜토리얼에서 언급한 것 외의 JavaScript 이벤트를 지원합니까?

 A: 예, Aspose.PDF for .NET은 다음을 포함한 광범위한 JavaScript 이벤트를 지원합니다.`OnMouseEnter`, `OnMouseExit`, `OnMouseDown` , 그리고`OnMouseUp`, 기타. 이러한 이벤트를 사용하여 사용자 상호작용에 따라 JavaScript 작업을 트리거할 수 있습니다.

#### 질문: Aspose.PDF for .NET을 사용하여 기존 PDF 문서에서 JavaScript 코드를 추출할 수 있나요?

 A: Aspose.PDF for .NET은 기존 PDF 문서에서 JavaScript 코드를 추출하는 기능을 제공합니다. 다음을 사용할 수 있습니다.`JavascriptAction` PDF 양식에서 JavaScript 동작에 액세스하고 분석하기 위한 클래스 및 기타 관련 메서드.