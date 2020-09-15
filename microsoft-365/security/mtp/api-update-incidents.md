---
title: Actualizar la API de incidentes
description: Obtenga información sobre cómo actualizar incidentes mediante la API de Microsoft Threat Protection
keywords: actualización, API, incidente
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: e790f4f415575323cfdd5fc15db41baa8b59c7f6
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650520"
---
# <a name="update-incidents-api"></a>Actualizar la API de incidentes

**Se aplica a:**
- Protección contra amenazas de Microsoft

>[!IMPORTANT] 
>Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.


## <a name="api-description"></a>Descripción de la API
Actualiza las propiedades de un incidente existente.
<br>Las propiedades actualizables son: ```status``` ,, ```determination``` ```classification``` ```assignedTo``` y ```tags``` .


## <a name="limitations"></a>Limitaciones
1. Las limitaciones de frecuencia de esta API son 50 llamadas por minuto y 1500 llamadas por hora.
2. Puede establecer la ```determination``` sola si la clasificación se establece en TruePositive.


## <a name="permissions"></a>Permisos
Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [acceso a las API de Microsoft Threat Protection](api-access.md).

Tipo de permiso |   Permiso  |   Nombre para mostrar del permiso
:---|:---|:---
Aplicación |   Incident. ReadWrite. All |    ' Leer y escribir todos los incidentes '
Delegado (cuenta profesional o educativa) | Incident. ReadWrite | ' Incidentes de lectura y escritura '

>[!NOTE]
> Al obtener un token con credenciales de usuario:
>- El usuario debe tener permiso para actualizar el incidente en el portal.


## <a name="http-request"></a>Solicitud HTTP

```
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre | Tipo | Descripción
:---|:---|:---
Authorization | Cadena | {Token} de portador. **Necesario**.
Content-Type | Cadena | application/json. **Necesario**.


## <a name="request-body"></a>Cuerpo de la solicitud
En el cuerpo de la solicitud, proporcione los valores de los campos relevantes que deben actualizarse.
<br>Las propiedades existentes que no se incluyan en el cuerpo de la solicitud mantendrán los valores anteriores o se recalcularán según los cambios efectuados en otros valores de propiedad. 
<br>Para obtener el mejor rendimiento, no debe incluir valores existentes que no hayan cambiado.

Propiedad | Tipo | Description
:---|:---|:---
status | Enum | Especifica el estado actual de la alerta. Los valores posibles son ```Active``` : ```Resolved``` y ```Redirected``` .
assignedTo | cadena | Propietario del incidente.
classification | Enum | Especificación de la alerta. Los valores posibles son: ```Unknown```, ```FalsePositive``` y ```TruePositive```.
cálculo | Enum | Especifica la determinación de la alerta. Valores posibles: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | Lista de cadenas | Lista de etiquetas de incidente.



## <a name="response"></a>Respuesta
Si se ejecuta correctamente, este método devuelve 200 OK y la entidad Incident en el cuerpo de la respuesta con las propiedades actualizadas. Si no se ha encontrado el incidente con el identificador especificado-404 no se encuentra.


## <a name="example"></a>Ejemplo

**Solicitud**

Aquí tiene un ejemplo de la solicitud.

```
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```


## <a name="related-topic"></a>Tema relacionado
- [API de incidentes](api-incident.md)
- [Enumerar incidentes](api-list-incidents.md)