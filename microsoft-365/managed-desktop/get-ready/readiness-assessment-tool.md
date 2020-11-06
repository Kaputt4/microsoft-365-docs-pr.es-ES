---
title: Herramienta de evaluación de preparación
description: Explica las comprobaciones que ejecuta la herramienta y el significado de los resultados.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 347266f71dada3de1bbd9b1434cb1e6628249147
ms.sourcegitcommit: 24826e1b61e7aace12fc9e8ae84ae3e760658b50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2020
ms.locfileid: "48931929"
---
# <a name="readiness-assessment-tool"></a>Herramienta de evaluación de preparación

Para obtener la mejor experiencia posible al inscribirse en el escritorio administrado de Microsoft, hay varias opciones de configuración y otros parámetros que debe establecer antes de tiempo. Puede usar esta herramienta para comprobar la configuración y recibir los pasos detallados para corregir los que no sean correctos.

La herramienta comprueba la configuración de Microsoft Endpoint Manager (en concreto, Microsoft Intune), Azure Active Directory (Azure AD) y Microsoft 365 para garantizar que funcionarán con el escritorio administrado por Microsoft. Microsoft Managed Desktop mantiene los datos asociados con estas comprobaciones durante 12 meses después de la última vez que ejecutó una protección en su organización (inquilino) de Azure AD. Después de 12 meses, lo mantenemos en un formulario de identificación.  Puede optar por eliminar los datos recopilados.

Cualquier usuario con al menos el rol de administrador de Intune podrá ejecutar esta herramienta, pero dos de las comprobaciones (los[conectores de certificados](readiness-assessment-fix.md#certificate-connectors) y [la autenticación multifactor](readiness-assessment-fix.md#multi-factor-authentication) requieren permisos adicionales.
 
La herramienta de evaluación comprueba estos elementos:

## <a name="microsoft-intune-settings"></a>Configuración de Microsoft Intune

|Check  |Descripción  |
|---------|---------|
|Perfil de implementación de piloto automático     | Comprueba que la asignación del perfil de implementación de piloto automático no se aplica a todos los dispositivos (el perfil *no* debe asignarse a ningún dispositivo de escritorio administrado por Microsoft).       |
|Conectores de certificados     | Comprueba el estado de los conectores de certificado para asegurarse de que están activos.   |
|Acceso condicional     | Comprueba que las directivas de acceso condicional no se asignan a todos los usuarios (las directivas de acceso condicional *no* deben asignarse a las cuentas de servicio de escritorio administradas de Microsoft).    |
|Directivas de cumplimiento de dispositivos     | Comprueba que las directivas de cumplimiento de Intune no se asignan a todos los usuarios (las directivas *no* deben asignarse a ningún dispositivo de escritorio administrado por Microsoft).    |
|Perfiles de configuración de dispositivos     | Confirma que los perfiles de configuración no se asignan a todos los usuarios o todos los dispositivos (los perfiles de configuración *no* deben asignarse a ningún dispositivo de escritorio administrado por Microsoft).     |
|Restricciones de tipo de dispositivo     | Comprueba que los dispositivos Windows 10 de su organización puedan inscribirse en Intune        |
|Página de estado de inscripción     | Confirma que la página de estado de inscripción no está habilitada      |
|Inscripción de Intune     | Comprueba que los dispositivos Windows 10 de la organización de Azure AD se inscriben automáticamente en Intune.         |
|Microsoft Store para Empresas     | Confirma que Microsoft Store for Business está habilitado y sincronizado con Intune        |
|Autenticación multifactor | Comprueba que la autenticación multifactor no se aplica a las cuentas de servicio de escritorio administradas de Microsoft.
|Scripts de PowerShell     | Comprueba que los scripts de Windows PowerShell *no* se asignan de una manera que se dirija a los dispositivos de escritorio administrados por Microsoft    |
|Región     | Comprueba que la región sea compatible con el escritorio administrado por Microsoft        |
|Líneas de base de seguridad     | Comprueba que el perfil de línea base de seguridad no tiene como objetivo todos los usuarios o todos los dispositivos (las directivas de línea de base de seguridad *no* deben dirigir ningún dispositivo de escritorio administrado por Microsoft).       |
|Aplicaciones de Windows     | Revise qué aplicaciones desea asignar a los dispositivos de escritorio administrados por Microsoft      |
|Windows Hello para empresas     | Comprueba que Windows Hello para empresas está habilitado        |
|Anillo de actualización de Windows 10     | Comprueba que la Directiva "Windows 10 Update Ring" de Intune no está destinada a todos los usuarios o todos los dispositivos (la directiva *no* debe dirigirse a ningún dispositivo de escritorio administrado por Microsoft).     |


## <a name="azure-active-directory-settings"></a>Configuración de Azure Active Directory

|Check  |Descripción  |
|---------|---------|
|Suscripciones "ad hoc" para la itinerancia del estado de la empresa     | Aconseja comprobar una opción que (si se establece en "false") impedir que la itinerancia del estado de la empresa funcione correctamente  |
|Enterprise State Roaming     | Aconseja comprobar que la itinerancia del estado de la empresa está habilitada       |
|Licencias     | Comprueba que ha obtenido las [licencias](prerequisites.md#more-about-licenses) necesarias         |
|Autenticación multifactor     | Comprueba que la autenticación multifactor no se aplica a todos los usuarios (la autenticación multifactor no se debe aplicar por accidente a las cuentas de servicio de escritorio administradas de Microsoft).|
|Nombres de cuenta de seguridad   | Comprueba que ningún nombre de usuario entra en conflicto con los que Microsoft administró las reservas de escritorio para uso propio.        |
|Roles de administrador de seguridad     | Confirma que los usuarios con roles de lector de seguridad, operador de seguridad o lector global han sido asignados a estos roles en Microsoft defender para el punto de conexión.         |
|Valores predeterminados de seguridad | Comprueba si la organización de Azure AD tiene los valores predeterminados de seguridad habilitados en Azure Active Directory |
|Autoservicio de restablecimiento de contraseña     | Confirma que el restablecimiento de contraseña de autoservicio está habilitado        |
|Rol de usuario estándar     | Verifica que los usuarios son usuarios estándar y no tienen derechos de administrador local         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a>Configuración de Microsoft 365 apps for Enterprise

|Check  |Descripción  |
|---------|---------|
|OneDrive para la Empresa     | Comprueba si OneDrive para la empresa usa una configuración no admitida.        |


Para cada comprobación, la herramienta notificará uno de los cuatro resultados posibles:


|Resultado  |Significado  |
|---------|---------|
|Listo     | No es necesario realizar ninguna acción antes de completar la inscripción.        |
|Consejo    | Siga los pasos de la herramienta para obtener la mejor experiencia con la inscripción y para los usuarios. *Puede* completar la inscripción, pero debe solucionar estos problemas antes de implementar el primer dispositivo.        |
|No preparado | *Se producirá un error* en la inscripción si no soluciona estos problemas. Siga los pasos de la herramienta para resolverlos.        |
|Error | El rol de Azure Active Director (AD) que está usando no tiene permisos suficientes para ejecutar esta comprobación. |
