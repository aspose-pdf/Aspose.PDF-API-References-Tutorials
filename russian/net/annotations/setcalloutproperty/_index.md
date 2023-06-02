---
title: Установить свойство выноски
linktitle: Установить свойство выноски
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как установить свойство выноски с помощью Aspose.PDF для .NET. Настройте аннотации с помощью линий выноски, цвета текста и стилей завершения.
type: docs
weight: 130
url: /ru/net/annotations/setcalloutproperty/
---
 Aspose.PDF для .NET — это мощная библиотека для создания, обработки и преобразования PDF-документов на C#. Одной из функций, предоставляемых этой библиотекой, является возможность устанавливать свойства выноски для аннотаций произвольного текста в документах PDF. Это можно сделать с помощью`FreeTextAnnotation` класс, который позволяет создавать аннотации с выносками.

В этом руководстве мы проведем вас через процесс настройки свойств выноски для произвольной текстовой аннотации с использованием Aspose.PDF для .NET на C#. Чтобы начать, выполните следующие действия.

## Установите Aspose.PDF для .NET

 Если вы еще этого не сделали, вам необходимо[скачать](https://releases.aspose.com/pdf/net/) и установите Aspose.PDF для .NET из Aspose Releases или через диспетчер пакетов NuGet.

## Создайте новый PDF-документ

 Создайте новый документ PDF с помощью`Document` класс, предоставляемый Aspose.PDF для .NET.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Добавить новую страницу в документ

 Добавьте новую страницу в документ с помощью`Pages` коллекция`Document` сорт.

```csharp
Page page = doc.Pages.Add();
```

## Установить внешний вид по умолчанию

 Задайте внешний вид по умолчанию для произвольной текстовой аннотации, создав новый`DefaultAppearance` объект и установка его свойств, таких как`TextColor` и`FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## Создание произвольной текстовой аннотации с выноской

 Создайте новую текстовую аннотацию с выноской, используя`FreeTextAnnotation` сорт. Установить`Intent` собственность на`FreeTextIntent.FreeTextCallout` чтобы указать, что это аннотация выноски. Установить`EndingStyle` собственность на`LineEnding.OpenArrow` чтобы указать стиль стрелки в конце выноски. Установить`Callout` свойство массива`Point` объекты, представляющие точки на странице, где должна быть нарисована линия выноски.

```csharp
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
    new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
```

## Добавьте аннотацию произвольного текста на страницу

 Добавьте аннотацию произвольного текста на страницу с помощью`Annotations` коллекция`Page` сорт.

```csharp
page.Annotations.Add(fta);
```

## Добавьте текст в аннотацию

 Добавьте текст в аннотацию, установив`RichText`свойство в строку форматированного XML. В этом уроке мы устанавливаем красный цвет текста и размер шрифта 9.

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" стиль=\"цвет:#FF
```

## 8. сохранить документ

Теперь сохраните документ, используя следующий код:

```csharp
doc.Save(dataDir + "SetCalloutProperty.pdf")
```

### Пример исходного кода для установки свойства выноски с использованием Aspose.PDF для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
	new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
page.Annotations.Add(fta);
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" стиль=\"цвет:#FF0000;вес шрифта:нормальный;стиль шрифта:нормальный;растяжка шрифта:нормальный\"><p dir=\"ltr\"> <span style=\"font-size:9.0pt;font-family:Helvetica\">Это образец</span></p></body>";
doc.Save(dataDir + "SetCalloutProperty.pdf");
```
