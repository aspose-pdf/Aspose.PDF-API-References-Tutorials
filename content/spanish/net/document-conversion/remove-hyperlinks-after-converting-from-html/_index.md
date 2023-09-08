---
title: Eliminar hipervínculos después de convertir desde HTML
linktitle: Eliminar hipervínculos después de convertir desde HTML
second_title: Aspose.PDF para referencia de API .NET
description: Guía paso a paso para eliminar hipervínculos después de convertir HTML a PDF usando Aspose.PDF para .NET.
type: docs
weight: 250
url: /es/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
En este tutorial, lo guiaremos a través del proceso de eliminar hipervínculos de un archivo PDF generado a partir de un archivo HTML usando Aspose.PDF para .NET. Los hipervínculos son enlaces en los que se puede hacer clic y que pueden redirigir a otras páginas o sitios web. Si sigue los pasos a continuación, podrá eliminar hipervínculos del archivo PDF resultante.

## Requisitos previos
Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada en su sistema.
- Un entorno de desarrollo como Visual Studio.

## Paso 1: cargar el archivo HTML y eliminar hipervínculos
En este paso, cargaremos el archivo HTML y eliminaremos los hipervínculos del documento PDF resultante. Utilice el siguiente código:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue el archivo HTML usando las opciones de carga HTML
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());

// Explorar las anotaciones de la primera página del documento.
foreach(Annotation a in doc.Pages[1].Annotations)
{
     // Compruebe si la anotación es un enlace.
     if (a.AnnotationType == AnnotationType.Link)
     {
         LinkAnnotation the = (LinkAnnotation)a;
        
         // Comprueba si la acción es del tipo GoToURIAction
         if (the.Action is GoToURIAction)
         {
             GoToURIAction gta = (GoToURIAction)the.Action;
             gta.URI = "";
            
             // Utilice un absorbente de fragmentos de texto para encontrar fragmentos de texto coincidentes
             TextFragmentAbsorber tfa = new TextFragmentAbsorber();
             tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
             doc.Pages[a.PageIndex].Accept(tfa);
            
             // Recorra fragmentos de texto coincidentes y elimine atributos de hipervínculos
             foreach(TextFragment tf in tfa.TextFragments)
             {
                 tf.TextState.Underline = false;
                 tf.TextState.ForegroundColor = Color.Black;
             }
         }
        
         // Eliminar la anotación de la página.
         doc.Pages[a.PageIndex].Annotations.Delete(a);
     }
}
```

 Asegúrate de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio real donde se encuentra su archivo HTML.

## Paso 2: guardar el archivo PDF resultante
Finalmente, guardaremos el archivo PDF resultante sin los hipervínculos. Utilice el siguiente código:

```csharp
// Guarde el archivo PDF resultante
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 El código anterior guarda el archivo PDF resultante con el nombre de archivo`"RemoveHyperlinksFromText_out.pdf"`.

### Código fuente de ejemplo para eliminar hipervínculos después de convertir desde HTML usando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
doc.Save(new MemoryStream());
foreach (Annotation a in doc.Pages[1].Annotations)
{
	if (a.AnnotationType == AnnotationType.Link)
	{
		LinkAnnotation la = (LinkAnnotation)a;
		if (la.Action is GoToURIAction)
		{
			GoToURIAction gta = (GoToURIAction)la.Action;
			gta.URI = "";
			TextFragmentAbsorber tfa = new TextFragmentAbsorber();
			tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
			doc.Pages[a.PageIndex].Accept(tfa);
			foreach (TextFragment tf in tfa.TextFragments)
			{
				tf.TextState.Underline = false;
				tf.TextState.ForegroundColor = Color.Black;
			}
		}
		doc.Pages[a.PageIndex].Annotations.Delete(a);
	}
}
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

## Conclusión
En este tutorial, cubrimos el proceso paso a paso de eliminar hipervínculos de un archivo PDF generado a partir de un archivo HTML usando Aspose.PDF para .NET. Si sigue las instrucciones descritas anteriormente, podrá eliminar con éxito los hipervínculos del archivo PDF resultante.

### Preguntas frecuentes

#### P: ¿Qué es Aspose.PDF para .NET?

R: Aspose.PDF para .NET es una potente biblioteca que permite a los desarrolladores trabajar con documentos PDF en aplicaciones C#. Ofrece una amplia gama de funcionalidades, incluida la capacidad de convertir archivos HTML a PDF y manipular contenido PDF.

#### P: ¿Por qué querría eliminar hipervínculos de un archivo PDF?

R: Existen varias razones para eliminar hipervínculos de un archivo PDF. Por ejemplo, es posible que desee eliminar enlaces externos para fines de impresión o archivado o asegurarse de que el contenido del PDF no sea navegable a través de hipervínculos.

#### P: ¿Cómo puedo cargar un archivo HTML y eliminar hipervínculos usando Aspose.PDF para .NET?

 R: Para cargar un archivo HTML y eliminar hipervínculos, puede utilizar Aspose.PDF para .NET.`HtmlLoadOptions` clase. Recorra las anotaciones de las páginas PDF para encontrar anotaciones de enlaces y modificar sus atributos.

#### P: ¿Puedo personalizar el nombre del archivo de salida del PDF resultante?

R: Sí, puede personalizar el nombre del archivo de salida del archivo PDF resultante modificando el código que guarda el documento PDF. Simplemente cambie el nombre de archivo deseado en el`doc.Save()` método.

#### P: ¿Es posible eliminar hipervínculos de forma selectiva según ciertos criterios?

R: Sí, puede eliminar hipervínculos de forma selectiva según criterios específicos. Por ejemplo, puede optar por eliminar sólo enlaces externos o enlaces que apunten a URL específicas.