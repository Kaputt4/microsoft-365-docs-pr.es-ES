---
title: Novedades de la puntuación de seguridad de Microsoft
description: Describe los nuevos cambios que han ocurrido en la puntuación de seguridad de Microsoft en el Centro de seguridad de Microsoft 365.
keywords: puntuación de seguridad de microsoft, puntuación de seguridad, puntuación de seguridad de Office 365, puntuación de seguridad de Microsoft, centro de seguridad de Microsoft 365
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
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
ms.openlocfilehash: 039ec1c3f9b0ba233f950d11b9d58be341b28121
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930599"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Novedades de la puntuación de seguridad de Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Para que La puntuación de seguridad de Microsoft sea un mejor representante de su posición de seguridad, hemos realizado algunos cambios. Para obtener información sobre los cambios planeados, consulte ¿Qué viene en puntuación de [seguridad de Microsoft?](microsoft-secure-score-whats-coming.md)

La puntuación de seguridad de Microsoft puede encontrarse en el Centro de seguridad https://security.microsoft.com/securescore [de Microsoft 365.](overview-security-center.md)

## <a name="january-2021"></a>Enero de 2021

### <a name="added-our-first-security-recommendation-for-microsoft-teams"></a>Se agregó nuestra primera recomendación de seguridad para Microsoft Teams

Los clientes de Microsoft Teams verán "Impedir que los usuarios anónimos se unan a reuniones" como una nueva acción de mejora en la puntuación de seguridad.

## <a name="december-2020"></a>Diciembre de 2020

### <a name="added-six-accounts-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>Se agregaron seis acciones de mejora relacionadas con cuentas para Microsoft Defender para endpoint (anteriormente ATP de Microsoft Defender):

- Establecer "Longitud mínima de contraseña" en "14 o más caracteres"
- Establecer "Exigir historial de contraseñas" en "24 o más contraseñas"
- Establecer "Antigüedad máxima de contraseña" en "60 días o menos, pero no 0"
- Establecer "Antigüedad mínima de contraseña" en "1 o más días"
- Deshabilitar la cuenta de administrador integrada
- Deshabilitar la cuenta de invitado integrada

## <a name="november-2020"></a>Noviembre de 2020

### <a name="removed-the-ability-to-create-servicenow-tickets-through-secure-score"></a>Se quitó la capacidad de crear vales de ServiceNow a través de puntuación de seguridad 

La capacidad de crear vales de ServiceNow a través de puntuación de seguridad yendo a **Compartir > ServiceNow** ya no está disponible. Gracias por sus comentarios y soporte continuo mientras determinamos los pasos siguientes.

### <a name="added-three-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>Se agregaron tres acciones de mejora relacionadas con los servicios para Microsoft Defender para Endpoint (anteriormente ATP de Microsoft Defender):

- Corregir la ruta de acceso de servicio sin comillas para los servicios de Windows
- Cambiar la ruta del archivo ejecutable del servicio a una ubicación protegida común
- Cambiar la cuenta de servicio para evitar la contraseña almacenada en caché en el Registro de Windows

## <a name="october-2020"></a>Octubre de 2020

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a>Quitar la acción de mejora relacionada con Microsoft Defender para endpoint

- Establecer la comprobación del contenido de la aplicación de la Tienda Windows SmartScreen de Microsoft Defender para advertir

## <a name="august-2020"></a>Agosto de 2020

### <a name="updated-improvement-action-for-azure-active-directory"></a>Acción de mejora actualizada para Azure Active Directory

- Habilitar la directiva para bloquear la autenticación heredada

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Incompatibilidad con la puntuación de seguridad de identidad y la API de Graph

En la versión reciente de Puntuación de seguridad de Microsoft, se ha publicado un modelo de puntuación mejorado. Estos cambios permiten una vista más flexible y precisa de su posición de seguridad. Sin embargo, estas actualizaciones han hecho que la puntuación de seguridad de Microsoft sea temporalmente incompatible con la puntuación de seguridad de identidad y la API de Graph.

Con el tiempo, la puntuación de seguridad de identidad y la API de Graph adoptarán el nuevo modelo de puntuación. Hasta entonces, los clientes verán diferencias en las puntuaciones notificadas por la puntuación de seguridad de Microsoft, la puntuación de seguridad de identidad y la API de Graph. We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.

## <a name="updated-improvement-actions"></a>Acciones de mejora actualizadas

- Se agregaron acciones de mejora de Azure Active Directory
- Se agregaron acciones de mejora de Microsoft Defender para la identidad
- Compatibilidad con Microsoft Defender para las recomendaciones de seguridad [de & de](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) endpoint threat
    - Todas las recomendaciones de seguridad publicadas proporcionadas por TVM ya están disponibles

## <a name="updated-interface-and-functionality"></a>Interfaz y funcionalidad actualizadas

* Todas las nuevas métricas y vistas de tendencias para discusiones de nivel de líder y CISO
* Nuevas formas de realizar un seguimiento y realizar pruebas comparativas de tu puntuación
* Mejor seguimiento y comprensión para las regresión de puntuaciones
* Filtrar, etiquetar, buscar y agrupar las acciones de mejora
* Administrar hacia sus objetivos futuros mediante proyecciones de puntuación y acciones planeadas
* Y mucho más.

## <a name="we-want-to-hear-from-you"></a>Queremos escuchar sus comentarios

Si tiene algún problema, háganoslo saber publicando en la comunidad [seguridad, privacidad & cumplimiento.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) Estamos supervisando la comunidad y proporcionaremos ayuda.

## <a name="related-resources"></a>Recursos relacionados

- [Evaluar su postura de seguridad](microsoft-secure-score-improvement-actions.md)
- [Realizar un seguimiento del historial de puntuaciones seguras de Microsoft y cumplir los objetivos](microsoft-secure-score-history-metrics-trends.md)
- [Próximas novedades](microsoft-secure-score-whats-coming.md)
