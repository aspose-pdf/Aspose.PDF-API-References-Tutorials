---
title: Нарисовать XForm на странице
linktitle: Нарисовать XForm на странице
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по рисованию формы XForm на странице PDF с использованием Aspose.PDF для .NET. Добавьте и разместите форму на странице.
type: docs
weight: 10
url: /ru/net/programming-with-operators/draw-xform-on-page/
---
В этом руководстве мы предоставим вам пошаговое руководство по рисованию XForm на странице с помощью Aspose.PDF для .NET. Aspose.PDF — это мощная библиотека, которая позволяет программно создавать, обрабатывать и конвертировать PDF-документы. Используя операторы, предоставляемые Aspose.PDF, вы можете добавить и разместить форму XForm на существующей странице PDF.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующие предварительные условия:

1. Visual Studio установлена с .NET framework.
2. Библиотека Aspose.PDF для .NET.

## Шаг 1: Настройка проекта

Для начала создайте новый проект в Visual Studio и добавьте ссылку на библиотеку Aspose.PDF для .NET. Вы можете загрузить библиотеку с официального сайта Aspose и установить ее на свой компьютер.

## Шаг 2. Импортируйте необходимые пространства имен

В файле кода C# импортируйте пространства имен, необходимые для доступа к классам и методам, предоставляемым Aspose.PDF:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## Шаг 3: Установка путей к файлам

Определите пути к файлам для фонового изображения, входного файла PDF и выходного файла PDF:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

Обязательно укажите фактические пути к файлам на вашем компьютере.

## Шаг 4: Загрузка входного PDF-файла

Используйте следующий код для загрузки входного PDF-файла:

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// В следующем коде используются операторы GSave/GRestore.
// В коде используется оператор ContatenateMatrix для позиционирования XForm.
// Код использует оператор Do для рисования XForm на странице.
// Операторы GSave/GRestore оборачивают существующий контент
// это делается для получения начального состояния графики в конце существующего контента
// иначе в конце цепочки существующих операторов могут остаться нежелательные преобразования
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// Добавлен оператор GSave для правильного сброса состояния графики после новых команд.
pageContents. Add(new GSave());

// Создайте X-форму
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// Установите ширину и высоту изображения
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// Загрузите изображение в поток
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// Добавьте изображение в коллекцию изображений ресурсов XForm.
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// Использование оператора Do: этот оператор рисует изображение
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
//Поместите XForm в координаты x=100 и y=500.
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Нарисуйте XForm с помощью оператора Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// Поместите XForm в координаты x=100 и y=300.
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Нарисуйте XForm с помощью оператора Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// Восстановить состояние графики с помощью GRestore после GSave
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

Обязательно укажите фактические пути к файлам и при необходимости измените номер страницы и позиции XForm.

### Пример исходного кода для рисования XForm на странице с использованием Aspose.PDF для .NET
 
```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	// Образец демонстрирует
	// Использование операторов GSave/GRestore
	// Использование оператора ContatenateMatrix для позиционирования xForm
	// Используйте оператор для рисования xForm на странице
	// Оберните существующее содержимое парой операторов GSave/GRestore
	// это для получения начального состояния графики в и существующего содержимого
	// в противном случае в конце существующей цепочки операторов могут остаться некоторые нежелательные преобразования.
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Добавлен оператор сохранения состояния графики, чтобы правильно очищать состояние графики после новых команд.
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// Создать xForm
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// Определить ширину и высоту изображения
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// Загрузить изображение в поток
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	//Добавьте изображение в коллекцию изображений ресурсов XForm.
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Использование оператора Do: этот оператор рисует изображение
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Поместите форму в координаты x=100 y=500
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Нарисуйте форму с помощью оператора Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Поместите форму в координаты x=100 y=300
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// Нарисуйте форму с помощью оператора Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Восстановите состояние графики с помощью GRestore после GSave.
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## Заключение

В этом руководстве вы узнали, как нарисовать форму XForm на странице PDF с помощью Aspose.PDF для .NET. Следуя описанным шагам, вы сможете добавить и расположить форму XForm на существующей странице, что сделает ваши документы PDF более гибкими.

### Часто задаваемые вопросы по Draw XForm на странице

#### В: Что такое XForm в Aspose.PDF?

О: XForm — это многократно используемый графический объект в документе PDF. Он позволяет вам определять и рисовать сложную графику, изображения или текст, которые можно повторно использовать несколько раз на разных страницах.

#### В: Как мне импортировать необходимые пространства имен для Aspose.PDF?

 A: В вашем файле кода C# используйте`using` директива для импорта необходимых пространств имен для доступа к классам и методам, предоставляемым Aspose.PDF:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### В: Каково назначение операторов GSave и GRestore?

 А:`GSave` и`GRestore`операторы в Aspose.PDF используются для сохранения и восстановления состояния графики. Они помогают гарантировать, что преобразования и настройки, примененные к одному разделу содержимого, не повлияют на последующие разделы.

#### В: Как определить XForm с помощью Aspose.PDF?

 A: Чтобы создать XForm, используйте`XForm.CreateNewForm` метод и добавить его в`Resources.Forms` коллекция конкретной страницы. Затем вы можете добавить содержимое в форму XForm.`Contents` свойство.

#### Q: Как я могу нарисовать изображение в XForm?

 A: Загрузите изображение в поток и добавьте его в`Resources.Images` коллекция XForm. Использовать`Do` оператор в XForm`Contents` нарисовать изображение.

#### В: Как расположить XForm на странице PDF?

 A: Чтобы расположить XForm на странице, используйте`ConcatenateMatrix` оператор на странице`Contents`. Настройте параметры матрицы, чтобы указать перевод (положение) и масштабирование XForm.

#### В: Могу ли я рисовать несколько XForms на одной странице?

 О: Да, вы можете нарисовать несколько XForms на одной странице, изменив`ConcatenateMatrix`параметры для размещения каждой формы XForm в разных координатах.

#### Вопрос. Можно ли изменить содержимое формы XForm после ее создания?

 О: Да, вы можете изменить содержимое формы XForm после ее создания, добавив в нее дополнительные операторы.`Contents` свойство.

#### В: Что произойдет, если я пропущу операторы GSave и GRestore?

О: Отсутствие операторов GSave и GRestore может привести к нежелательным преобразованиям или настройкам, применяемым к последующему содержимому. Их использование помогает поддерживать чистоту графики.

#### Вопрос. Можно ли повторно использовать XForms на разных страницах документа PDF?

 О: Да, вы можете повторно использовать формы XForm на нескольких страницах, добавив одну и ту же форму XForm в`Resources.Forms` коллекция различных страниц.

#### В: Есть ли ограничение на количество XForms, которые я могу создать?

О: Хотя строгого ограничения на количество XForms, которые вы можете создать, нет, имейте в виду, что слишком большое количество XForms может повлиять на производительность и использование памяти. Используйте их разумно.

#### В: Можно ли повернуть XForm или применить другие преобразования?

 О: Да, вы можете использовать`ConcatenateMatrix`оператор для применения таких преобразований, как вращение, масштабирование и перемещение к XForm.
