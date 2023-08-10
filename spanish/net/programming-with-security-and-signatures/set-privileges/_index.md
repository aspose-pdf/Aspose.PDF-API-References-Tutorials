---
title: Establecer privilegios en archivo PDF
linktitle: Establecer privilegios en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Configure fácilmente los privilegios de acceso en un archivo PDF con Aspose.PDF para .NET.
type: docs
weight: 100
url: /es/net/programming-with-security-and-signatures/set-privileges/
---
A menudo es necesario establecer privilegios de acceso específicos en el archivo PDF. Con Aspose.PDF para .NET, puede configurar fácilmente los privilegios de acceso utilizando el siguiente código fuente:

## Paso 1: importa las bibliotecas requeridas

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto de C#. Aquí están las directivas de importación necesarias:

```csharp
using Aspose.Pdf;
```

## Paso 2: establecer la ruta a la carpeta de documentos

 En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF que desea editar. Reemplazar`"YOUR DOCUMENTS DIRECTORY"`en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 3: Cargue el archivo PDF de origen

Ahora cargaremos el archivo PDF fuente usando el siguiente código:

```csharp
using (Document document = new Document(dataDir + "input.pdf"))
```

## Paso 4: Establecer privilegios de acceso

 En este paso, instanciaremos el`DocumentPrivilege` objeto para establecer los privilegios de acceso deseados. Puede aplicar restricciones en todos los privilegios usando`DocumentPrivilege.ForbidAll` . Por ejemplo, si solo desea permitir la lectura de pantalla, puede configurar`AllowScreenReaders` a`true`. Aquí está el código correspondiente:

```csharp
DocumentPrivilege documentPrivilege = DocumentPrivilege.ForbidAll;
documentPrivilege.AllowScreenReaders = true;
```

## Paso 5: cifrar y guardar el documento

 Finalmente, podemos encriptar el documento PDF con una contraseña de usuario y propietario usando`Encrypt` y especificar el algoritmo de cifrado deseado. Luego guardamos el documento actualizado. Aquí está el código correspondiente:

```csharp
document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
document.Save(dataDir + "SetPrivileges_out.pdf");
```

### Ejemplo de código fuente para establecer privilegios con Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Cargue un archivo PDF de origen
using (Document document = new Document(dataDir + "input.pdf"))
{
	// Instanciar objeto de privilegios de documento
	// Aplicar restricciones en todos los privilegios
	DocumentPrivilege documentPrivilege = DocumentPrivilege.ForbidAll;
	// Solo permitir lectura de pantalla
	documentPrivilege.AllowScreenReaders = true;
	// Cifre el archivo con la contraseña de Usuario y Propietario.
	// Necesita configurar la contraseña, de modo que una vez que el usuario vea el archivo con la contraseña de usuario,
	// Solo está habilitada la opción de lectura de pantalla
	document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
	// Guardar documento actualizado
	document.Save(dataDir + "SetPrivileges_out.pdf");
}
```

## Conclusión

¡Felicidades! Ahora tiene una guía paso a paso para configurar los privilegios de acceso a un documento PDF utilizando Aspose.PDF para .NET. Puede usar este código para aplicar restricciones específicas y proteger sus archivos PDF según sea necesario.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre la seguridad avanzada de documentos PDF y las funciones de administración de privilegios de acceso.

### Preguntas frecuentes para establecer privilegios en un archivo PDF

#### P: ¿Por qué tendría que establecer privilegios de acceso en un archivo PDF?

R: Establecer privilegios de acceso le permite controlar cómo los usuarios interactúan con sus documentos PDF. Puede restringir acciones como imprimir, copiar y editar para mejorar la seguridad del documento.

#### P: ¿Cómo puedo beneficiarme al establecer privilegios de acceso usando Aspose.PDF para .NET?

R: Aspose.PDF para .NET proporciona una forma sencilla de implementar privilegios de acceso, lo que le permite personalizar los permisos de los usuarios y proteger el contenido confidencial.

#### P: ¿Puedo aplicar diferentes privilegios para diferentes usuarios?

R: Sí, puede establecer privilegios de acceso específicos para diferentes grupos de usuarios, lo que le permite ajustar el acceso a los documentos en función de las funciones de los usuarios.

#### P: ¿Cuáles son algunos privilegios de acceso comunes que puedo establecer?

R: Los privilegios de acceso comunes incluyen permitir o prohibir acciones como imprimir, copiar texto o imágenes, modificar el documento y completar campos de formulario.

#### P: ¿Cómo mejora la accesibilidad del documento la configuración del privilegio de lectura de pantalla?

R: Habilitar el privilegio de lectura de pantalla garantiza que los usuarios puedan acceder al contenido del PDF mediante lectores de pantalla, lo que mejora la accesibilidad para las personas con discapacidades visuales.

#### P: ¿Puedo configurar la protección con contraseña junto con los privilegios de acceso?

R: Absolutamente, puede encriptar su documento PDF con contraseñas mientras aplica los privilegios de acceso. Esto proporciona una capa extra de seguridad.

#### P: ¿Hay alguna forma de revocar los privilegios de acceso después de aplicarlos?

R: Una vez que se aplican los privilegios de acceso y se cifra el documento, los usuarios necesitarán la contraseña adecuada para acceder al contenido. Los privilegios se pueden modificar alterando el código fuente.

#### P: ¿Existen consideraciones de rendimiento al configurar los privilegios de acceso?

R: El impacto en el rendimiento es mínimo, ya que la configuración de los privilegios de acceso se aplica durante el cifrado, que es un proceso rápido.

#### P: ¿Puedo aplicar privilegios de acceso a un documento PDF existente?

R: Sí, puede usar Aspose.PDF para .NET para aplicar privilegios de acceso a documentos PDF nuevos y existentes.