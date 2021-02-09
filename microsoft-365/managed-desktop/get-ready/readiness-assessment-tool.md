---
title: Herramientas de evaluación de preparación
description: Explica las dos herramientas, las comprobaciones que ejecutan y el significado de los resultados
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1a00f7d5fb37cc9eea3f9454d473703084960864
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142938"
---
# <a name="readiness-assessment-tools"></a>Herramientas de evaluación de preparación

Para una experiencia lo más fluida posible al inscribirse en el Escritorio administrado de Microsoft, hay opciones de configuración y otros parámetros que debe establecer con antelación, así como ciertos requisitos de dispositivo y red que cumplir. Una herramienta, a la que se accede a través del portal de administración de Escritorio administrado de Microsoft, comprueba la configuración relacionada con la administración. Otra herramienta, que se puede descargar, comprueba los requisitos de dispositivo individuales y la configuración de red. Puedes usar estas herramientas para comprobar esa configuración y recibir pasos detallados para corregir los que no sean correctos.

## <a name="downloadable-readiness-assessment-checker-for-devices-and-network"></a>Herramienta de comprobación de evaluación de preparación descargable para dispositivos y red

Para obtener más información sobre cómo usar el herramienta de comprobación de evaluación de preparación descargable, consulta El herramienta de comprobación de evaluación [de](readiness-assessment-downloadable.md)preparación descargable.

## <a name="online-readiness-assessment-tool-for-management-settings"></a>Herramienta de evaluación de preparación en línea para la configuración de administración

La herramienta en línea comprueba la configuración de Microsoft Endpoint Manager (en concreto, Microsoft Intune), Azure Active Directory (Azure AD) y Microsoft 365 para asegurarse de que funcionarán con el escritorio administrado de Microsoft. Escritorio administrado de Microsoft conserva los datos asociados con estas comprobaciones durante 12 meses después de la última vez que se ejecuta una comprobación en la organización de Azure AD (inquilino). Después de 12 meses, lo conservamos en formato no identificado. Puedes elegir eliminar los datos que recopilamos.

Cualquiera con al menos el rol lector global o administrador de Intune podrá ejecutar esta herramienta, pero dos de las comprobaciones[(las](readiness-assessment-fix.md#conditional-access-policies) directivas de acceso condicional y la autenticación [multifactor](readiness-assessment-fix.md#multifactor-authentication) requieren permisos adicionales.
 
La herramienta de evaluación comprueba estos elementos:

## <a name="microsoft-intune-settings"></a>Configuración de Microsoft Intune

|Cheque  |Description  |
|---------|---------|
|Perfil de implementación de Autopilot     | Comprueba que la asignación del perfil de implementación de Autopilot no se aplica a todos los dispositivos (el perfil no debe asignarse a ningún dispositivo de Escritorio administrado de Microsoft).        |
|Conectores de certificados     | Comprueba el estado de los conectores de certificado para asegurarse de que están activos   |
|Acceso condicional     | Comprueba que las directivas de acceso condicional no están  asignadas a todos los usuarios (las directivas de acceso condicional no deben asignarse a las cuentas de servicio de Escritorio administrado de Microsoft).    |
|Directivas de cumplimiento de dispositivos     | Comprueba que las directivas de cumplimiento de Intune  no están asignadas a todos los usuarios (las directivas no deben asignarse a ningún dispositivo de Escritorio administrado de Microsoft).    |
|Perfiles de configuración de dispositivos     | Confirma que los perfiles de configuración no están asignados  a todos los usuarios ni a todos los dispositivos (los perfiles de configuración no deben asignarse a ningún dispositivo de Escritorio administrado de Microsoft).     |
|Restricciones de tipo de dispositivo     | Comprueba que los dispositivos Windows 10 de la organización pueden inscribirse en Intune        |
|Página de estado de inscripción     | Confirma que la página de estado de inscripción no está habilitada      |
|Inscripción de Intune     | Comprueba que los dispositivos Windows 10 de la organización de Azure AD se inscribieron automáticamente en Intune         |
|Microsoft Store para Empresas     | Confirma que la Microsoft Store para Empresas está habilitada y sincronizada con Intune        |
|Autenticación multifactor | Comprueba que la autenticación multifactor no se aplica a las cuentas de servicio de Escritorio administrado de Microsoft.
|Scripts de PowerShell     | Comprueba que Windows PowerShell scripts no *se* asignan de forma que se dirigirían a dispositivos de Escritorio administrado de Microsoft    |
|Región     | Comprueba que su región es compatible con el Escritorio administrado de Microsoft        |
|Líneas base de seguridad     | Comprueba que el perfil de línea base de seguridad no  está destinado a todos los usuarios ni a todos los dispositivos (las directivas de línea base de seguridad no deben dirigirse a ningún dispositivo de Escritorio administrado de Microsoft).       |
|Aplicaciones de Windows     | Revisar qué aplicaciones desea asignar a los dispositivos de Escritorio administrado de Microsoft      |
|Windows Hello para empresas     | Comprueba que Windows Hello para empresas está habilitado        |
|Anillo de actualización de Windows 10     | Comprueba que la directiva "Anillo de actualización de Windows 10" de Intune  no está destinada a todos los usuarios ni a todos los dispositivos (la directiva no debe dirigirse a ningún dispositivo de Escritorio administrado de Microsoft).     |


## <a name="azure-active-directory-settings"></a>Configuración de Azure Active Directory

|Cheque  |Description  |
|---------|---------|
|Suscripciones "ad hoc" para Enterprise State Roaming     | Indica cómo comprobar una configuración que (si se establece en "false") podría impedir que enterprise State Roaming funcione correctamente  |
|Enterprise State Roaming     | Aconseja cómo comprobar que enterprise State Roaming está habilitado       |
|Licencias     | Comprueba que ha obtenido las [licencias necesarias](prerequisites.md#more-about-licenses)         |
|Autenticación multifactor     | Comprueba que la autenticación multifactor no se aplica a todos los usuarios (la autenticación multifactor no se debe aplicar accidentalmente a las cuentas de servicio de Escritorio administrado de Microsoft).|
|Nombres de cuenta de seguridad   | Comprueba que ningún nombre de usuario entre en conflicto con los que Microsoft Managed Desktop reserva para su propio uso        |
|Roles de administrador de seguridad     | Confirma que los usuarios con roles lector de seguridad, operador de seguridad o lector global tienen asignados esos roles en Microsoft Defender para endpoint         |
|Valores predeterminados de seguridad | Comprueba si la organización de Azure AD tiene habilitados los valores predeterminados de seguridad en Azure Active Directory |
|Autoservicio de restablecimiento de contraseña     | Confirma que el restablecimiento de contraseña de autoservicio está habilitado        |
|Rol de usuario estándar     | Comprueba que los usuarios son usuarios estándar y no tienen derechos de administrador local         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a>Configuración de Aplicaciones de Microsoft 365 para empresas

|Cheque  |Description  |
|---------|---------|
|OneDrive para la Empresa     | Comprueba si OneDrive para la Empresa usa la configuración no compatible.        |


Para cada comprobación, la herramienta mostrará uno de los cuatro resultados posibles:


|Resultado  |Significado  |
|---------|---------|
|Listo     | No se requiere ninguna acción antes de completar la inscripción.        |
|Aviso    | Siga los pasos de la herramienta para obtener la mejor experiencia con la inscripción y para los usuarios. Puedes *completar* la inscripción, pero debes solucionar estos problemas antes de implementar el primer dispositivo.        |
|No preparado | *Si no* solucionas estos problemas, se producirá un error en la inscripción. Siga los pasos de la herramienta para resolverlos.        |
|Error | El rol de Azure Active Director (AD) que está usando no tiene permisos suficientes para ejecutar esta comprobación. |

## <a name="after-enrollment"></a>Después de la inscripción

Después de completar la inscripción en el Escritorio administrado de Microsoft, recuerda volver atrás y ajustar determinadas opciones de configuración de Intune y Azure AD. Para obtener más información, consulta [Ajustar la configuración después de la inscripción.](../get-started/conditional-access.md)
