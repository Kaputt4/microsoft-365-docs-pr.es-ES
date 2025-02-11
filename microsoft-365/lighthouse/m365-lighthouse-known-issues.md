---
title: Problemas conocidos con Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
ms.reviewer: crimora
audience: Admin
ms.topic: article
ms.service: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolib
- M365-Lighthous
search.appverid: MET150
description: Para los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, consulte una lista de problemas conocidos de Lighthouse por área de características.
ms.openlocfilehash: a3e2162b196d7870b3ff8b5c456e91e1136c24cc
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68719045"
---
# <a name="known-issues-with-microsoft-365-lighthouse"></a>Problemas conocidos con Microsoft 365 Lighthouse

En este artículo se enumeran los problemas conocidos de Microsoft 365 Lighthouse por área de características. Para obtener más información sobre Lighthouse, consulte [Información general de Microsoft 365 Lighthouse](m365-lighthouse-overview.md).

## <a name="users"></a>Usuarios

| Problema | Descripción | Solución |
| ---------------- | ---------------- | ---------------- |
| **No se muestra ningún dato en la pestaña OneDrive del panel de detalles del usuario** | Cuando un técnico de MSP intenta ver los datos de OneDrive en la pestaña OneDrive en el panel de detalles del usuario, ve el mensaje: "OneDrive no está configurado para este usuario. Pida a la persona que vaya a portal.office.com/onedrive para configurarlo. Puede tardar un tiempo. Si sigue viendo este mensaje 24 horas más tarde, póngase en contacto con el soporte técnico." | La pestaña OneDrive no admite la autenticación delegada en este momento. Para solucionar el problema, los técnicos de MSP deben ver los datos de OneDrive en el Centro de administración de Microsoft 365 iniciando sesión con las credenciales del cliente. |

## <a name="threat-management"></a>Administración de amenazas

| Problema | Descripción | Solución |
| ---------------- | ---------------- | ---------------- |
| **Falta el nombre de la amenaza** | Cuando los técnicos de MSP ven la lista de amenazas desde la página Administración de amenazas, es posible que falte el nombre de la amenaza en algunas amenazas. Esto ocurrirá cuando el dispositivo en el que se detectó la amenaza se quitó recientemente de Intune. | El problema se resolverá en un plazo de 48 horas. No se requieren pasos adicionales. |

## <a name="baselines"></a>Líneas base

| Problema | Descripción | Solución |
| ---------------- | ---------------- | ---------------- |
| **Configuración en conflicto al comparar la autenticación heredada de bloque y los pasos de implementación de MFA** | Si un inquilino de cliente ha implementado la autenticación heredada de bloque y uno de los pasos de implementación de MFA, una prueba de comparación describirá erróneamente esta configuración como en conflicto. | No se requiere ninguna solución alternativa. La configuración no entra en conflicto y los usuarios del inquilino del cliente no se ven afectados. |

## <a name="windows-365"></a>Windows 365

| Problema | Descripción | Solución |
| ---------------- | ---------------- | ---------------- |
| **Error de aprovisionamiento de reintentos** | Los técnicos de MSP reciben un mensaje de error "No tiene permisos para hacerlo" al intentar reintentar el aprovisionamiento de un equipo en la nube. | Para solucionar este problema, inicie sesión en el inquilino del cliente y vuelva a aprovisionar equipos en la nube desde el Centro de administración de Microsoft Endpoint Manger. Para obtener instrucciones, consulte [Reprovision a Cloud PC( Reprovision a Cloud PC](/windows-365/enterprise/reprovision-cloud-pc)). |

## <a name="delegated-admin-privileges-dap"></a>Privilegios de Administración delegados (DAP)

| Problema | Descripción | Solución |
| ---------------- | ---------------- | ---------------- |
| **Retraso de permisos al cambiar los roles de DAP** | Si se agrega o quita un técnico de MSP del grupo agente de Administración o agente del departamento de soporte técnico, puede haber un retraso en la reflexión de los permisos adecuados en Lighthouse. | El problema se resolverá en 30 minutos. No se requieren pasos adicionales. |

## <a name="granular-delegated-admin-privileges-gdap"></a>Privilegios de Administración delegados granulares (GDAP)

Se requiere privilegios de Administración delegados granulares (GDAP) más una relación de revendedor indirecto o una relación de privilegios delegados de Administración (DAP) para incorporar clientes a Lighthouse. Si DAP y GDAP coexisten en un inquilino de cliente, los permisos de GDAP tienen prioridad para los técnicos de MSP en grupos de seguridad habilitados para GDAP. Los clientes con relaciones solo de GDAP (sin relaciones de revendedor indirecto) actualmente no pueden incorporarse a Lighthouse, pero podrán incorporarse en una versión futura.<br><br>

| Problema | Descripción | Solución |
| ---------------- | ---------------- | ---------------- |
| **Varios problemas de permisos de GDAP en Lighthouse** | Determinados roles de GDAP por sí mismos no conceden el mismo nivel de acceso a los datos del cliente en Lighthouse que en una experiencia de inquilino único. Si alguno de los siguientes roles se asigna individualmente (es decir, no en combinación con otros roles de GDAP) a los técnicos de MSP, pueden encontrar errores, incluidos:<ul><li>Los administradores de seguridad de GDAP no pueden ver usuarios de riesgo, descartar riesgos o confirmar usuarios en peligro en Lighthouse.</li><li>Los lectores de seguridad de GDAP no pueden ver usuarios de riesgo en Lighthouse.</li><li>Los administradores globales de GDAP ven un mensaje de error al intentar ver el estado del servicio en Lighthouse.</li><li>Los administradores globales de GDAP experimentan problemas al implementar los pasos del plan de implementación en Lighthouse.</li></ul> | La solución alternativa consiste en asignar una combinación de roles GDAP a los técnicos de MSP en función del nivel de acceso a los datos del cliente que necesitan. Para obtener una lista de los roles de GDAP recomendados para usar Lighthouse, consulte [Introducción a los permisos en Microsoft 365 Lighthouse](m365-lighthouse-overview-of-permissions.md).<br><br>Para los problemas en los que incluso los permisos de administrador global de GDAP no permiten el uso de una característica en Lighthouse, la solución alternativa es acceder al centro de administración adecuado desde el inquilino del cliente para administrar al cliente (por ejemplo, acceder a la Centro de administración de Microsoft 365 desde el inquilino del cliente para comprobar el estado del servicio). Para obtener instrucciones sobre cómo modificar una relación GDAP, consulte [Obtención de permisos de administrador pormenorizados para administrar el servicio de un cliente: Centro de partners](/partner-center/gdap-obtain-admin-permissions-to-manage-customer). |

## <a name="localization"></a>Localización

| Problema | Descripción | Solución |
| ---------------- | ---------------- | ---------------- |
| **Problemas de traducción** | Los usuarios pueden experimentar problemas de traducción de idioma cuando el idioma de su explorador, o su selección de idioma en Lighthouse, no sea inglés. | Para minimizar los problemas de traducción en Lighthouse, asegúrese de que la selección de idioma del explorador coincide con la de la configuración de idioma en el portal de Lighthouse. Para cambiar la selección de idioma en Lighthouse, inicie sesión en Lighthouse y seleccione el icono de engranaje de la parte superior de la página para abrir la página Configuración del portal, seleccione **Idioma y región** y, a continuación, seleccione el idioma y los formatos regionales adecuados. |

## <a name="related-content"></a>Contenido relacionado

[preguntas más frecuentes sobre Microsoft 365 Lighthouse](m365-lighthouse-faq.yml) (artículo)\
[Solución de problemas y mensajes de error en Microsoft 365 Lighthouse](m365-lighthouse-troubleshoot.md) (artículo)\
[Obtener ayuda y soporte técnico para Microsoft 365 Lighthouse](m365-lighthouse-get-help-and-support.md) (artículo)
