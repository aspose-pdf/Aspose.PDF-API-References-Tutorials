---
title: PDF 파일에서 만료일 설정
linktitle: PDF 파일에서 만료일 설정
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에 만료일을 설정하는 방법을 알아보세요. 이 단계별 가이드로 문서 보안을 강화하세요.
type: docs
weight: 300
url: /ko/net/programming-with-document/setexpirydate/
---
## 소개

오늘날의 디지털 시대에 문서를 관리하고 보호하는 것은 그 어느 때보다 중요합니다. 특정 날짜 이후에 자동으로 액세스할 수 없게 되는 PDF를 보내는 것을 상상해보세요. 마법처럼 들리죠? Aspose.PDF for .NET을 사용하면 PDF 파일의 만료일을 쉽게 설정할 수 있습니다. 이 기능은 특정 기간 이후에 제한해야 하는 민감한 문서에 특히 유용합니다. 이 튜토리얼에서는 PDF 파일에서 만료일을 설정하는 과정을 단계별로 안내합니다. 그러니 코딩 모자를 쓰고 시작해 볼까요!

## 필수 조건

시작하기 전에 꼭 준비해야 할 몇 가지 사항이 있습니다.

1. 개발 환경: .NET 개발 환경이 설정되어 있는지 확인하세요. 이는 Visual Studio 또는 .NET을 지원하는 다른 IDE일 수 있습니다.
2.  .NET용 Aspose.PDF: Aspose.PDF 라이브러리를 설치해야 합니다. 아직 설치하지 않았다면 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/pdf/net/).
3. C#에 대한 기본 지식: 이 튜토리얼은 여러분이 C# 프로그래밍에 대한 기본 지식이 있다고 가정합니다. C#을 처음 접한다면 걱정하지 마세요! 간단하고 직관적으로 설명해 드리겠습니다.

## 패키지 가져오기

Aspose.PDF를 시작하려면 C# 프로젝트에서 필요한 네임스페이스를 가져와야 합니다. 다음과 같이 할 수 있습니다.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

이러한 네임스페이스를 통해 Aspose.PDF에서 PDF 문서 작업에 필요한 핵심 기능에 액세스할 수 있습니다.

## 1단계: 문서 디렉토리 설정

먼저, 문서 디렉토리 경로를 지정해야 합니다. 여기가 출력 PDF가 저장되는 곳입니다. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` PDF 파일을 저장하려는 실제 경로와 함께. 프로그램에 "여기에 내 파일을 보관합니다!"라고 말하는 것과 같습니다.

## 2단계: 문서 개체 인스턴스화

 다음으로, 새 인스턴스를 생성해야 합니다.`Document` 클래스. 여기는 PDF를 만들 캔버스입니다.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

 생각해 보세요`Document` 빈 종이 한 장으로 된 객체입니다. 원하는 대로 내용을 추가할 수 있습니다!

## 3단계: PDF에 페이지 추가

이제 문서가 설정되었으니 페이지를 추가할 차례입니다. 여기에 콘텐츠가 들어갈 것입니다.

```csharp
doc.Pages.Add();
```

방금 PDF에 새 페이지를 만들었습니다. 마치 생각을 적어둘 수 있는 노트북에 새 페이지를 추가하는 것과 같습니다.

## 4단계: 페이지에 텍스트 추가

텍스트를 추가하여 이 페이지를 좀 더 흥미롭게 만들어 보겠습니다. 간단한 "Hello World" 메시지를 추가하겠습니다.

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

이 코드 줄은 PDF의 첫 페이지에 텍스트 조각을 추가합니다. 페이지 맨 위에 제목을 쓰는 것과 같습니다!

## 5단계: 만료 날짜를 위한 JavaScript 만들기

이제 재밌는 부분이 왔습니다! PDF의 만료일을 확인하는 JavaScript 작업을 만듭니다. 현재 날짜가 만료일을 초과하면 사용자에게 경고 메시지가 표시됩니다.

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
```

무슨 일이 일어나고 있는지 알려드리겠습니다.
- 만료 연도와 월을 정의합니다.
- 오늘 날짜를 얻게 됩니다.
- 오늘 날짜와 만료일을 비교합니다.
- 오늘 날짜가 만료일을 지난 경우, 메시지가 나타납니다!

## 6단계: JavaScript를 PDF 열기 동작으로 설정

이제 JavaScript 동작을 PDF 문서의 열기 동작으로 설정해야 합니다. 즉, PDF가 열리면 JavaScript가 실행됩니다.

```csharp
doc.OpenAction = javaScript;
```

이 줄은 PDF에 누군가가 열 때 JavaScript를 실행하라고 알려줍니다. 캘린더를 여는 즉시 울리는 알림을 설정하는 것과 같습니다!

## 7단계: PDF 문서 저장

마지막으로 만료일 기능을 사용하여 PDF 문서를 저장할 시간입니다. 

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
doc.Save(dataDir);
```

이 줄은 PDF를 "SetExpiryDate_out.pdf"라는 이름으로 지정된 디렉토리에 저장합니다. 완성된 아트워크를 프레임에 넣는 것과 같습니다!

## 결론

이제 Aspose.PDF for .NET을 사용하여 만료일이 있는 PDF 파일을 성공적으로 만들었습니다. 이 기능은 보안을 강화할 뿐만 아니라 민감한 정보를 통제할 수 있도록 보장합니다. 계약서, 보고서 또는 기타 중요한 문서를 보내는 경우 만료일을 설정하면 게임 체인저가 될 수 있습니다.

## 자주 묻는 질문

### .NET용 Aspose.PDF란 무엇인가요?
.NET용 Aspose.PDF는 개발자가 .NET 애플리케이션에서 PDF 문서를 만들고, 조작하고, 변환할 수 있는 강력한 라이브러리입니다.

### Aspose.PDF를 무료로 사용할 수 있나요?
 네, Aspose.PDF의 무료 체험판을 사용할 수 있습니다. 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).

### Aspose.PDF를 어떻게 구매하나요?
Aspose.PDF는 다음 사이트에서 구매하실 수 있습니다.[구매 페이지](https://purchase.aspose.com/buy).

### 지원이 필요하면 어떻게 하나요?
질문이 있거나 도움이 필요하면 다음을 방문하세요.[Aspose 지원 포럼](https://forum.aspose.com/c/pdf/10).

### Aspose.PDF에 대한 임시 라이선스를 받을 수 있나요?
 네, 임시 면허를 요청할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).