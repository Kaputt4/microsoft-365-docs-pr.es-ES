---
title: Configurar el acceso condicional en Microsoft Defender para el extremo
description: Obtenga información sobre los pasos que debe realizar en Intune, El Centro de seguridad de Microsoft Defender y Azure para implementar el acceso condicional
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
ms.openlocfilehash: e68a8c35fb1028fa8e60cf52a8e8bb411a534b19
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903783"
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


- Administrador de TI: para obtener más información sobre cómo habilitar la inscripción automática, consulta [Inscripción de Windows](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)
- Usuario final: para obtener más información sobre cómo inscribir el dispositivo Windows 10 en Intune, consulta Inscribir el dispositivo [Windows 10 en Intune](https://docs.microsoft.com/intune/quickstart-enroll-windows-device)
- Alternativa de usuario final: para obtener más información sobre cómo unirse a un dominio de Azure AD, vea [How to: Plan your Azure AD join implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan).



Hay pasos que deberá seguir en el Centro de seguridad de Microsoft Defender, el portal de Intune y el portal de Azure AD.

Es importante tener en cuenta los roles necesarios para tener acceso a estos portales e implementar el acceso condicional:
- **Centro de seguridad de Microsoft Defender:** deberá iniciar sesión en el portal con un rol de administrador global para activar la integración.
- **Intune:** deberá iniciar sesión en el portal con derechos de administrador de seguridad con permisos de administración. 
- **Portal de Azure AD:** deberá iniciar sesión como administrador global, administrador de seguridad o administrador de acceso condicional.


> [!NOTE]
> Necesitarás un entorno de Microsoft Intune, con Intune administrado y Azure AD unido a dispositivos Windows 10.

Siga estos pasos para habilitar el acceso condicional:
- Paso 1: Activar la conexión de Microsoft Intune desde el Centro de seguridad de Microsoft Defender
- Paso 2: Activar la integración de Defender for Endpoint en Intune
- Paso 3: Crear la directiva de cumplimiento en Intune
- Paso 4: Asignar la directiva 
- Paso 5: Crear una directiva de acceso condicional de Azure AD


### <a name="step-1-turn-on-the-microsoft-intune-connection"></a>Paso 1: Activar la conexión de Microsoft Intune
1. En el panel de navegación, seleccione **Configuración**  >  **Características avanzadas Conexión** de Microsoft  >  **Intune.**
2. Alterna la configuración de Microsoft Intune a **On**.
3. Haga clic **en Guardar preferencias**.


### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a>Paso 2: Activar la integración de Defender for Endpoint en Intune
1. Inicie sesión en el [Azure Portal](https://portal.azure.com).
2. Seleccione **Cumplimiento de**  >  **dispositivos ATP de Microsoft Defender**.
3. Establece **Conectar dispositivos Windows 10.0.15063+** a Protección contra amenazas avanzada de Microsoft Defender en **On**.
4. Haga clic en **Guardar**.


### <a name="step-3-create-the-compliance-policy-in-intune"></a>Paso 3: Crear la directiva de cumplimiento en Intune
1. En [Azure Portal,](https://portal.azure.com)seleccione **Todos los servicios**, filtre en **Intune** y seleccione **Microsoft Intune**.
2. Seleccione **Directivas de cumplimiento de**  >    >  **dispositivos Crear directiva**.
3. Escriba un **nombre** y **una descripción**.
4. En **Plataforma,** **selecciona Windows 10 y versiones posteriores.**
5. En la **configuración estado del** dispositivo, establece Requerir que el dispositivo esté en el nivel de amenaza del dispositivo o en el nivel **que** prefieras:

   - **Protegido:** este nivel es el más seguro. El dispositivo no puede tener amenazas existentes y seguir teniendo acceso a los recursos de la compañía. Si se encuentra alguna amenaza, el dispositivo se evalúa como no compatible.
   - **Bajo:** el dispositivo es compatible si solo existen amenazas de bajo nivel. Los dispositivos con niveles de amenazas medianos o altos no son compatibles.
   - **Medium:** el dispositivo es compatible si las amenazas encontradas en el dispositivo son bajas o medianas. Si se detectan amenazas de alto nivel, el dispositivo se determina como no compatible.
   - **Alto:** este nivel es el menos seguro y permite todos los niveles de amenazas. Por lo tanto, los dispositivos que tienen niveles de amenazas altos, medianos o bajos se consideran compatibles.

6. Seleccione **Aceptar** y **Crear** para guardar los cambios (y crear la directiva).

### <a name="step-4-assign-the-policy"></a>Paso 4: Asignar la directiva
1. En [Azure Portal,](https://portal.azure.com)seleccione **Todos los servicios**, filtre en **Intune** y seleccione **Microsoft Intune**.
2. Selecciona **Directivas de cumplimiento**  >  **de** dispositivos> la directiva de cumplimiento de Microsoft Defender para puntos de conexión.
3. Seleccione **Asignaciones**.
4. Incluya o excluya los grupos de Azure AD para asignarles la directiva.
5. Para implementar la directiva en los grupos, seleccione **Guardar**. Los dispositivos de usuario dirigidos por la directiva se evalúan para el cumplimiento.

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a>Paso 5: Crear una directiva de acceso condicional de Azure AD
1. En [Azure Portal,](https://portal.azure.com)abra **Azure Active Directory** Acceso  >  **condicional**  >  **Nueva directiva**.
2. Escriba un nombre **de directiva** y seleccione Usuarios **y grupos**. Use las opciones Incluir o Excluir para agregar los grupos para la directiva y seleccione **Listo**.
3. Selecciona **Aplicaciones en la** nube y elige qué aplicaciones proteger. Por ejemplo, elija **Seleccionar aplicaciones** y seleccione **Office 365 SharePoint Online** y Office **365 Exchange Online**. Seleccione **Listo** para guardar los cambios.

4. Selecciona **Condiciones**  >  **Aplicaciones cliente para** aplicar la directiva a aplicaciones y exploradores. Por ejemplo, seleccione **Sí** y, a continuación, habilite **Explorador** y **Aplicaciones móviles y clientes de escritorio.** Seleccione **Listo** para guardar los cambios.

5. Selecciona **Conceder para** aplicar el acceso condicional en función del cumplimiento del dispositivo. Por ejemplo, seleccione **Conceder acceso Requerir** que el dispositivo se marque como  >  **compatible.** Elija **Seleccionar** para guardar los cambios.

6. Seleccione **Habilitar directiva** y, a **continuación, Crear** para guardar los cambios.

Para obtener más información, vea [Enforce compliance for Microsoft Defender for Endpoint with Conditional Access in Intune](https://docs.microsoft.com/intune/advanced-threat-protection).

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-belowfoldlink)
