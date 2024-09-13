---
title: PDF 파일의 숨겨진 텍스트 블록
linktitle: PDF 파일의 숨겨진 텍스트 블록
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에서 숨겨진 텍스트 블록을 만드는 방법을 알아보세요.
type: docs
weight: 230
url: /ko/net/programming-with-text/hidden-text-block/
---
이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 파일에 숨겨진 텍스트 블록을 만드는 방법을 설명합니다. 숨겨진 텍스트 블록은 마우스 커서가 특정 영역 위로 이동하면 표시되는 떠다니는 텍스트입니다. 제공된 C# 소스 코드를 사용하여 숨겨진 텍스트 블록을 만드는 단계별 프로세스를 살펴보겠습니다.

## 요구 사항

시작하기 전에 다음 사항이 있는지 확인하세요.

- .NET 라이브러리용 Aspose.PDF가 설치되었습니다.
- C# 프로그래밍에 대한 기본적인 이해.

## 1단계: 문서 디렉토리 설정

 먼저 생성된 PDF 파일을 저장할 디렉토리 경로를 설정해야 합니다. 바꾸기`"YOUR DOCUMENT DIRECTORY"` 에서`dataDir` 원하는 디렉토리의 경로를 담은 변수입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 샘플 문서 만들기

이 단계에서는 샘플 PDF 문서를 만들고 텍스트 조각을 추가합니다. 텍스트 조각은 숨겨진 텍스트 블록을 표시하는 트리거 역할을 합니다.

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## 3단계: 문서 열기

 이제 이전에 만든 문서를 다음을 사용하여 엽니다.`Document` 수업.

```csharp
Document document = new Document(outputFile);
```

## 4단계: 텍스트 조각 찾기

 우리는 ~을 사용합니다`TextFragmentAbsorber`숨겨진 텍스트 블록의 표시를 트리거할 텍스트 조각을 찾기 위한 객체입니다. 이 경우, 우리는 정확한 텍스트 "여기로 마우스 커서를 이동하여 떠다니는 텍스트를 표시합니다"를 검색합니다.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## 5단계: 숨겨진 텍스트 필드 만들기

 우리는 만듭니다`TextBoxField` 숨겨진 텍스트 필드를 나타내는 개체입니다. 이 필드에는 마우스 커서가 트리거 텍스트 위에 있을 때 표시되는 텍스트가 포함됩니다.

```csharp
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
floatingField.Value = "This is the \"floating text field\".";
floatingField. ReadOnly = true;
floatingField.Flags |= AnnotationFlags.Hidden;
floatingField.PartialName = "FloatingField_1";
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField. Multiline = true;
```

## 6단계: 문서에 숨겨진 텍스트 필드 추가

숨겨진 텍스트 필드를 문서의 양식 컬렉션에 추가합니다.

```csharp
document.Form.Add(floatingField);
```

## 7단계: 보이지 않는 버튼 만들기

트리거 텍스트 조각 위에 배치될 보이지 않는 버튼 필드를 만듭니다. 이 버튼 필드에는 마우스 진입 및 종료 이벤트와 관련된 동작이 있습니다.

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## 8단계: 문서 저장

마지막으로 숨겨진 텍스트 블록과 함께 수정된 문서를 저장합니다.

```csharp
document. Save(outputFile);
```

### .NET용 Aspose.PDF를 사용한 숨겨진 텍스트 블록에 대한 샘플 소스 코드 
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// 텍스트로 샘플 문서 만들기
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// 텍스트가 있는 문서 열기
Document document = new Document(outputFile);
//정규 표현식과 일치하는 모든 구문을 찾기 위해 TextAbsorber 객체를 생성합니다.
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// 문서 페이지에 대한 흡수체를 수락합니다.
document.Pages.Accept(absorber);
// 첫 번째 추출된 텍스트 조각을 가져옵니다.
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
//페이지의 지정된 사각형에 떠 있는 텍스트를 위한 숨겨진 텍스트 필드를 만듭니다.
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// 필드 값으로 표시할 텍스트를 설정합니다.
floatingField.Value = "This is the \"floating text field\".";
// 이 시나리오에서는 필드를 '읽기 전용'으로 만드는 것이 좋습니다.
floatingField.ReadOnly = true;
// 문서를 열 때 필드가 표시되지 않도록 '숨김' 플래그를 설정합니다.
floatingField.Flags |= AnnotationFlags.Hidden;
// 고유한 필드 이름을 설정하는 것은 필수는 아니지만 허용됩니다.
floatingField.PartialName = "FloatingField_1";
// 필드 외관의 특성을 설정하는 것은 필수는 아니지만 더 좋게 만듭니다.
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// 문서에 텍스트 필드 추가
document.Form.Add(floatingField);
// 텍스트 조각 위치에 보이지 않는 버튼 만들기
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// 지정된 필드(주석)와 숨기기 플래그에 대한 새로운 숨기기 작업을 만듭니다.
// (위에 지정한 경우 이름으로 부동 필드를 참조할 수도 있습니다.)
// 보이지 않는 버튼 필드에 마우스 진입/종료 시 동작 추가
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// 문서에 버튼 필드 추가
document.Form.Add(buttonField);
// 문서 저장
document.Save(outputFile);
```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET 라이브러리를 사용하여 숨겨진 텍스트 블록을 만드는 방법을 알아보았습니다. 단계별 가이드를 따르면 마우스 커서가 특정 영역 위로 이동하면 표시되는 숨겨진 텍스트 필드가 있는 PDF 문서를 생성할 수 있습니다. 요구 사항에 따라 숨겨진 텍스트 블록의 모양과 동작을 사용자 지정할 수 있습니다.

### 자주 묻는 질문

#### 질문: "PDF 파일의 숨겨진 텍스트 블록" 튜토리얼의 목적은 무엇인가요?

A: "PDF 파일에서 숨겨진 텍스트 블록" 튜토리얼은 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 파일에서 숨겨진 텍스트 블록을 만드는 방법을 설명합니다. 숨겨진 텍스트 블록은 마우스 커서가 특정 영역 위로 이동하면 표시되는 떠다니는 텍스트입니다. 이 튜토리얼은 C# 소스 코드를 사용하여 단계별 가이드를 제공합니다.

#### 질문: PDF 파일에 숨겨진 텍스트 블록을 만들어야 하는 이유는 무엇인가요?

답변: 숨겨진 텍스트 블록을 만드는 기능은 사용자가 마우스 커서를 지정된 영역 위에 올려놓았을 때만 표시되는 추가 정보나 컨텍스트를 제공하려는 대화형 PDF 문서에 유용할 수 있습니다.

#### 질문: 문서 디렉토리를 어떻게 설정하나요?

A: 문서 디렉토리를 설정하려면:

1.  바꾸다`"YOUR DOCUMENT DIRECTORY"` 에서`dataDir` 생성된 PDF 파일을 저장할 디렉토리 경로가 있는 변수입니다.

#### 질문: 샘플 문서를 만들고 텍스트 조각을 추가하려면 어떻게 해야 하나요?

 A: 튜토리얼에서는 다음을 사용합니다.`Document` 샘플 PDF 문서를 만들고 텍스트 조각을 추가하는 클래스입니다. 이 텍스트 조각은 숨겨진 텍스트 블록을 표시하는 트리거 역할을 합니다.

#### 질문: 숨겨진 텍스트 블록을 트리거하는 텍스트 조각을 어떻게 찾을 수 있나요?

 A: 튜토리얼에서는 다음을 사용하는 방법을 보여줍니다.`TextFragmentAbsorber` 숨겨진 텍스트 블록의 표시를 트리거하는 텍스트 조각을 찾는 객체입니다. PDF 문서 내에서 특정 텍스트 문자열을 검색합니다.

#### 질문: 숨겨진 텍스트 필드를 어떻게 만들고 사용자 지정하나요?

 A: 당신이 만듭니다`TextBoxField`숨겨진 텍스트 필드를 나타내는 객체입니다. 이 튜토리얼은 숨겨진 텍스트 필드의 위치, 값, 모양 및 동작과 같은 다양한 속성을 설정하는 코드를 제공합니다.

#### 질문: 숨겨진 텍스트 블록과 연관된 보이지 않는 버튼을 어떻게 만듭니까?

 A: 보이지 않는 버튼 필드는 다음을 사용하여 생성됩니다.`ButtonField` 클래스. 이 버튼 필드는 트리거 텍스트 조각 위에 위치하며 마우스 진입 및 종료 이벤트와 관련된 동작을 갖습니다. 이러한 동작은 숨겨진 텍스트 블록의 가시성을 제어합니다.

#### 질문: 숨겨진 텍스트 블록과 트리거 영역의 모양을 사용자 지정할 수 있나요?

대답: 네, 숨겨진 텍스트 필드와 보이지 않는 버튼 모두의 글꼴, 색상, 크기, 위치 등 다양한 속성을 사용자 정의할 수 있습니다.

#### 질문: 숨겨진 텍스트 블록이 포함된 수정된 문서를 저장하려면 어떻게 해야 하나요?

 A: 이 튜토리얼에서는 수정된 문서를 저장하는 방법을 보여줍니다.`Save` 의 방법`Document` 수업.