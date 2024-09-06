---
title: Нарисовать XForm на странице
linktitle: Нарисовать XForm на странице
second_title: Справочник по API Aspose.PDF для .NET
description: Пошаговое руководство по рисованию формы XForm на странице PDF с помощью Aspose.PDF для .NET. Добавьте и разместите форму на странице.
type: docs
weight: 10
url: /ru/net/programming-with-operators/draw-xform-on-page/
---
В этом уроке мы предоставим вам пошаговое руководство по рисованию XForm на странице с помощью Aspose.PDF для .NET. Aspose.PDF — это мощная библиотека, которая позволяет вам создавать, изменять и преобразовывать PDF-документы программным способом. Используя операторы, предоставляемые Aspose.PDF, вы можете добавлять и размещать форму XForm на существующей странице PDF.

## Предпосылки

Прежде чем начать, убедитесь, что выполнены следующие предварительные условия:

1. Visual Studio, установленная с .NET Framework.
2. Библиотека Aspose.PDF для .NET.

## Шаг 1: Настройка проекта

Для начала создайте новый проект в Visual Studio и добавьте ссылку на библиотеку Aspose.PDF for .NET. Вы можете скачать библиотеку с официального сайта Aspose и установить ее на свой компьютер.

## Шаг 2: Импортируйте необходимые пространства имен

В файле кода C# импортируйте пространства имен, необходимые для доступа к классам и методам, предоставляемым Aspose.PDF:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## Шаг 3: Установка путей к файлам

Определите пути к файлам для фонового изображения, входного PDF-файла и выходного PDF-файла:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

Обязательно укажите фактические пути к файлам на вашем компьютере.

## Шаг 4: Загрузка входного PDF-файла

Для загрузки входного PDF-файла используйте следующий код:

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// В следующем коде используются операторы GSave/GRestore
// Код использует оператор ContateNateMatrix для позиционирования XForm
// Код использует оператор Do для рисования XForm на странице.
// Операторы GSave/GRestore оборачивают существующее содержимое
//это делается для того, чтобы получить начальное графическое состояние в конце существующего контента
// в противном случае в конце цепочки существующих операторов могут остаться нежелательные преобразования.
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// Добавлен оператор GSave для корректного сброса состояния графики после новых команд.
pageContents. Add(new GSave());

// Создать XForm
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// Установите ширину и высоту изображения
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// Загрузить изображение в поток
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// Добавьте изображение в коллекцию изображений ресурсов XForm.
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// Использование оператора Do: этот оператор рисует изображение
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
// Расположите XForm в точке с координатами x=100 и y=500.
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Нарисуйте XForm с помощью оператора Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// Расположите XForm в точке с координатами x=100 и y=300.
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Нарисуйте XForm с помощью оператора Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// Восстановление состояния графики с помощью GRestore после GSave
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

Обязательно укажите фактические пути к файлам и при необходимости измените номер страницы и положение XForm.

### Пример исходного кода для Draw XForm On Page с использованием Aspose.PDF для .NET
 
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
	// Использование оператора ContateMatrix для позиционирования xForm
	//Использование оператора для рисования xForm на странице
	// Обернуть существующее содержимое с помощью пары операторов GSave/GRestore
	// это нужно для получения начального графического состояния в конце существующего содержимого
	// в противном случае могут остаться некоторые нежелательные преобразования в конце существующей цепочки операторов.
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Добавлен оператор сохранения графического состояния для корректной очистки графического состояния после выполнения новых команд.
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// Создать xForm
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// Определите ширину и высоту изображения
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// Загрузить изображение в поток
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	// Добавить изображение в коллекцию изображений ресурсов XForm
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Использование оператора Do: этот оператор рисует изображение
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Поместите форму в координаты x=100 y=500
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Нарисуйте форму с оператором Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Поместите форму в координаты x=100 y=300
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// Нарисуйте форму с оператором Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Восстановите состояние графики с помощью GRestore после GSave
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## Заключение

В этом уроке вы узнали, как нарисовать форму XForm на странице PDF с помощью Aspose.PDF для .NET. Выполнив описанные шаги, вы сможете добавить и разместить форму XForm на существующей странице, тем самым придав большую гибкость вашим документам PDF.

### FAQ по draw XForm на странице

#### В: Что такое XForm в Aspose.PDF?

A: XForm — это повторно используемый графический объект в документе PDF. Он позволяет вам определять и рисовать сложную графику, изображения или текст, которые можно использовать повторно несколько раз на разных страницах.

#### В: Как импортировать необходимые пространства имен для Aspose.PDF?

 A: В вашем файле кода C# используйте`using` директива для импорта требуемых пространств имен для доступа к классам и методам, предоставляемым Aspose.PDF:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### В: Каково назначение операторов GSave и GRestore?

 А:`GSave` и`GRestore` Операторы в Aspose.PDF используются для сохранения и восстановления состояния графики. Они помогают гарантировать, что преобразования и настройки, примененные к одному разделу контента, не повлияют на последующие разделы.

#### В: Как определить XForm с помощью Aspose.PDF?

 A: Чтобы создать XForm, используйте`XForm.CreateNewForm` метод и добавьте его в`Resources.Forms` коллекция определенной страницы. Затем вы можете добавить содержимое в XForm`Contents` свойство.

#### В: Как нарисовать изображение в XForm?

A: Загрузите изображение в поток и добавьте его в`Resources.Images` Коллекция XForm. Используйте`Do` оператор в XForm`Contents` чтобы нарисовать изображение.

#### В: Как разместить XForm на странице PDF?

 A: Чтобы разместить XForm на странице, используйте`ConcatenateMatrix` оператор внутри страницы`Contents`. Отрегулируйте параметры матрицы, чтобы указать перемещение (положение) и масштабирование XForm.

#### В: Могу ли я нарисовать несколько XForms на одной странице?

 A: Да, вы можете нарисовать несколько XForms на одной странице, настроив`ConcatenateMatrix` параметры для позиционирования каждой XForm в разных координатах.

#### В: Могу ли я изменить содержимое XForm после его создания?

 A: Да, вы можете изменить содержимое XForm после создания, добавив в него дополнительные операторы.`Contents` свойство.

#### В: Что произойдет, если я пропущу операторы GSave и GRestore?

A: Пропуск операторов GSave и GRestore может привести к нежелательным преобразованиям или настройкам, применяемым к последующему контенту. Их использование помогает поддерживать чистое графическое состояние.

#### В: Могу ли я повторно использовать XForms на разных страницах PDF-документа?

 A: Да, вы можете повторно использовать XForms на нескольких страницах, добавив один и тот же XForms в`Resources.Forms` коллекция разных страниц.

#### В: Существует ли ограничение на количество XForms, которые я могу создать?

A: Хотя нет строгого ограничения на количество XForms, которые вы можете создать, имейте в виду, что слишком большое количество XForms может повлиять на производительность и использование памяти. Используйте их разумно.

#### В: Могу ли я вращать XForm или применять другие преобразования?

 A: Да, вы можете использовать`ConcatenateMatrix` оператор для применения преобразований, таких как вращение, масштабирование и перемещение, к XForm.
