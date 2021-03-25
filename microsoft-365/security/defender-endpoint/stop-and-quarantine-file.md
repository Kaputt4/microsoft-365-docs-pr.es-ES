---
title: API de archivos de detenerse y poner en cuarentena
description: Obtén información sobre cómo dejar de ejecutar un archivo en un dispositivo y eliminar el archivo en Microsoft Defender para endpoint. Vea un ejemplo.
keywords: api, api de gráfico, api admitidas, archivo de detenerse y poner en cuarentena
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
ms.openlocfilehash: 670282f0f87092437bb1f3c6bf7be908e4649042
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199734"
---
# <a name="stop-and-quarantine-file-api"></a>API de archivos de detenerse y poner en cuarentena

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descripción de la API
Detenga la ejecución de un archivo en un dispositivo y elimínelo.


## <a name="limitations"></a>Limitaciones
1. Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a>Permisos
Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)

Tipo de permiso |   Permiso  |   Nombre para mostrar de permisos
:---|:---|:---
Aplicación |   Machine.StopAndQuarantine | 'Detener y poner en cuarentena'
Delegado (cuenta profesional o educativa) | Machine.StopAndQuarantine | 'Detener y poner en cuarentena'

>[!Note]
> Al obtener un token con credenciales de usuario:
>- El usuario debe tener al menos el siguiente permiso de función: "Acciones de corrección activas" (vea [Crear y](user-roles.md) administrar roles para obtener más información)
>- El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos (consulta Crear y administrar grupos [de dispositivos](machine-groups.md) para obtener más información)

## <a name="http-request"></a>Solicitud HTTP
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/StopAndQuarantineFile
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
Sha1 |  Cadena   | Sha1 del archivo para detener y poner en cuarentena en el dispositivo. **Necesario**.

## <a name="response"></a>Respuesta
Si se realiza correctamente, este método devuelve 201: código de respuesta creado y [Acción de](machineaction.md) máquina en el cuerpo de la respuesta.


## <a name="example"></a>Ejemplo

**Solicitud**

Aquí tiene un ejemplo de la solicitud.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/StopAndQuarantineFile 
```

```json
{
  "Comment": "Stop and quarantine file on machine due to alert 441688558380765161_2136280442",
  "Sha1": "87662bc3d60e4200ceaf7aae249d1c343f4b83c9"
}

```
