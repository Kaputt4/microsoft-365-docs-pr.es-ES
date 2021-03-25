---
title: Agregar o quitar API de etiquetas de máquina
description: Obtenga información sobre cómo usar la API Agregar o quitar etiquetas de máquina para agregar o quitar una etiqueta para una máquina en Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api admitidas, etiquetas, etiquetas de máquina
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
ms.openlocfilehash: 98dd513cc66683ff1b95f66d6d7b89916ce54bab
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199782"
---
# <a name="add-or-remove-machine-tags-api"></a>Agregar o quitar API de etiquetas de máquina

**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Agrega o quita etiqueta a una [máquina específica.](machine.md)

## <a name="limitations"></a>Limitaciones

1. Puede publicar en máquinas que se han visto por última vez de acuerdo con el período de retención configurado.

2. Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.


## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Defender for Endpoint API](apis-intro.md)

Tipo de permiso |    Permiso    |    Nombre para mostrar de permisos
:---|:---|:---
Aplicación |    Machine.ReadWrite.All |    'Leer y escribir toda la información de la máquina'
Delegado (cuenta profesional o educativa) | Machine.ReadWrite | 'Leer y escribir información de máquina'

>[!Note]
> Al obtener un token con credenciales de usuario:
>
>- El usuario debe tener al menos el siguiente permiso de función: "Administrar la configuración de seguridad". Para obtener más información (vea [Crear y administrar roles](user-roles.md) para obtener más información)
>- El usuario debe tener acceso a la máquina en función de la configuración del grupo de máquinas (vea [Crear y](machine-groups.md) administrar grupos de máquinas para obtener más información)

## <a name="http-request"></a>Solicitud HTTP

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/tags
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre | Tipo | Descripción
:---|:---|:---
Authorization | Cadena | Portador {token}. **Necesario**.
Content-Type | string | application/json. **Necesario**.

## <a name="request-body"></a>Cuerpo de la solicitud

En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:

Parámetro |    Tipo    | Descripción
:---|:---|:---
Valor |    Cadena |    El nombre de la etiqueta. **Necesario**.
Acción    | Enum |    Agregar o quitar. Los valores permitidos son: "Agregar" o "Quitar". **Necesario**.


## <a name="response"></a>Respuesta

Si se realiza correctamente, este método devuelve 200: código de respuesta Aceptar y la máquina actualizada en el cuerpo de la respuesta.

## <a name="example"></a>Ejemplo

**Solicitud**

Este es un ejemplo de una solicitud que agrega etiqueta de máquina.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/tags
```

```json
{
  "Value" : "test Tag 2",
  "Action": "Add"
}
```

- Para quitar la etiqueta de máquina, establece la acción en "Quitar" en lugar de "Agregar" en el cuerpo de la solicitud.
