---
title: 자유 텍스트 주석 형식 설정
linktitle: 자유 텍스트 주석 형식 설정
second_title: .NET API 참조용 Aspose.PDF
description: 이 문서에서는 무료 텍스트 주석을 생성하고 .NET용 Aspose.PDF를 사용하여 해당 내용을 지정하는 방법에 대한 단계별 가이드를 제공합니다.
type: docs
weight: 140
url: /ko/net/annotations/setfreetextannotationformatting/
---
Aspose.PDF for .NET은 강력하고 사용하기 쉬운 PDF 문서 조작 API로, .NET 애플리케이션에서 프로그래밍 방식으로 PDF 파일을 작업할 수 있습니다. .NET용 Aspose.PDF가 제공하는 기능 중 하나는 PDF 문서에서 자유 텍스트 주석 형식을 설정하는 기능입니다. 이 기사에서는 .NET용 Aspose.PDF를 사용하여 무료 텍스트 주석 서식을 설정하는 단계별 프로세스를 안내합니다.

## 전제조건

시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.

- 마이크로소프트 비주얼 스튜디오 2010 이상
- .NET용 Aspose.PDF
- C#에 대한 기본 지식



## 1단계: 새 C# 콘솔 애플리케이션 만들기

먼저 Microsoft Visual Studio에서 새 C# 콘솔 애플리케이션을 만듭니다. 새 콘솔 애플리케이션을 생성하려면 메인 메뉴에서 "파일" > "새로 만들기" > "프로젝트" > "Visual C#" > "콘솔 애플리케이션"을 선택하세요.

## 2단계: .NET용 Aspose.PDF에 대한 참조 추가

다음으로 프로젝트에 Aspose.PDF for .NET에 대한 참조를 추가합니다. 이렇게 하려면 "솔루션 탐색기" 창에서 프로젝트를 마우스 오른쪽 버튼으로 클릭하고 "추가" > "참조"를 선택한 다음 Aspose.PDF for .NET DLL 파일을 저장한 위치를 찾습니다. DLL 파일을 선택하고 "확인"을 클릭하여 프로젝트에 참조를 추가합니다.

## 3단계: 환경 설정

Aspose.PDF for .NET에 대한 참조를 추가한 후 환경을 설정해야 합니다. 이렇게 하려면 "dataDir"이라는 새 문자열 변수를 생성하고 PDF 문서가 있는 디렉터리의 경로로 설정하세요. 아래 코드의 "YOUR DOCUMENT DIRECTORY"를 문서 디렉터리의 실제 경로로 바꿉니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 4단계: PDF 문서 열기

환경을 설정한 후에는 다음 코드를 사용하여 PDF 문서를 열 수 있습니다.

```csharp
// 문서 열기
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");
```

"SetFreeTextAnnotationFormatting.pdf"를 PDF 문서의 실제 이름으로 바꾸세요.

## 5단계: 기본 모양 설정

자유 텍스트 주석의 기본 모양을 설정하려면 원하는 글꼴, 글꼴 크기 및 색상을 사용하여 DefaultAppearance 개체를 인스턴스화해야 합니다. 이 튜토리얼에서는 글꼴을 "Arial"로, 글꼴 크기를 28로, 색상을 빨간색으로 설정합니다.

```csharp
// DefaultAppearance 객체 인스턴스화
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
```

## 6단계: 자유 텍스트 주석 생성

이제 기본 모양을 설정했으므로 다음 코드를 사용하여 자유 텍스트 주석을 생성할 수 있습니다.

```csharp
// 주석 만들기
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
```

위 코드는 PDF 문서의 두 번째 페이지에 새로운 자유 텍스트 주석을 생성합니다. 주석은 (200, 400)에 위치하며 너비는 400, 높이는 600입니다.

## 7단계: 주석 내용 지정

자유 텍스트 주석을 생성한 후 다음 코드를 사용하여 주석의 내용을 지정할 수 있습니다.

```csharp
// 주석 내용 지정
freetext.Contents = "Free Text
```

### .NET용 Aspose.PDF를 사용하여 자유 텍스트 주석 서식 설정에 대한 예제 소스 코드
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 열기
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");

// DefaultAppearance 객체 인스턴스화
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
// 주석 만들기
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
// 주석 내용 지정
freetext.Contents = "Free Text";
// 페이지의 주석 컬렉션에 주석 추가
pdfDocument.Pages[1].Annotations.Add(freetext);
dataDir = dataDir + "SetFreeTextAnnotationFormatting_out.pdf";
// 업데이트된 문서 저장
pdfDocument.Save(dataDir);            
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서에서 자유 텍스트 주석 형식을 설정하는 방법을 배웠습니다. 라이브러리는 프로그래밍 방식으로 PDF 문서를 작업할 수 있는 간단하고 효율적인 방법을 제공하므로 개발자는 자유 텍스트 주석을 포함하여 다양한 유형의 주석을 생성하고 사용자 정의할 수 있습니다. 단계별 가이드를 따르고 제공된 C# 소스 코드를 사용하면 쉽게 환경을 설정하고, PDF 문서를 열고, 사용자 지정 형식으로 자유 텍스트 주석을 만들 수 있습니다. .NET용 Aspose.PDF는 PDF 문서 조작 작업을 단순화하는 강력하고 안정적인 API로, PDF 파일로 작업하는 .NET 개발자에게 유용한 도구입니다.

### FAQ

#### Q: PDF 문서의 자유 텍스트 주석이란 무엇입니까?

A: PDF 문서의 자유 텍스트 주석은 특정 위치나 구조에 얽매이지 않고 문서에 텍스트를 추가할 수 있는 일종의 주석입니다. 일반적으로 문서에 주석, 메모 또는 기타 추가 정보를 제공하는 데 사용됩니다.

#### Q: .NET용 Aspose.PDF를 사용하여 자유 텍스트 주석의 모양을 사용자 정의할 수 있습니까?

A: 예, 글꼴, 글꼴 크기, 색상, 위치 등과 같은 자유 텍스트 주석의 다양한 속성을 사용자 정의할 수 있습니다.

#### Q: 자유 텍스트 주석의 내용을 어떻게 지정합니까?

 A: 자유 텍스트 주석의 내용을 지정하려면`Contents` 의 재산`FreeTextAnnotation` 원하는 텍스트에 반대합니다.

#### Q: .NET용 Aspose.PDF를 사용하여 PDF 문서에 여러 개의 무료 텍스트 주석을 추가할 수 있습니까?

 A: 예, 여러 인스턴스를 생성하여 PDF 문서에 여러 개의 자유 텍스트 주석을 생성할 수 있습니다.`FreeTextAnnotation`개체를 문서의 다른 페이지나 위치에 추가합니다.