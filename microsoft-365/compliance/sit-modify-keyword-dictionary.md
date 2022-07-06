---
title: Modificar un diccionario de palabras clave
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo modificar un diccionario de palabras clave en el portal de cumplimiento Microsoft Purview.
ms.openlocfilehash: 8b2f2256be506f0ba01dc059bf0ac54e84c481c9
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66621719"
---
# <a name="modify-a-keyword-dictionary"></a>Modificar un diccionario de palabras clave

Es posible que tenga que modificar palabras clave en uno de los diccionarios de palabras clave o modificar uno de los diccionarios integrados. Puede hacerlo a través de PowerShell o a través del Centro de cumplimiento.

## <a name="modify-a-keyword-dictionary-in-compliance-center"></a>Modificación de un diccionario de palabras clave en el Centro de cumplimiento

Los diccionarios de palabras clave se pueden usar como `Primary elements` o `Supporting elements` en patrones de tipo de información confidencial (SIT). Puede editar un diccionario de palabras clave al crear un SIT o en un SIT existente. Por ejemplo, para editar un diccionario de palabras clave existente:

1. Abra el patrón que tiene el diccionario de palabras clave que desea actualizar.
2. Busque el diccionario de palabras clave que desea actualizar y elija Editar.
3. Realice las modificaciones con una palabra clave por línea.

   ![captura de pantalla editar palabras clave.](../media/edit-keyword-dictionary.png)

4. Elija `Done`.

## <a name="modify-a-keyword-dictionary-using-powershell"></a>Modificación de un diccionario de palabras clave mediante PowerShell

Por ejemplo, vamos a modificar algunos términos en PowerShell, guardar los términos localmente donde se puedan modificar en un editor y, después, actualizar los términos anteriores.

En primer lugar, recupere el objeto de diccionario:

```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

La impresión `$dict` mostrará las distintas propiedades. Las propias palabras clave se almacenan en un objeto en el back-end, pero `$dict.KeywordDictionary` contienen una representación de cadena de ellas, que usará para modificar el diccionario.

Antes de modificar el diccionario, debe volver a convertir la cadena de términos en una matriz mediante el `.split(',')` método . A continuación, limpiará los espacios no deseados entre las palabras clave con el `.trim()` método , dejando solo las palabras clave con las que trabajar.

```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

Ahora, quitará algunos términos del diccionario. Como el diccionario de ejemplo solo tiene unas pocas palabras clave, podría fácilmente pasar a la exportación del diccionario y editarlo en el Bloc de notas, pero los diccionarios suelen contener una gran cantidad de texto, por lo que primero aprenderá esta forma de editarlos fácilmente en PowerShell.

En el último paso, guardó las palabras clave en una matriz. Hay varias formas de [quitar elementos de una matriz](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), pero un método sencillo es crear una matriz de los términos que quiera quitar del diccionario y, después, copiar en este solo los términos que no se encuentren en la lista de términos que quiera quitar.

Ejecute el comando `$terms` para mostrar la lista actual de términos. El resultado del comando tiene este aspecto:

```powershell
aarskog's syndrome
abandonment
abasia
abderhalden-kaufmann-lignac
abdominalgia
abduction contracture
abetalipoproteinemia
abiotrophy
ablatio
ablation
ablepharia
abocclusion
abolition
aborter
abortion
abortus
aboulomania
abrami's disease
```

Ejecute este comando para especificar los términos que quiera quitar:

```powershell
$termsToRemove = @('abandonment','ablatio')
```

Ejecute este comando para quitar los términos de la lista:

```powershell
$updatedTerms = $terms | Where-Object {$_ -notin $termsToRemove}
```

Ejecute el comando `$updatedTerms` para mostrar la lista actualizada de términos. La salida del comando tiene este aspecto (se han quitado los términos especificados):

```powershell
aarskog's syndrome
abasia
abderhalden-kaufmann-lignac
abdominalgia
abduction contracture
abetalipoproteinemia
abiotrophy
ablation
ablepharia
abocclusion
abolition
aborter
abortion
abortus
aboulomania
abrami's disease
```

Ahora, guarde el diccionario localmente y agregue algunos términos más. Puede agregar los términos aquí en PowerShell, pero tendrá que exportar el archivo localmente para asegurarse de que se guarde con la codificación Unicode y que contenga el BOM.

Para guardar el diccionario localmente, ejecute lo siguiente:

```powershell
Set-Content $updatedTerms -Path "C:\myPath\terms.txt"
```

Ahora, abra el archivo, agregue los otros términos y guárdelo con la codificación Unicode (UTF-16). Ahora, cargará los términos actualizados y actualizará el diccionario en contexto.

```powershell
Set-DlpKeywordDictionary -Identity "Diseases" -FileData ([System.IO.File]::ReadAllBytes('C:myPath\terms.txt'))
```

Ahora se ha actualizado el diccionario en contexto. El `Identity` campo toma el nombre del diccionario. Si también desea cambiar el nombre del diccionario mediante el `Set-` cmdlet , solo tendrá que agregar el `-Name` parámetro a lo anterior con el nuevo nombre del diccionario.

## <a name="see-also"></a>Vea también

- [Crear un diccionario de palabras clave](create-a-keyword-dictionary.md)
- [Crear un tipo personalizado de información confidencial](create-a-custom-sensitive-information-type.md)
