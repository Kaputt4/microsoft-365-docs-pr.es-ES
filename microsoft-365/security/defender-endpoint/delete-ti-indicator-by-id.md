---
title: Eliminar API de indicador.
description: Obtenga información sobre cómo usar la API Eliminar indicador para eliminar una entidad Indicator por id. en Microsoft Defender para endpoint.
keywords: apis, api pública, api admitidas, delete, indicador ti, entidad, id
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: fb023ab3d4ec4115411b1c8d12ef1c2ef1b1eece
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2021
ms.locfileid: "53652340"
---
# <a name="delete-indicator-api"></a>Eliminar API de indicador

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descripción de la API

Elimina una entidad [Indicator](ti-indicator.md) por identificador.

## <a name="limitations"></a>Limitaciones

Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, vea [Introducción](apis-intro.md)

Tipo de permiso | Permiso | Nombre para mostrar de permisos
:---|:---|:---
Aplicación | Ti.ReadWrite | 'Leer y escribir indicadores de TI'
Aplicación | Ti.ReadWrite.All | Indicadores de lectura y escritura

## <a name="http-request"></a>Solicitud HTTP

```http
Delete https://api.securitycenter.microsoft.com/api/indicators/{id}
```

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization | Cadena | Portador {token}. **Necesario**.

## <a name="request-body"></a>Cuerpo de la solicitud

En blanco

## <a name="response"></a>Respuesta

Si el indicador existe y se elimina correctamente: 204 Aceptar sin contenido.

Si no se encontró Indicator con el identificador especificado- 404 No se encontró.

## <a name="example"></a>Ejemplo

### <a name="request"></a>Solicitud

Aquí tiene un ejemplo de la solicitud.

```http
DELETE https://api.securitycenter.microsoft.com/api/indicators/995
```
