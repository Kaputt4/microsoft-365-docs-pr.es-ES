---
title: INICIAR API de investigación
description: Usa esta API para iniciar la investigación en un dispositivo.
keywords: api, api de gráfico, api admitidas, investigación
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4bdbfbb20f3abb9829b2c8be83b9eaa6ec92cde7
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187330"
---
# <a name="start-investigation-api"></a>INICIAR API de investigación

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descripción de la API
Inicie una investigación automatizada en un dispositivo.
<br>Vea [Overview of automated investigations](automated-investigations.md) para obtener más información.


## <a name="limitations"></a>Limitaciones
1. Las limitaciones de velocidad para esta API son 50 llamadas por hora.


## <a name="permissions"></a>Permisos
Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)

Tipo de permiso |   Permiso  |   Nombre para mostrar de permisos
:---|:---|:---
Aplicación |   Alert.ReadWrite.All |   'Leer y escribir todas las alertas'
Delegado (cuenta profesional o educativa) | Alert.ReadWrite | 'Leer y escribir alertas'

>[!Note]
> Al obtener un token con credenciales de usuario:
>- El usuario debe tener al menos el siguiente permiso de función: "Acciones de corrección activas" (vea [Crear y](user-roles.md) administrar roles para obtener más información)
>- El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos (consulta Crear y administrar grupos [de dispositivos](machine-groups.md) para obtener más información)


## <a name="http-request"></a>Solicitud HTTP
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/startInvestigation
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre | Tipo | Descripción
:---|:---|:---
Authorization | Cadena | Portador {token}. **Necesario**.
Content-Type | string | application/json. **Necesario**.

## <a name="request-body"></a>Cuerpo de la solicitud
En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:

Parámetro | Tipo    | Descripción
:---|:---|:---
Comentario |   Cadena |    Comentario para asociarlo a la acción. **Necesario**.


## <a name="response"></a>Respuesta
Si se realiza correctamente, este método devuelve 201: código de respuesta creado e [Investigación](investigation.md) en el cuerpo de la respuesta.


## <a name="example"></a>Ejemplo

**Solicitud**

Aquí tiene un ejemplo de la solicitud.

```https
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/startInvestigation
```

```json
{
  "Comment": "Test investigation"
}
```
