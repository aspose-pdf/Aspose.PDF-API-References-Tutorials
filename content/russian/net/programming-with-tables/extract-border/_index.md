---
title: Извлечь границу в файл PDF
linktitle: Извлечь границу в файл PDF
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как извлечь границы из файла PDF и сохранить их как изображение с помощью Aspose.PDF для .NET. Пошаговое руководство с примерами кода и советами для успеха.
type: docs
weight: 80
url: /ru/net/programming-with-tables/extract-border/
---
## Введение

При работе с PDF-файлами извлечение определенных элементов, таких как границы или графические пути, может показаться сложной задачей. Но с Aspose.PDF для .NET вы можете легко извлекать границы или фигуры из файла PDF и сохранять их как изображение. В этом уроке мы погрузимся в процесс извлечения границы из PDF-файла и сохранения его как изображения PNG. Приготовьтесь взять под контроль графическое содержимое вашего PDF-файла!

## Предпосылки

Прежде чем погрузиться в код, убедитесь, что у вас все настроено:

1.  Aspose.PDF для .NET: Если вы еще не установили библиотеку Aspose.PDF, вы можете[скачать здесь](https://releases.aspose.com/pdf/net/). Вам также необходимо будет применить лицензию, либо через бесплатную пробную версию, либо через приобретенную лицензию.
2. Настройка IDE: Настройте проект C# в Visual Studio или любой другой .NET IDE. Убедитесь, что вы добавили необходимые ссылки в библиотеку Aspose.PDF.
3. Входной PDF-файл: Имейте готовый PDF-файл, из которого вы будете извлекать границы. Этот урок будет ссылаться на файл с именем`input.pdf`.

## Импорт необходимых пакетов

Давайте начнем с импорта требуемых пространств имен. Эти пакеты предоставляют инструменты, необходимые для управления содержимым PDF.

```csharp
using System.IO;
using System;
using System.Drawing.Drawing2D;
using System.Drawing.Imaging;
using System.Collections;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

Теперь, когда мы изучили основы, давайте перейдем к пошаговому руководству, в котором мы подробно разберем каждую часть кода.


## Шаг 1: Загрузка PDF-документа

Первый шаг — загрузить PDF-документ, содержащий границу, которую вы хотите извлечь. Представьте, что вы открываете книгу, прежде чем начать читать — вам нужен доступ к ее содержанию!

 Начнем с указания каталога, в котором хранится ваш PDF-файл, и загрузим документ с помощью`Aspose.Pdf.Document` сорт.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

 Этот код загружает`input.pdf` файл из указанного вами каталога. Убедитесь, что путь к файлу правильный, иначе вы можете получить ошибку «файл не найден».

## Шаг 2: Настройка графики и растрового изображения

Прежде чем начать извлечение, нам нужно создать холст для рисования. В мире .NET это означает настройку объектов Bitmap и Graphics. Bitmap представляет изображение, а объект Graphics позволит нам рисовать фигуры, такие как границы, извлеченные из PDF.

```csharp
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);
```

Вот краткий обзор:
- Мы создаем растровое изображение размером с первую страницу PDF-файла.
- GraphicsPath используется для определения фигур (в данном случае границ).
- Матрица определяет, как будет преобразована графика; нам нужна матрица инверсии, поскольку PDF и .NET имеют разные системы координат.

## Шаг 3: Обработка содержимого PDF-файла


Файл PDF представляет собой серию команд рисования, и нам необходимо обработать каждую из этих команд, чтобы определить и извлечь информацию о границах.

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    // Обработка команд, таких как сохранение/восстановление состояния, рисование линий, заполнение фигур и т. д.
}
```

Код проходит через каждый оператор рисования в потоке содержимого PDF. Каждый оператор может представлять линию, прямоугольник или другую графическую инструкцию.

## Шаг 4: Обработка операторов PDF

Каждый оператор в файле PDF управляет действием. Чтобы извлечь границу, нам нужно определить такие команды, как «переместить в», «линия в» и «нарисовать прямоугольник». Следующие операторы обрабатывают эти действия:

- MoveTo: перемещает курсор в начальную точку.
- LineTo: рисует линию от текущей точки до новой точки.
- Re: Рисует прямоугольник (может быть частью границы).

```csharp
Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;

if (opMoveTo != null)
{
    lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
    System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
    graphicsPath.AddLine(lastPoint, linePoint);
    lastPoint = linePoint;
}
else if (opRe != null)
{
    System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
    graphicsPath.AddRectangle(re);
}
```

На этом этапе:
- Мы фиксируем точки для каждой нарисованной линии или фигуры.
- Для прямоугольников (`opRe` ), мы добавляем их непосредственно в`graphicsPath`, который мы позже используем для рисования границы.

## Шаг 5: Рисование границы

После того, как мы определили линии и прямоугольники, которые формируют границу, нам нужно фактически нарисовать их на объекте Bitmap. Вот тут-то и вступает в дело объект Graphics.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
    gr.SmoothingMode = SmoothingMode.HighQuality;
    gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
}
```

- Мы создаем графический объект на основе растрового изображения.
- SmoothingMode.HighQuality гарантирует, что мы получим красивое плавное изображение.
- Наконец, мы используем DrawPath для рисования границы.

## Шаг 6: Сохранение извлеченной границы

Теперь, когда мы извлекли границу, пришло время сохранить ее как файл изображения. Это сохранит границу как PNG.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

- Растровое изображение сохраняется как изображение PNG.
- Теперь вы можете открыть это изображение, чтобы увидеть извлеченную границу.

## Заключение

Извлечение границ из файла PDF с помощью Aspose.PDF для .NET может показаться сложным на первый взгляд, но как только вы разберетесь, все станет просто. Понимая операторы рисования в PDF и используя мощные библиотеки .NET, вы сможете эффективно манипулировать и извлекать графический контент. Это руководство дает вам надежную основу для начала работы с манипуляциями PDF!

## Часто задаваемые вопросы

### Как работать с несколькими страницами в PDF-файле?  
 Вы можете просмотреть каждую страницу документа, выполнив итерацию`doc.Pages` вместо жесткого кодирования`doc.Pages[1]`.

### Могу ли я извлечь другие элементы, например текст, используя тот же подход?  
Да, Aspose.PDF предоставляет богатые API для извлечения текста, изображений и другого контента из PDF-файлов.

### Как применить лицензию, чтобы избежать ограничений?  
 Ты можешь[применить лицензию](https://purchase.aspose.com/temporary-license/) загрузив его через`License` класс предоставлен Aspose.

### Что делать, если у моего PDF-файла нет границ?  
Если ваш PDF не содержит видимых границ, процесс извлечения графики может не дать никакого результата. Убедитесь, что содержимое PDF включает в себя прорисовываемые границы.

### Могу ли я сохранить вывод в форматах, отличных от PNG?  
 Да, просто измените`ImageFormat.Png` в другой поддерживаемый формат, такой как`ImageFormat.Jpeg`.