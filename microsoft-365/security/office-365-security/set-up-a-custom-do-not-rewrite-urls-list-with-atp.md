---
title: Configurar una lista de direcciones URL de do-not-Rewrite personalizada con los vínculos seguros de Office 365 ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
ms.collection:
- M365-security-compliance
description: Cuando configure las directivas de vínculos seguros de ATP, puede incluir una lista de direcciones URL de "do-not-Rewrite" para permitir que algunos usuarios de la organización visiten los sitios que incluya en la lista.
ms.openlocfilehash: 1983e0ff2ea85092af483d4f7a563681a6441152
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42082219"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-office-365-atp-safe-links"></a>Configurar una lista de direcciones URL de do-not-Rewrite personalizada con los vínculos seguros de Office 365 ATP

> [!IMPORTANT]
> Este artículo está destinado a los clientes empresariales que tienen la [Protección contra amenazas avanzada de Office 365](office-365-atp.md). Si es un usuario doméstico que busca información sobre vínculos seguros en Outlook, consulte [Advanced Outlook.com Security](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).

Con [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), su organización puede tener [direcciones URL bloqueadas personalizadas](set-up-a-custom-blocked-urls-list-wtih-atp.md), de modo que cuando los usuarios hagan clic en direcciones web (URL) en mensajes de correo electrónico o en determinados documentos de Office, no se les impedirá ir a esas direcciones URL. La organización también puede tener listas personalizadas de "no reescribir" para grupos específicos de la organización. Una lista "no reescribir" permite que algunas personas visiten direcciones URL que, de lo contrario, se bloquearán mediante [vínculos seguros de ATP en Office 365](atp-safe-links.md).

En este artículo se describe cómo especificar una lista de direcciones URL que se excluyen del análisis de vínculos seguros de ATP y algunos puntos importantes que se deben tener en cuenta.

## <a name="set-up-a-do-not-rewrite-list"></a>Configurar una lista de "no reescribir"

La protección de vínculos seguros de ATP usa varias listas, incluidas la lista de URL bloqueadas de su organización y las listas "no reescribir" para las excepciones. Si tiene los permisos necesarios, puede configurar las listas de "no reescribir" personalizadas. Esto se hace al agregar o editar directivas de vínculos a prueba de errores que se aplican a destinatarios específicos de la organización.

Para editar (o definir) las directivas de ATP, debe tener asignado un rol apropiado. En la tabla siguiente se incluyen algunos ejemplos. Para obtener más información, consulte [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

|Role  |Dónde y cómo se asigna  |
|---------|---------|
|Administrador global de Office 365 |La persona que se registra para comprar Office 365 es un administrador global de forma predeterminada. (Consulte [acerca de los roles de administrador de Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) para obtener más información).         |
|Administrador de seguridad |Centro de administración de Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)Directory ()|
|Administración de la organización en Exchange Online |Centro de administración de[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)Exchange () <br>o <br>  Cmdlets de PowerShell (vea [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)) |

> [!TIP]
> Para obtener más información acerca de los roles y los permisos, consulte [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a>Para ver o editar una lista de direcciones URL "no reescribir" personalizadas

1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta profesional o educativa.

2. En el panel de navegación izquierdo, en **vínculos seguros**de la **Directiva** \> de **Administración** \> de amenazas.

3. En la sección **directivas que se aplican a destinatarios específicos** , elija **nuevo** (el botón nuevo es similar a un **+** signo más ()) para crear una nueva Directiva. (También puede editar una directiva existente).<br/>![Elija nuevo para agregar una directiva de vínculos seguros para destinatarios de correo electrónico específicos](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)

4. Especifique un nombre y una descripción para la Directiva.

5. En la sección no **reescribir las siguientes direcciones** URL, seleccione el cuadro **Escriba una dirección URL válida** y, a continuación, escriba una dirección URL y, a continuación, elija el signo más (+).

6. En la sección **aplicado a** , elija **el destinatario es miembro de**y, a continuación, elija el grupo o los grupos que desea incluir en la Directiva. Elija **Agregar**y, después, haga clic en **Aceptar**.

7. Cuando termine de agregar direcciones URL, en la esquina inferior derecha de la pantalla, elija **Guardar**.

> [!NOTE]
> Asegúrese de revisar la lista personalizada de direcciones URL bloqueadas de su organización. Consulte [configurar una lista de direcciones URL bloqueadas personalizadas mediante vínculos seguros de ATP](set-up-a-custom-blocked-urls-list-wtih-atp.md).

## <a name="important-points-to-keep-in-mind"></a>Aspectos importantes que debe tener en cuenta

- Las direcciones URL que especifique en la lista "no reescribir" se excluyen del análisis de vínculos seguros de ATP para los destinatarios que especifique.

- Si ya tiene una lista de direcciones URL en la lista "no reescribir", asegúrese de revisar dicha lista y agregar caracteres comodín según corresponda. Por ejemplo, si la lista existente tiene una entrada como `https://contoso.com/a` y desea incluir subrutas como `https://contoso.com/a/b` en la Directiva, agregue un carácter comodín a la entrada para que tenga el aspecto `https://contoso.com/a/*`deseado.

- Cuando se especifica una lista de "no reescribir" para una directiva de vínculos seguros de ATP, puede incluir hasta tres asteriscos comodín (\*). Los caracteres comodín\*() se usan para incluir explícitamente prefijos o subdominios. La entrada `contoso.com` no es la misma que `*.contoso.com/*`, ya `*.contoso.com/*` que permite a los pueblos visitar subdominios y rutas de acceso en el dominio especificado.

En la tabla siguiente se muestran ejemplos de lo que se puede especificar y el efecto que tienen estas entradas.

|**Entrada de ejemplo**|**Qué hace**|
|:-----|:-----|
|`contoso.com`|Permite a los destinatarios visitar un sitio `https://contoso.com` como, por ejemplo, subdominios o rutas de una ruta.|
|`*.contoso.com/*`|Permite a los destinatarios visitar un dominio, subdominios y rutas de, como `https://www.contoso.com`, `https://www.contoso.com` `https://maps.contoso.com`, o `https://www.contoso.com/a`. <br/><br/> Esta entrada es intrínsecamente mejor que `*contoso.com*`, ya que no incluye sitios potencialmente fraudulentos, `https://www.falsecontoso.com` como o`https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|Permite a los destinatarios específicos visitar un sitio `https://contoso.com/a`como, pero no subtrazados como`https://contoso.com/a/b`|
|`https://contoso.com/a/*`|Permite a los destinatarios específicos visitar un sitio `https://contoso.com/a` como y subrutas como`https://contoso.com/a/b`|
