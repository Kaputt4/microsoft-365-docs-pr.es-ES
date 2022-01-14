---
title: Herramientas de evaluación de preparación
description: Explica las dos herramientas, las comprobaciones que ejecutan y el significado de los resultados
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: 866cebcf036c3b70470379139603a5addadb5b95
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2022
ms.locfileid: "62035587"
---
# <a name="readiness-assessment-tools"></a>Herramientas de evaluación de preparación

Para obtener la experiencia más fluida posible al inscribirse en Microsoft Managed Desktop, hay opciones de configuración y otros parámetros que debes establecer con antelación y ciertos requisitos de dispositivo y red que debes cumplir. Una herramienta, a la que se accede a través del portal de administración de Escritorio administrado de Microsoft, comprueba la configuración relacionada con la administración. Otra herramienta, que se puede descargar, comprueba los requisitos individuales del dispositivo y la configuración de red. Puede usar estas herramientas para comprobar esa configuración y recibir pasos detallados para corregir cualquier que no sea correcto.

## <a name="downloadable-readiness-assessment-checker-for-devices-and-network"></a>Control de evaluación de preparación descargable para dispositivos y red

Para obtener más información sobre cómo usar el control de evaluación de preparación descargable, vea [Downloadable readiness assessment checker](readiness-assessment-downloadable.md).

## <a name="online-readiness-assessment-tool-for-management-settings"></a>Herramienta de evaluación de preparación en línea para la configuración de administración

La [](https://aka.ms/mmdart) herramienta en línea comprueba la configuración de Microsoft Endpoint Manager (específicamente, Microsoft Intune), Azure Active Directory (Azure AD) y Microsoft 365 para asegurarse de que funcionarán con Microsoft Managed Desktop. Microsoft Managed Desktop conserva los datos asociados a estas comprobaciones durante 12 meses después de la última vez que ejecute una comprobación en su Azure AD (inquilino). Después de 12 meses, lo conservamos en forma no identificada. Puede elegir eliminar los datos que recopilamos.

Cualquiera que tenga al menos el rol Lector global o Administrador de Intune podrá ejecutar esta herramienta, pero dos de las comprobaciones[(las](readiness-assessment-fix.md#conditional-access-policies) directivas de acceso condicional y la autenticación [multifactor](readiness-assessment-fix.md#multifactor-authentication) requieren permisos adicionales).

> [!IMPORTANT]  
> La herramienta de evaluación de preparación en línea le ayuda a comprobar su preparación para inscribirse en Microsoft Managed Desktop por primera vez. Si su organización ya está registrada en Microsoft Managed Desktop, no use esta herramienta.

La herramienta de evaluación comprueba estos elementos:

## <a name="microsoft-intune-settings"></a>Microsoft Intune configuración

|Cheque  |Descripción  |
|---------|---------|
|Perfil de implementación de Autopilot     | Comprueba que la asignación del perfil de implementación de Autopilot no se aplica a todos los dispositivos (el perfil no debe asignarse a ningún dispositivo de Escritorio administrado de Microsoft).        |
|Conectores de certificado     | Comprueba el estado de los conectores de certificado para asegurarse de que están activos   |
|Acceso condicional     | Comprueba que las directivas de acceso condicional no están  asignadas a todos los usuarios (las directivas de acceso condicional no deben asignarse a cuentas de servicio de Escritorio administrado de Microsoft).    |
|Directivas de cumplimiento de dispositivos     | Comprueba que las directivas de cumplimiento de Intune  no están asignadas a todos los usuarios (las directivas no deben asignarse a ningún dispositivo de Escritorio administrado de Microsoft).    |
|Perfiles de configuración de dispositivos     | Confirma que los perfiles de configuración no están asignados  a todos los usuarios ni a todos los dispositivos (los perfiles de configuración no deben asignarse a ningún dispositivo de Escritorio administrado de Microsoft).     |
|Restricciones de tipo de dispositivo     | Comprueba que Windows 10 dispositivos de la organización pueden inscribirse en Intune        |
|Página de estado de inscripción     | Confirma que la página de estado de inscripción no está habilitada      |
|Con una inscripción de Intune     | Comprueba que los Windows 10 de la organización Azure AD se inscribieron automáticamente en Intune         |
|Microsoft Store para Empresas     | Confirma que Microsoft Store para Empresas está habilitado y sincronizado con Intune        |
|Autenticación multifactor | Comprueba que la autenticación multifactor no se aplica a las cuentas de servicio de Escritorio administrado de Microsoft.
|Scripts de PowerShell     | Comprueba que Windows PowerShell scripts no *están* asignados de una manera que se dirigiría a dispositivos de Escritorio administrado de Microsoft    |
|Región     | Comprueba que su región es compatible con Microsoft Managed Desktop        |
|Líneas base de seguridad     | Comprueba que el perfil de línea base de seguridad no  está dirigido a todos los usuarios o todos los dispositivos (las directivas de línea base de seguridad no deben dirigirse a ningún dispositivo de Escritorio administrado de Microsoft).       |
|Windows aplicaciones     | Revisar qué aplicaciones quieres asignar a dispositivos de Escritorio administrado de Microsoft      |
|Windows Hello para empresas     | Comprueba que Windows Hello para empresas está habilitada        |
|Windows 10 de actualización     | Comprueba que la directiva de "anillo de actualización Windows 10" de Intune no está  dirigida a todos los usuarios ni a todos los dispositivos (la directiva no debe dirigirse a ningún dispositivo de Escritorio administrado de Microsoft).     |

## <a name="azure-active-directory-settings"></a>Azure Active Directory configuración

|Cheque  |Descripción  |
|---------|---------|
|Suscripciones "ad hoc" para Enterprise itinerancia de estado     | Aconseja comprobar una configuración que (si se establece en "false") podría impedir que Enterprise estado móvil funcione correctamente  |
|Enterprise State Roaming     | Aconseja cómo comprobar si Enterprise itinerancia de estado está habilitada       |
|Licencias     | Comprueba que ha obtenido las [licencias necesarias](prerequisites.md#more-about-licenses)         |
|Autenticación multifactor     | Comprueba que la autenticación multifactor no se aplica a todos los usuarios (la autenticación multifactor no debe aplicarse accidentalmente a las cuentas de servicio de Escritorio administrado de Microsoft).|
|Nombres de cuenta de seguridad   | Comprueba que ningún nombre de usuario entre en conflicto con los que Microsoft Managed Desktop reserva para su propio uso        |
|Roles de administrador de seguridad     | Confirma que los usuarios con roles de Lector de seguridad, Operador de seguridad o Lector global se han asignado esos roles en Microsoft Defender para endpoint         |
|Valores predeterminados de seguridad | Comprueba si su Azure AD tiene habilitados los valores predeterminados de seguridad en Azure Active Directory |
|Restablecimiento de contraseñas de autoservicio     | Confirma que el restablecimiento de contraseñas de autoservicio está habilitado        |
|Rol de usuario estándar     | Comprueba que los usuarios son usuarios estándar y que no tienen derechos de administrador local         |

## <a name="microsoft-365-apps-for-enterprise-settings"></a>Aplicaciones Microsoft 365 para empresas configuración

|Cheque  |Descripción  |
|---------|---------|
|OneDrive para la Empresa     | Comprueba si OneDrive para la Empresa está usando la configuración no compatible.        |

Para cada comprobación, la herramienta mostrará uno de los cuatro resultados posibles:

|Resultado  |Significado  |
|---------|---------|
|Listo     | No se requiere ninguna acción antes de completar la inscripción.        |
|Advertencia    | Siga los pasos de la herramienta para obtener la mejor experiencia con la inscripción y para los usuarios. Puedes *completar* la inscripción, pero debes solucionar estos problemas antes de implementar el primer dispositivo.        |
|No preparado | *La inscripción producirá un* error si no se solucionan estos problemas. Siga los pasos de la herramienta para resolverlos.        |
|Error | El rol de Azure Active Director (AD) que está usando no tiene permiso suficiente para ejecutar esta comprobación. |

## <a name="after-enrollment"></a>Después de la inscripción

Después de completar la inscripción en Microsoft Managed Desktop, recuerda volver atrás y ajustar ciertas opciones de Configuración de Intune Azure AD configuración. Para obtener más información, vea [Ajustar la configuración después de la inscripción.](../get-started/conditional-access.md)

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>Pasos para prepararse para El escritorio administrado de Microsoft

1. Revisar los [requisitos previos del Escritorio administrado de Microsoft](prerequisites.md)
2. Ejecute herramientas de evaluación de preparación (este artículo).
3. Comprar el [Portal de empresa](../get-started/company-portal.md).
4. Revisar los [requisitos previos para las cuentas de invitado](guest-accounts.md).
5. Comprobar la [configuración de red](network.md).
6. [Preparar los certificados y perfiles de red](certs-wifi-lan.md).
7. [Preparar el acceso de usuario a los datos](authentication.md).
8. [Preparar las aplicaciones](apps.md).
9. [Preparar las unidades asignadas](mapped-drives.md).
10. [Preparar los recursos de impresión](printing.md).
11. [Nombres del dispositivo](address-device-names.md) de dirección.
