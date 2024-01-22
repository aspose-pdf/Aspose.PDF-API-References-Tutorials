---
title: 메모 구조 요소 생성
linktitle: 메모 구조 요소 생성
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 문서에 구조화된 메모 항목을 만드는 단계별 가이드입니다.
type: docs
weight: 30
url: /ko/net/programming-with-tagged-pdf/create-note-structure-element/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에서 노트 구조 요소를 생성하는 방법에 대한 단계별 가이드를 제공합니다. Aspose.PDF는 PDF 문서를 프로그래밍 방식으로 생성, 조작 및 변환할 수 있는 강력한 라이브러리입니다. Aspose.PDF의 표시된 콘텐츠 구조 기능을 사용하면 PDF 문서에 구조화된 메모를 추가할 수 있습니다.

## 전제조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. .NET 프레임워크와 함께 설치된 Visual Studio.
2. .NET용 Aspose.PDF 라이브러리.

## 1단계: 프로젝트 설정

시작하려면 Visual Studio에서 새 프로젝트를 만들고 .NET용 Aspose.PDF 라이브러리에 대한 참조를 추가하세요. Aspose 공식 웹사이트에서 라이브러리를 다운로드하여 컴퓨터에 설치할 수 있습니다.

## 2단계: 필요한 네임스페이스 가져오기

C# 코드 파일에서 Aspose.PDF에서 제공하는 클래스 및 메서드에 액세스하는 데 필요한 네임스페이스를 가져옵니다.

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## 3단계: PDF 문서 작성 및 구조적 요소 기록

다음 코드를 사용하여 PDF 문서를 만들고 노트 구조 요소를 추가하세요.

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample Grade Items");
taggedContent.SetLanguage("fr-FR");

ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);

NoteElement note1 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note1);
note1.SetText("Note with automatically generated ID. ");

NoteElement note2 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note2);
note2.SetText("Note with ID = 'note_002'.");
note2.SetId("note_002");

NoteElement note3 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note3);
note3.SetText("Note with ID = 'note_003'.");
note3.SetId("note_003");
```

이 코드는 빈 PDF 문서를 만들고 구조화된 메모 요소를 단락에 추가합니다. 각 메모는 Aspose.PDF에서 제공하는 방법을 사용하여 생성됩니다.

## 4단계: PDF 문서 저장

PDF 문서를 저장하려면 다음 코드를 사용하십시오.

```csharp
document. Save(outFile);
```

이 코드는 노트 구조 요소가 포함된 PDF 문서를 지정된 파일에 저장합니다.

### .NET용 Aspose.PDF를 사용하여 노트 구조 요소 생성에 대한 샘플 소스 코드 

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
// PDF 문서 만들기
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
// 단락 요소 추가
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
// NoteElement 추가
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
// NoteElement 추가
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
// NoteElement 추가
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
// 예외를 발생시켜야 함 - Aspose.Pdf.Tagged.TaggedException: ID='note_002'인 구조 요소가 이미 존재합니다.
//note3.SetId("note_002");
// 노트 구조 요소에 ClearId()가 사용된 경우 결과 문서가 PDF/UA를 준수하지 않습니다.
//note3.ClearId();
// 태그가 있는 PDF 문서 저장
document.Save(outFile);
// PDF/UA 준수 확인
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서에 노트 구조 요소를 만드는 방법을 배웠습니다. 구조화된 노트 요소를 사용하면 PDF 문서에 구조화된 추가 정보를 추가할 수 있습니다.

### FAQ

#### Q: Aspose.PDF for .NET을 사용하여 PDF 문서에 노트 구조 요소를 생성하는 목적은 무엇입니까?

A: .NET용 Aspose.PDF를 사용하여 PDF 문서에 노트 구조 요소를 생성하면 문서 내용에 구조화된 노트를 추가할 수 있습니다. 이러한 메모는 콘텐츠의 특정 부분에 대한 추가 컨텍스트, 설명 또는 참조를 제공할 수 있습니다.

#### Q: Aspose.PDF 라이브러리는 PDF 문서에서 노트 구조 요소를 생성하는 데 어떻게 도움이 됩니까?

답변: Aspose.PDF for .NET은 PDF 문서를 프로그래밍 방식으로 생성, 조작 및 변환하는 기능을 제공하는 강력한 라이브러리입니다. 이 튜토리얼에서는 라이브러리의 표시된 컨텐츠 구조 기능을 사용하여 PDF 문서 컨텐츠 내에 구조화된 노트 요소를 생성합니다.

#### Q: .NET용 Aspose.PDF를 사용하여 PDF 문서에 노트 구조 요소를 생성하기 위한 전제 조건은 무엇입니까?

A: 시작하기 전에 .NET 프레임워크와 함께 Visual Studio가 설치되어 있고 프로젝트에서 참조되는 .NET용 Aspose.PDF 라이브러리가 있는지 확인하세요.

#### Q: 제공된 C# 코드는 PDF 문서 콘텐츠에 노트 구조 요소를 어떻게 생성합니까?

답변: 코드는 PDF 문서를 생성하고, 노트 구조 요소를 정의하고, 이를 단락에 추가하는 방법을 보여줍니다. 각 노트는 Aspose.PDF에서 제공하는 방법을 사용하여 생성되므로 구조화된 노트를 콘텐츠에 통합할 수 있습니다.

#### Q: 내가 생성한 노트 구조 요소의 내용과 속성을 사용자 정의할 수 있습니까?

A: 예, Aspose.PDF 라이브러리에서 제공하는 방법과 속성을 사용하여 노트 구조 요소의 내용과 속성을 사용자 정의할 수 있습니다. 코드는 메모 요소의 텍스트와 ID를 설정하는 방법을 보여 주지만 필요에 따라 추가로 사용자 정의할 수 있습니다.

#### Q: 노트 구조 요소와 문서 내용 사이의 계층적 관계는 어떻게 설정되나요?

 A: 계층적 관계는 노트 구조 요소를 단락과 같은 다른 구조적 요소의 하위 요소로 추가하여 설정됩니다. 코드에서 메모 요소는 다음을 사용하여 단락 요소에 추가됩니다.`AppendChild` 방법.

#### Q: 노트 구조 요소에 고유 ID를 할당할 수 있나요?

A: 예, 다음을 사용하여 메모 구조 요소에 고유 ID를 할당할 수 있습니다.`SetId` 방법. 이 코드는 메모 요소의 ID를 고유한 값으로 설정하는 방법을 보여줍니다.

#### Q: 메모 구조 요소에 중복 ID를 할당하려고 하면 어떻게 되나요?

A: 메모 구조 요소에 중복된 ID를 할당하려고 하면 예외가 발생합니다. 자습서에 제공된 코드에는 이 시나리오를 설명하는 설명이 포함되어 있습니다.

#### Q: 노트 구조 요소를 생성할 때 PDF/UA 규격을 어떻게 보장할 수 있습니까?

 A: 튜토리얼에 제공된 코드는 다음을 사용하여 PDF/UA 규정 준수를 검증하는 방법을 보여줍니다.`Validate` 방법. PDF/UA 표준에 따라 문서의 유효성을 검사하면 추가된 메모 구조 요소가 접근성 지침을 준수하는지 확인할 수 있습니다.

#### Q: 이 접근 방식을 사용하여 기존 PDF 문서에 노트 구조 요소를 추가할 수 있습니까?

A: 예, 제공된 접근 방식을 수정하여 기존 PDF 문서에 노트 구조 요소를 추가할 수 있습니다. 새 문서를 만드는 대신 Aspose.PDF를 사용하여 기존 문서를 로드한 다음 유사한 단계에 따라 메모 요소를 추가합니다.
