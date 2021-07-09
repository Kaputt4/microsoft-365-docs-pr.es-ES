---
title: Configurar el acceso condicional en Microsoft Defender para el extremo
description: Obtenga información sobre los pasos que debe realizar en Intune, Microsoft 365 Defender y Azure para implementar el acceso condicional
keywords: acceso condicional, condicional, acceso, riesgo de dispositivo, nivel de riesgo, integración, integración de Intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: 2c9462fa0d4be4d6ff78ba3e5db2cd4fa71fef0b
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339519"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a>Configurar el acceso condicional en Microsoft Defender para el extremo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

En esta sección se le guían todos los pasos que debe seguir para implementar correctamente el acceso condicional.

### <a name="before-you-begin"></a>Antes de empezar
>[!WARNING]
>Es importante tener en cuenta que los dispositivos registrados de Azure AD no se admiten en este escenario.</br>
>Solo se admiten dispositivos inscritos en Intune.


Debes asegurarte de que todos los dispositivos estén inscritos en Intune. Puede usar cualquiera de las siguientes opciones para inscribir dispositivos en Intune:


- Administrador de TI: para obtener más información sobre cómo habilitar la inscripción automática, [vea Windows Enrollment](/intune/windows-enroll#enable-windows-10-automatic-enrollment)
- Usuario final: para obtener más información sobre cómo inscribir el dispositivo Windows 10 en Intune, consulte Inscribir el [dispositivo Windows 10 en Intune](/intune/quickstart-enroll-windows-device)
- Alternativa de usuario final: para obtener más información sobre cómo unirse a un dominio de Azure AD, vea [How to: Plan your Azure AD join implementation](/azure/active-directory/devices/azureadjoin-plan).



Hay pasos que deberá seguir en Microsoft 365 Defender, el portal de Intune y el portal de Azure AD.

Es importante tener en cuenta los roles necesarios para tener acceso a estos portales e implementar el acceso condicional:
- **Microsoft 365 Defender:** deberá iniciar sesión en el portal con un rol de administrador global para activar la integración.
- **Intune:** deberá iniciar sesión en el portal con derechos de administrador de seguridad con permisos de administración. 
- **Portal de Azure AD:** deberá iniciar sesión como administrador global, administrador de seguridad o administrador de acceso condicional.


> [!NOTE]
> Necesitará un entorno Microsoft Intune, con Intune administrado y Azure AD unido a Windows 10 dispositivos.

Siga estos pasos para habilitar el acceso condicional:
- Paso 1: Activar la conexión Microsoft Intune desde Microsoft 365 Defender
- Paso 2: Activar la integración de Defender for Endpoint en Intune
- Paso 3: Crear la directiva de cumplimiento en Intune
- Paso 4: Asignar la directiva 
- Paso 5: Crear una directiva de acceso condicional de Azure AD


### <a name="step-1-turn-on-the-microsoft-intune-connection"></a>Paso 1: Activar la conexión Microsoft Intune conexión
1. En el panel de navegación, **seleccione Configuración**  >  **características avanzadas** generales  >    >  **Microsoft Intune**  >  **conexión**.
2. Alterna la Microsoft Intune a **On**.
3. Haga clic **en Guardar preferencias**.


### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a>Paso 2: Activar la integración de Defender for Endpoint en Intune
1. Inicie sesión en el [portal de Azure](https://portal.azure.com).
2. Seleccione **Cumplimiento de**  >  **dispositivos ATP de Microsoft Defender**.
3. Establece **Conectar Windows 10.0.15063+** en Protección contra amenazas avanzada de Microsoft Defender en **On**.
4. Haga clic en **Guardar**.


### <a name="step-3-create-the-compliance-policy-in-intune"></a>Paso 3: Crear la directiva de cumplimiento en Intune
1. En [Azure Portal,](https://portal.azure.com)seleccione **Todos los servicios**, filtre en **Intune** y **seleccione Microsoft Intune**.
2. Seleccione **Directivas de cumplimiento de**  >    >  **dispositivos Crear directiva**.
3. Escriba un **nombre** y **una descripción**.
4. En **Plataforma,** **seleccione Windows 10 y versiones posteriores**.
5. En la **configuración estado del** dispositivo, establece Requerir que el dispositivo esté en el nivel de amenaza del dispositivo o en el nivel **que** prefieras:

   - **Protegido:** este nivel es el más seguro. El dispositivo no puede tener amenazas existentes y seguir teniendo acceso a los recursos de la compañía. Si se encuentra alguna amenaza, el dispositivo se evalúa como no compatible.
   - **Bajo:** el dispositivo es compatible si solo existen amenazas de bajo nivel. Los dispositivos con niveles de amenazas medianos o altos no son compatibles.
   - **Medium:** el dispositivo es compatible si las amenazas encontradas en el dispositivo son bajas o medianas. Si se detectan amenazas de alto nivel, el dispositivo se determina como no compatible.
   - **Alto:** este nivel es el menos seguro y permite todos los niveles de amenazas. Por lo tanto, los dispositivos que tienen niveles de amenazas altos, medianos o bajos se consideran compatibles.

6. Seleccione **Aceptar** y **Crear** para guardar los cambios (y crear la directiva).

### <a name="step-4-assign-the-policy"></a>Paso 4: Asignar la directiva
1. En [Azure Portal,](https://portal.azure.com)seleccione **Todos los servicios**, filtre en **Intune** y **seleccione Microsoft Intune**.
2. Selecciona **Directivas de cumplimiento**  >  **de** dispositivos> la directiva de cumplimiento de Microsoft Defender para puntos de conexión.
3. Seleccione **Asignaciones**.
4. Incluya o excluya los grupos de Azure AD para asignarles la directiva.
5. Para implementar la directiva en los grupos, seleccione **Guardar**. Los dispositivos de usuario dirigidos por la directiva se evalúan para el cumplimiento.

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a>Paso 5: Crear una directiva de acceso condicional de Azure AD
1. En [Azure Portal,](https://portal.azure.com)abra **Azure Active Directory**  >  **Acceso condicional** Nueva  >  **directiva**.
2. Escriba un nombre **de directiva** y seleccione Usuarios **y grupos**. Use las opciones Incluir o Excluir para agregar los grupos para la directiva y seleccione **Listo**.
3. Selecciona **Aplicaciones en la** nube y elige qué aplicaciones proteger. Por ejemplo, elija **Seleccionar aplicaciones** y seleccione **Office 365 SharePoint Online** y **Office 365 Exchange Online**. Seleccione **Listo** para guardar los cambios.

4. Selecciona **Condiciones**  >  **Aplicaciones cliente para** aplicar la directiva a aplicaciones y exploradores. Por ejemplo, seleccione **Sí** y, a continuación, habilite **Explorador** y **Aplicaciones móviles y clientes de escritorio.** Seleccione **Listo** para guardar los cambios.

5. Selecciona **Conceder para** aplicar el acceso condicional en función del cumplimiento del dispositivo. Por ejemplo, seleccione **Conceder acceso Requerir** que el dispositivo se marque como  >  **compatible.** Elija **Seleccionar** para guardar los cambios.

6. Seleccione **Habilitar directiva** y, a **continuación, Crear** para guardar los cambios.

Para obtener más información, vea [Enforce compliance for Microsoft Defender for Endpoint with Conditional Access in Intune](/intune/advanced-threat-protection).

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-belowfoldlink)
