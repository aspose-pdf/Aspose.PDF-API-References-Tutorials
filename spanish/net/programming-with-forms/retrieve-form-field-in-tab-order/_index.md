---
title: Recuperar campo de formulario en orden de tabulación
linktitle: Recuperar campo de formulario en orden de tabulación
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a recuperar campos de formulario en orden de tabulación usando Aspose.PDF para .NET.
type: docs
weight: 240
url: /es/net/programming-with-forms/retrieve-form-field-in-tab-order/
---

Al trabajar con documentos PDF en C# usando Aspose.PDF para .NET, es posible que se encuentre con un escenario en el que necesite recuperar campos de formulario en un orden de tabulación específico. Esto puede ser útil cuando desea realizar operaciones en campos de formulario en función de su secuencia de tabulación. En este tutorial, lo guiaremos paso a paso sobre cómo recuperar campos de formulario en orden de tabulación usando Aspose.PDF para .NET.

## Requisitos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

- Visual Studio instalado en su sistema
- Aspose.PDF para la biblioteca .NET instalada

Ahora, profundicemos en los pasos para recuperar campos de formulario en orden de tabulación.

## Paso 1: Configuración del directorio de documentos

Para empezar, debe configurar el directorio de documentos donde se encuentra su documento PDF. Puede hacer esto especificando la ruta al directorio en el`dataDir` variable.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

## Paso 2: Cargar el documento PDF

 En este paso, cargaremos el documento PDF utilizando Aspose.PDF para .NET. El`Document` class proporciona la capacidad de cargar y manipular documentos PDF.

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

 Aquí,`"Test2.pdf"` es el nombre del documento PDF que desea cargar. Asegúrese de que el documento esté presente en el directorio de documentos especificado.

## Paso 3: Recuperar campos de formulario en orden de tabulación

 Para recuperar campos de formulario en orden de tabulación, necesitamos acceder a la`FieldsInTabOrder` propiedad de la`Page` clase. Esta propiedad devuelve una lista de campos de formulario ordenados por su secuencia de tabulación.

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

En el fragmento de código anterior, recuperamos los campos del formulario de la segunda página (`doc.Pages[1]` ) e iterar a través de cada campo para concatenar sus nombres parciales en el`s` variable. Puede modificar este fragmento de código según sus requisitos específicos.

## Paso 4: modificar el orden de tabulación

 Si desea modificar el orden de tabulación de los campos del formulario, puede hacerlo accediendo a la`TabOrder` propiedad de cada campo y asignando un nuevo valor de orden de tabulación. Aquí hay un ejemplo:

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

En el fragmento de código anterior, asignamos nuevos valores de orden de tabulación a tres campos de formulario (`doc.Form[3]`, `doc.Form[1]` , y`doc.Form[2]`). Ajuste los índices de campo y los valores de orden de tabulación de acuerdo con sus requisitos específicos.

## Paso 5: Guardar el documento modificado

 Después de modificar el orden de tabulación de los campos del formulario, debe guardar el documento modificado. Puedes hacer esto usando el`Save` metodo de la`Document` clase.

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

 Aquí,`"39522_out.pdf"` es el nombre del archivo de salida donde se guardará el documento modificado. Especifique el nombre y la ubicación deseados para el archivo de salida.

### Ejemplo de código fuente para Recuperar campo de formulario en orden de tabulación usando Aspose.Words para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Test2.pdf");
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
	s += field.PartialName;
}
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
doc.Save(dataDir + "39522_out.pdf");
Document doc1 = new Document(dataDir + "39522_out.pdf");
s = "";
foreach (Field field in doc1.Pages[1].FieldsInTabOrder)
{
	s += field.PartialName;
}
string index = "";
foreach (Field field in doc1.Form)
{
	index += field.TabOrder;
}
```

## Conclusión

En este tutorial, aprendimos cómo recuperar campos de formulario en orden de tabulación usando Aspose.PDF para .NET. Cubrimos los pasos necesarios para cargar un documento PDF, recuperar campos de formulario en orden de tabulación, modificar el orden de tabulación y guardar el documento modificado. Siguiendo estos pasos, puede trabajar de manera eficiente con campos de formulario y personalizar su secuencia de pestañas según sus requisitos.