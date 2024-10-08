---
title: PDF 페이지 크기 가져오기
linktitle: PDF 페이지 크기 가져오기
second_title: .NET API 참조를 위한 Aspose.PDF
description: 이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 페이지 치수를 가져오고 조작을 수행하는 방법을 설명합니다. 자세한 단계를 제공하여 프로세스를 안내합니다.
type: docs
weight: 60
url: /ko/net/programming-with-pdf-pages/get-dimensions/
---
## 소개

PDF 문서의 페이지 크기를 조작해야 했던 적이 있나요? 페이지 크기를 조정하거나 필요에 맞게 회전하고 싶었던 적이 있나요? 그렇다면 올바른 곳에 오셨습니다! 이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 페이지 크기를 검색하고 수정하는 방법을 안내해 드리겠습니다. 초보자이든 노련한 개발자이든 이 가이드는 간단하고 따라하기 쉽습니다.

Aspose.PDF for .NET은 PDF 파일을 손쉽게 만들고, 조작하고, 변환할 수 있는 강력한 라이브러리입니다. PDF를 위한 스위스 군용 칼과 같습니다. 모든 세부 사항을 조정하여 정확한 요구 사항에 맞출 수 있습니다. 그럼, 바로 뛰어들어 이 멋진 도구를 사용하여 PDF 페이지 크기를 가져오고 업데이트하는 방법을 알아보겠습니다!

## 필수 조건

이 튜토리얼을 원활하게 따라가기 위해서는 시작하기 전에 몇 가지가 필요합니다.

1.  .NET용 Aspose.PDF: 다음을 수행할 수 있습니다.[최신 버전을 여기에서 다운로드하세요](https://releases.aspose.com/pdf/net/) . 면허가 없어도 걱정하지 마세요! 면허를 요청할 수 있습니다.[무료 체험](https://releases.aspose.com/) 또는 다음을 선택하십시오.[임시 면허](https://purchase.aspose.com/temporary-license/).
2. Visual Studio: 코드를 작성하고 실행하는 데 사용하는 개발 환경입니다.
3. C#에 대한 기본 지식: 간단하게 설명하겠지만, C#에 대해 어느 정도 알고 있다면 과정이 더 순조로울 것입니다.
4. 작업할 PDF 파일: 샘플 PDF 파일을 가져오거나 새 파일을 만들어 테스트하세요.

## 패키지 가져오기

.NET용 Aspose.PDF를 사용하려면 몇 가지 필수 네임스페이스를 가져와야 합니다. 이렇게 하면 PDF 문서와 상호 작용할 수 있는 단계가 설정됩니다. 방법은 다음과 같습니다.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

이러한 가져오기를 통해 PDF 파일을 조작하는 데 필요한 핵심 클래스에 액세스할 수 있으며, 특히 페이지를 관리하고 크기를 검색할 수 있습니다.

이제 모든 것이 준비되었으니, 그 과정을 쉽게 따라할 수 있는 단계로 나누어 보겠습니다.

## 1단계: 파일 경로 정의 및 문서 로드

첫 번째 단계는 PDF 문서 경로를 지정하고 Aspose.PDF를 사용하여 로드하는 것입니다. 이렇게 하면 PDF 파일의 페이지와 상호 작용할 수 있습니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 열기
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

이 단계에서는 기본적으로 작업하려는 PDF 파일을 엽니다. 특정 페이지에서 책을 열어본 적이 있다면, 이는 매우 유사합니다. 다만 PDF 문서를 열어 페이지에 액세스합니다.

## 2단계: 페이지가 없는 경우 빈 페이지 추가

문서에 페이지가 없다면요? 걱정하지 마세요! 문서에 빈 페이지를 추가하고 작업할 수 있습니다. 페이지가 있는지 확인하고 필요한 경우 새 페이지를 추가하는 방법은 다음과 같습니다.

```csharp
// PDF 문서에 빈 페이지를 추가합니다
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

이 코드 줄은 문서에 이미 페이지가 있는지 확인합니다. 그렇다면 첫 번째 페이지를 선택합니다(`Pages[1]`). 그렇지 않으면 빈 페이지를 만들어 PDF에 추가합니다.

아무것도 없을 때 빈 노트를 펴서 첫 페이지에 글을 쓰는 것과 비슷하다고 생각하시면 됩니다. 쉽죠?

## 3단계: 페이지 높이 및 너비 정보 가져오기

 이제 작업할 페이지가 있으므로 페이지의 크기를 검색해 보겠습니다. 다음을 사용합니다.`GetPageRect()` 높이와 너비를 구하는 방법입니다.

```csharp
// 페이지 높이 및 너비 정보 가져오기
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height.ToString());
```

 여기,`GetPageRect(true)` 페이지의 높이와 너비를 포함하는 사각형을 반환합니다. 자로 종이 한 장을 측정하는 것과 같습니다. 출력은 콘솔에 표시되어 현재 페이지 크기를 알려줍니다.

## 4단계: 페이지를 90도 회전

페이지를 회전하시겠습니까? 문제 없습니다! 간단한 속성으로 페이지를 90도 회전할 수 있습니다.

```csharp
// 페이지를 90도 각도로 회전
page.Rotate = Rotation.on90;
```

이 단계는 페이지를 시계 방향으로 90도 회전합니다. 책상 위에 인쇄된 시트를 뒤집는다고 상상해보세요. 이제 가로 모드입니다!

## 5단계: 회전 후 페이지 크기 다시 확인

페이지를 회전한 후에는 치수를 다시 확인하는 것이 좋습니다. 왜? 회전은 높이와 너비를 해석하는 방식에 영향을 미칠 수 있기 때문입니다.

```csharp
// 페이지 높이 및 너비 정보 가져오기
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height.ToString());
```

이제 페이지 크기는 새로운 방향에 따라 업데이트됩니다. 휴대폰에서 사진을 회전하는 것과 같습니다. 갑자기 너비가 높이가 되고 그 반대도 마찬가지입니다.


## 결론

축하합니다! Aspose.PDF for .NET을 사용하여 PDF 페이지의 크기를 검색하고 수정하는 방법을 성공적으로 배웠습니다. 이제 PDF를 로드하고, 페이지 크기를 확인하고, 필요한 경우 페이지를 회전할 수 있어야 합니다.

PDF를 조작하는 것은 복잡할 필요가 없습니다. Aspose.PDF를 사용하면 몇 가지 단계를 따르고 직관적인 방법을 사용하는 것만큼 간단합니다. 따라서 다음에 PDF 페이지 크기를 처리해야 할 때 정확히 무엇을 해야 할지 알게 될 것입니다!

## 자주 묻는 질문

### 90도 외에 다른 각도로 페이지를 회전할 수 있나요?
 예, Aspose.PDF를 사용하면 페이지를 0, 90, 180 또는 270도 회전할 수 있습니다.`Rotation` 재산.

### PDF에 페이지가 없으면 어떻게 되나요?
 PDF에 페이지가 없으면 다음을 사용하여 빈 페이지를 추가할 수 있습니다.`Pages.Add()` 이 튜토리얼에서 보여준 것과 같은 방법입니다.

### 한 번에 여러 페이지를 조작할 수 있나요?
네, 여러 페이지를 반복하여 크기 조정이나 회전 등의 변환을 모든 페이지에 적용할 수 있습니다.

### 페이지 크기가 PDF 내부의 내용에 영향을 미칩니까?
페이지 크기는 캔버스의 크기만 변경하고, 내용은 변경하지 않습니다. 그러나 크기를 조정하면 페이지에 내용이 표시되는 방식이 변경될 수 있습니다.

### .NET용 Aspose.PDF에 대한 자세한 정보는 어디에서 찾을 수 있나요?
 방문할 수 있습니다[여기 문서](https://reference.aspose.com/pdf/net/) 더욱 자세한 정보와 고급 사용 사례는 여기에서 확인하세요.