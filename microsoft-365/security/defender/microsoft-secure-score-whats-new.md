---
title: Novedades de La puntuación segura de Microsoft
description: Describe los cambios nuevos que se han producido en La puntuación segura de Microsoft en el portal de Microsoft 365 Defender.
keywords: puntuación de seguridad de microsoft, puntuación de seguridad, puntuación de seguridad de office 365, puntuación de seguridad de Microsoft, Microsoft 365 Defender portal
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 6f478959d8e6de84ad64fdc128c4f7a9eea73a62
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2022
ms.locfileid: "67369145"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Novedades de La puntuación segura de Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Para que La puntuación segura de Microsoft sea un mejor representante de su posición de seguridad, seguimos agregando nuevas características y acciones de mejora.

Cuantos más acciones de mejora realice, mayor será la puntuación de seguridad. Para obtener más información, consulte [Puntuación segura de Microsoft](microsoft-secure-score.md).

La Puntuación de seguridad de Microsoft se puede encontrar en <https://security.microsoft.com/securescore> el [portal de Microsoft 365 Defender](microsoft-365-defender-portal.md).

## <a name="august-2022"></a>Agosto de 2022

Ahora hay nuevas recomendaciones de Microsoft Information Protection disponibles como acciones de mejora de puntuación segura:

- **Etiquetar**
  - Extensión del etiquetado de confidencialidad de M365 a los recursos del mapa de datos de Azure Purview
  - Asegúrese de que las directivas de clasificación de datos de etiquetado automático se configuran y usan.
  - Publicación de directivas de clasificación de datos de etiquetas de confidencialidad de M365
  - Creación de directivas de prevención de pérdida de datos (DLP)

Ahora hay nuevas recomendaciones de Microsoft Defender para Office 365 disponibles como acciones de mejora de puntuación segura:

- **Antispam: directiva de entrada**
  - Establecer el umbral de nivel de queja masiva de correo electrónico (BCL) en 6 o inferior
  - Establecer la acción que se va a realizar en la detección de correo no deseado
  - Establecer la acción para realizar la detección de correo no deseado de alta confianza
  - Establecer la acción que se va a realizar en la detección de suplantación de identidad (phishing)
  - Establecer la acción para realizar la detección de suplantación de identidad de alta confianza
  - Establecer acción para realizar la detección masiva de correo no deseado
  - Conservar el correo no deseado en cuarentena durante 30 días
  - Asegúrese de que las sugerencias de seguridad de correo no deseado estén habilitadas
  - Asegúrese de que no se permiten dominios de remitente para las directivas de antispam (reemplazará "Asegúrese de que no hay dominios de remitente permitidos para las directivas antispam" para ampliar la funcionalidad también para remitentes específicos).

- **Antispam: directiva de salida**
  - Establecer el número máximo de destinatarios externos que un usuario puede enviar por correo electrónico por hora
  - Establecer el número máximo de destinatarios internos a los que un usuario puede enviar en un plazo de una hora
  - Establecer un límite de mensajes diario
  - Bloquear usuarios que alcanzaron el límite de mensajes
  - Establecer reglas de reenvío automático de correo electrónico para que estén controladas por el sistema

- **Antispam: filtro de conexión**
  - No agregar direcciones IP permitidas en la directiva de filtro de conexión

## <a name="june-2022"></a>Junio de 2022

- Ahora hay disponibles nuevas recomendaciones de Microsoft Defender para punto de conexión y Administración de vulnerabilidades de Microsoft Defender como acciones de mejora de puntuación segura:

  - No permitir el acceso sin conexión a recursos compartidos
  - Quitar el permiso de escritura compartido establecido en **Todos**
  - Quitar recursos compartidos de la carpeta raíz
  - Establecimiento de una enumeración basada en el acceso a carpetas para recursos compartidos
  - Actualizar Microsoft Defender para punto de conexión componentes principales

- Hay disponible una nueva recomendación de Microsoft Defender for Identity como una acción de mejora de puntuación segura:

  - Resolución de configuraciones de dominio no seguras

- Ahora hay disponible una nueva recomendación de [gobernanza](/defender-cloud-apps/app-governance-manage-app-governance) de aplicaciones como una acción de mejora de puntuación segura:

  - Regular aplicaciones con consentimiento de cuentas prioritarias

- Las nuevas recomendaciones de Salesforce y ServiceNow ahora están disponibles como acciones de mejora de puntuación segura para Microsoft Defender for Cloud Apps clientes. Para obtener más información, consulte [Información general sobre la administración de posturas de seguridad de SaaS](https://aka.ms/saas_security_posture_management).

> [!NOTE]
> Los controles de Salesforce y ServiceNow ahora están disponibles en versión preliminar pública.

## <a name="april-2022"></a>Abril de 2022

- Activar la autenticación de usuario para conexiones remotas

## <a name="december-2021"></a>Diciembre de 2021

- Activar datos adjuntos seguros en modo de bloque
- Impedir el uso compartido Exchange Online detalles del calendario con usuarios externos
- Activar documentos seguros para clientes de Office
- Activar la configuración de filtro de datos adjuntos comunes para directivas antimalware
- Asegúrese de que no se permiten dominios de remitente para las directivas contra correo no deseado.
- Creación de directivas de vínculos seguros para mensajes de correo electrónico
- Creación de directivas de purga automática de cero horas para malware
- Activar Microsoft Defender para Office 365 en SharePoint, OneDrive y Microsoft Teams
- Creación de directivas de purga automática de cero horas para mensajes de phishing
- Creación de directivas de purga automática de cero horas para mensajes de correo no deseado
- Bloquear el abuso de controladores firmados vulnerables explotados
- Activar el examen de unidades extraíbles durante un examen completo

## <a name="we-want-to-hear-from-you"></a>Queremos escuchar sus comentarios

Si tiene algún problema, háganoslo saber publicando en la comunidad [seguridad, privacidad & cumplimiento](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) . Estamos supervisando la comunidad y proporcionaremos ayuda.

## <a name="related-resources"></a>Recursos relacionados

- [Evaluar su posición de seguridad](microsoft-secure-score-improvement-actions.md)
- [Seguimiento del historial de puntuación segura de Microsoft y cumplimiento de objetivos](microsoft-secure-score-history-metrics-trends.md)
- [Próximas novedades](microsoft-secure-score-whats-coming.md)
