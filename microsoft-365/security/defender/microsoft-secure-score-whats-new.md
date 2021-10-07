---
title: Novedades de La puntuación segura de Microsoft
description: Describe los nuevos cambios que han ocurrido en Microsoft Secure Score en el portal Microsoft 365 Defender web.
keywords: puntuación segura de microsoft, puntuación segura, puntuación segura de Office 365, puntuación de seguridad de Microsoft, Microsoft 365 Defender portal
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
ms.openlocfilehash: 59ff0e516bb6b0a5f5c89e07fb972184a5a6c837
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60162307"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Novedades de La puntuación segura de Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Para que Microsoft Secure Score sea un mejor representante de su posición de seguridad, hemos realizado algunos cambios. Para obtener información sobre los cambios planeados, consulte [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md)

Microsoft Secure Score se puede encontrar en https://security.microsoft.com/securescore el [portal de Microsoft 365 Defender.](overview-security-center.md)

## <a name="july-2021"></a>Julio de 2021

### <a name="added-improvement-action-related-to-microsoft-teams"></a>Se agregó una acción de mejora relacionada con Microsoft Teams

- Restringir que los usuarios de acceso telefónico no omita una sala de espera de reuniones
- Limitar que los participantes externos tengan control en una Teams reunión
- Restringir que los usuarios anónimos inicien Teams reuniones
- Requerir que los lobbies se configuren para Teams reuniones
- Configurar qué usuarios pueden estar presentes en Teams reuniones

### <a name="added-improvement-action-related-to-microsoft-defender-for-endpoint"></a>Se agregó una acción de mejora relacionada con Microsoft Defender para endpoint

- Corrección de Microsoft Defender para la recopilación de datos del sensor de extremo para macOS
- Corrección de Microsoft Defender para comunicaciones con problemas de punto de conexión para macOS
- Establecer la longitud mínima de contraseña en 15 o más caracteres en macOS
- Establece "Exigir historial de contraseñas" en "24 o más contraseñas" en macOS
- Establecer "Antigüedad máxima de contraseña" en "90 o menos días, pero no 0" en macOS
- Establecer el umbral de bloqueo de cuentas en 5 o inferior en macOS
- Activar firewall en macOS
- Habilitar Gatekeeper
- Habilitar la protección de integridad del sistema (SIP)
- Habilitar el cifrado de disco de FileVault
- Establecer la pantalla para que se bloquee cuando se inicie el protector de pantalla en macOS
- Asegúrese de que el protector de pantalla está configurado para iniciarse en 20 minutos o menos en macOS
- Carpetas de inicio seguras
- Activar la Antivirus de Microsoft Defender en tiempo real para macOS
- Activar la Antivirus de Microsoft Defender PUA en modo de bloqueo para macOS
- Habilitar Antivirus de Microsoft Defender de entrega en la nube para macOS
- Actualizar Antivirus de Microsoft Defender para macOS
- Corrección de microsoft defender para la recopilación de datos del sensor de extremo para Linux
- Corregir microsoft defender para las comunicaciones con problemas de punto de conexión para Linux
- Cuentas de acceso sin restricciones
- Activar la Antivirus de Microsoft Defender en tiempo real para Linux
- Activar la protección Antivirus de Microsoft Defender PUA en modo de bloqueo para Linux
- Habilitar Antivirus de Microsoft Defender de entrega en la nube para Linux
- Actualizar Antivirus de Microsoft Defender para Linux

## <a name="june-2021"></a>Junio de 2021

### <a name="removed-improvement-action-related-to-microsoft-cloud-app-security"></a>Se quitó la acción de mejora relacionada con Microsoft Cloud App Security

- Use Cloud App Security para detectar comportamientos anómalos.

## <a name="february-2021"></a>Febrero de 2021

### <a name="compatibility-with-graph-api"></a>Compatibilidad con Graph API

Las recomendaciones de puntuación segura de Microsoft que se entregan Graph api de seguridad tendrán el mismo aspecto que las recomendaciones que se ven actualmente en Microsoft 365 Defender portal.

## <a name="january-2021"></a>Enero de 2021

### <a name="added-our-first-security-recommendation-for-microsoft-teams"></a>Se agregó nuestra primera recomendación de seguridad para Microsoft Teams

Microsoft Teams los clientes verán "Restringir que los usuarios anónimos se unan a reuniones" como una nueva acción de mejora en Puntuación segura.

## <a name="december-2020"></a>Diciembre de 2020

### <a name="added-six-accounts-related-improvement-actions-for-microsoft-defender-for-endpoint"></a>Se agregaron seis acciones de mejora relacionadas con cuentas para Microsoft Defender para endpoint:

- Establecer "Longitud mínima de contraseña" en "14 o más caracteres"
- Establece "Exigir historial de contraseñas" en "24 o más contraseñas".
- Establecer "Antigüedad máxima de contraseña" en "60 o menos días, pero no 0"
- Establecer "Antigüedad mínima de contraseña" en "1 o más días".
- Deshabilitar la cuenta de administrador integrada
- Deshabilitar la cuenta de invitado integrada

## <a name="november-2020"></a>Noviembre de 2020

### <a name="removed-the-ability-to-create-servicenow-tickets-through-secure-score"></a>Se quitó la capacidad de crear vales de ServiceNow a través de puntuación segura 

La capacidad de crear vales de ServiceNow a través de Puntuación segura yendo a **Compartir > ServiceNow** ya no está disponible. Gracias por sus comentarios y soporte continuado mientras determinamos los pasos siguientes.

### <a name="added-three-services-related-improvement-actions-for-microsoft-defender-for-endpoint"></a>Se agregaron tres acciones de mejora relacionadas con los servicios para Microsoft Defender para endpoint:

- Corregir la ruta de acceso de servicio sin comillas para Windows servicios
- Cambiar la ruta de acceso ejecutable del servicio a una ubicación protegida común
- Cambiar la cuenta de servicio para evitar la contraseña almacenada en caché en el Registro de Windows

## <a name="october-2020"></a>Octubre de 2020

### <a name="removed-improvement-action-related-to-microsoft-defender-for-endpoint"></a>Se quitó la acción de mejora relacionada con Microsoft Defender para endpoint

- Establecer SmartScreen de Microsoft Defender Windows de contenido web de la aplicación de la Tienda para advertir

## <a name="august-2020"></a>Agosto de 2020

### <a name="updated-improvement-action-for-azure-active-directory"></a>Acción de mejora actualizada para Azure Active Directory

- Habilitar la directiva para bloquear la autenticación heredada

## <a name="incompatibility-with-identity-secure-score"></a>Incompatibilidad con la puntuación segura de identidad

En la versión reciente de Puntuación segura de Microsoft, se ha publicado un modelo de puntuación mejorado. Estos cambios permiten una vista más flexible y precisa de su posición de seguridad. Sin embargo, estas actualizaciones han hecho que Microsoft Secure Score sea temporalmente incompatible con identity secure score.

Con el tiempo, la puntuación segura de identidad adoptará el nuevo modelo de puntuación. Hasta entonces, los clientes verán diferencias en las puntuaciones notificadas por la puntuación segura de Microsoft y la puntuación segura de identidad. Pedimos disculpas por los inconvenientes que esto causa y estamos trabajando para garantizar que estas experiencias sean más compatibles en el futuro.

## <a name="updated-improvement-actions"></a>Acciones de mejora actualizadas

- Se agregaron Azure Active Directory acciones de mejora
- Se agregaron acciones de mejora de Identidad de Microsoft Defender
- Compatibilidad con Microsoft Defender para recomendaciones de seguridad de administración [& de vulnerabilidades](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
    - Todas las recomendaciones de seguridad publicadas proporcionadas por TVM ya están disponibles

## <a name="updated-interface-and-functionality"></a>Interfaz y funcionalidad actualizadas

* Todas las nuevas métricas y vistas de tendencias para CISO y discusiones de nivel de cliente potencial
* Nuevas formas de realizar un seguimiento y comparar la puntuación
* Mejor seguimiento y comprensión de las regresión de puntuación
* Filtrar, etiquetar, buscar y agrupar las acciones de mejora
* Administrar hacia sus objetivos futuros mediante proyecciones de puntuación y acciones planeadas
* Y mucho más.

## <a name="we-want-to-hear-from-you"></a>Queremos escuchar sus comentarios

Si tiene algún problema, háganoslo saber publicando en la comunidad [seguridad, privacidad & cumplimiento.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) Estamos supervisando la comunidad y proporcionaremos ayuda.

## <a name="related-resources"></a>Recursos relacionados

- [Evaluar su posición de seguridad](microsoft-secure-score-improvement-actions.md)
- [Realizar un seguimiento del historial de puntuación segura de Microsoft y cumplir objetivos](microsoft-secure-score-history-metrics-trends.md)
- [Próximas novedades](microsoft-secure-score-whats-coming.md)
