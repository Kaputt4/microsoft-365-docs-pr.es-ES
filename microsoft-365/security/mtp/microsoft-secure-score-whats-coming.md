---
title: ¿Qué viene con la puntuación segura de Microsoft?
description: Describe la puntuación segura de Microsoft en el centro de seguridad 365 de Microsoft, cómo se calculan los detalles y qué administradores de seguridad pueden esperar.
keywords: seguridad, malware, Microsoft 365, M365, calificación segura, centro de seguridad, acciones de mejora
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 4d445d4c917a46b12592308f599570725ace8e9d
ms.sourcegitcommit: 6c7f6ef98c321c80a9254c10bbbb917895b5c156
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "42322569"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>¿Qué viene con la puntuación segura de Microsoft?

Para hacer que la puntuación segura de Microsoft sea un mejor representante de su postura de seguridad y mejorar el uso, estamos realizando algunos cambios en un futuro próximo. Se cambiará la puntuación y la puntuación máxima posible. Sin embargo, esto no implica un cambio en su postura de seguridad.

Para obtener más información sobre los cambios recientes, vea [what's New in Secure score de Microsoft](microsoft-secure-score.md#whats-new)

## <a name="march-2nd-2020"></a>2 de marzo 2020

### <a name="removing-improvement-actions-from-intune"></a>Eliminación de acciones de mejora de Intune

Después de una evaluación de las acciones de mejora de la puntuación segura de Microsoft que se han proporcionado desde Intune, se decidió que no proporcionan una representación útil de la postura de seguridad de los dispositivos en las organizaciones. En lugar de centrarse en las directivas, estamos trabajando para incluir controles de seguridad que evalúen directamente el estado de configuración de los dispositivos.

Se quitarán las siguientes acciones para la mejora de Intune:

- Habilitar la administración de dispositivos móviles de Microsoft Intune
- Crear una directiva de cumplimiento de Microsoft Intune para Android
- Crear una directiva de cumplimiento de Microsoft Intune para Android para trabajar
- Crear una directiva de protección de aplicaciones de Microsoft Intune para Android
- Crear una directiva de protección de aplicaciones de Microsoft Intune para iOS
- Marcar dispositivos sin directiva de cumplimiento de Microsoft Intune asignada como no compatible
- Crear una directiva de cumplimiento de Microsoft Intune para iOS
- Crear una directiva de cumplimiento de Microsoft Intune para macOS
- Crear una directiva de cumplimiento de Microsoft Intune para Windows
- Crear un perfil de configuración de Microsoft Intune para Android
- Crear un perfil de configuración de Microsoft Intune para Android para trabajar
- Crear un perfil de configuración de Microsoft Intune para macOS
- Crear un perfil de configuración de Microsoft Intune para iOS
- Crear un perfil de configuración de Microsoft Intune para Windows
- Habilitar la detección de jailbreak mejorada en Microsoft Intune
- Requerir que todos los dispositivos sean revisados, tengan antivirus y firewalls habilitados
- Habilitar la integración de ATP de Windows Defender en Microsoft Intune
- Crear una directiva de Windows Information Protection para Microsoft Intune
- Requerir que todos los dispositivos tengan configuraciones de seguridad avanzada
- Revisar semanalmente el informe de dispositivos bloqueados

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a>Eliminación de acciones de mejora que no cumplen las expectativas para una medida fiable 

Para asegurarse de que la puntuación segura de Microsoft es significativa y que cada acción de mejora es medible y confiable, se quitan las siguientes acciones de mejora.

- Activar la grabación de datos de auditoría
- Descubra aplicaciones de TI de instantáneas arriesgadas y no compatibles
- Revisión de permisos & bloquear aplicaciones de OAuth arriesgadas conectadas a su entorno
- Configurar el control de versiones en las bibliotecas de documentos de SharePoint Online

### <a name="mfa-improvement-action-updates"></a>Actualizaciones de acciones de mejora de MFA

Para reflejar la necesidad de las empresas de garantizar la máxima seguridad al aplicar las directivas que funcionan con su negocio, la calificación segura de Microsoft es quitar tres acciones de mejora centradas alrededor de la autenticación multifactor y agregando dos.

Los tres que se quitarán:

- Registrar todos los usuarios para la autenticación multifactor
- Requerir MFA para todos los usuarios
- Requerir MFA para los roles privilegiados de Azure AD

Nuevas acciones de mejora agregadas:

- Asegurarse de que todos los usuarios puedan completar la autenticación multifactor para el acceso seguro
- Requerir MFA para roles administrativos

 Estas nuevas acciones de mejora requerirán el registro de los usuarios o administradores para la autenticación multifactor (MFA) en el directorio y el establecimiento del conjunto adecuado de directivas que se adapten a las necesidades de la organización. El objetivo principal es tener flexibilidad a la vez que se asegura de que todos los usuarios y administradores puedan autenticarse con varios factores o solicitudes de verificación de identidad basadas en riesgos. Esto puede tener la forma de tener varias directivas que apliquen decisiones en el ámbito o establecer los valores predeterminados de seguridad (desde el 16 de marzo) que permitan a Microsoft decidir cuándo debe desafiar a los usuarios para MFA.

### <a name="removing-review-improvement-actions"></a>Eliminación de acciones de mejora de "revisión"

Uno de los principios de la puntuación segura es que la puntuación debe estar estandarizada y ser fácil de relacionar con. Las acciones de mejora que no se pueden medir o realizar acciones han causado confusión. Una calificación segura de Microsoft solo tiene sentido cuando cada recomendación puede tener un efecto claro en la puntuación. Revisión las acciones de mejora no se miden en el mismo estándar que otras acciones de mejora.  

Por estos motivos, todas las acciones de mejora que requerían una cadencia de revisión se eliminarán temporalmente. No es necesario realizar ninguna acción en su parte.

## <a name="march-16th-2020"></a>16 de marzo de 2020

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>Eliminación de acciones de mejora que no cumplen con las expectativas para una medición fiable o que no proporcionan una representación útil de la postura de seguridad

Para asegurarse de que la puntuación segura de Microsoft es significativa y que cada acción de mejora es medible y confiable, se quitan las siguientes acciones de mejora.

- Almacenar documentos de usuario en OneDrive para la empresa
- Configurar las directivas de datos adjuntos seguros de Office 365 ATP
- Configurar vínculos seguros de Office 365 para comprobar direcciones URL
- No permitir la delegación de buzones
- Permitir vínculos de uso compartido de invitados anónimos para sitios y documentos
- Activar la consola de Cloud App Security

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a>Compatibilidad con los valores predeterminados de seguridad para acciones de mejora de Azure AD

La calificación segura de Microsoft actualizará las acciones de mejora para admitir los [valores predeterminados de seguridad en Azure ad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), que facilitan la protección de la organización con opciones de seguridad preconfiguradas para ataques comunes.

Afectará a las siguientes acciones de mejora:

- Asegurarse de que todos los usuarios puedan completar la autenticación multifactor para el acceso seguro
- Requerir MFA para roles administrativos
- Habilitar la Directiva para bloquear la autenticación heredada
