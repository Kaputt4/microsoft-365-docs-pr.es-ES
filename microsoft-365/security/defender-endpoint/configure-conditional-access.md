---
title: Configuración del acceso condicional en Microsoft Defender para punto de conexión
description: Obtenga información sobre los pasos que debe realizar en Intune, Microsoft 365 Defender y Azure para implementar el acceso condicional.
keywords: acceso condicional, condicional, acceso, riesgo de dispositivo, nivel de riesgo, integración, integración de Intune
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: a565fc87c538fa6f9f590a4037ff9c346118c3cf
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67680191"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a>Configuración del acceso condicional en Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

Esta sección le guía por todos los pasos que debe seguir para implementar correctamente el acceso condicional.

## <a name="before-you-begin"></a>Antes de empezar

> [!WARNING]
> Es importante tener en cuenta que los dispositivos registrados en Azure AD no se admiten en este escenario.</br>
> Solo se admiten Intune dispositivos inscritos.

Debe asegurarse de que todos los dispositivos están inscritos en Intune. Puede usar cualquiera de las siguientes opciones para inscribir dispositivos en Intune:

- Administración de TI: para obtener más información sobre cómo habilitar la inscripción automática, vea [Inscripción de Windows](/intune/windows-enroll#enable-windows-10-automatic-enrollment).
- Usuario final: para obtener más información sobre cómo inscribir el dispositivo Windows 10 y Windows 11 en Intune, consulte [Inscripción del dispositivo Windows 10 en Intune](/intune/quickstart-enroll-windows-device)
- Alternativa al usuario final: para obtener más información sobre cómo unirse a un dominio de Azure AD, consulte [How to: Plan your Azure AD join implementation (Cómo: Planear la implementación de unión a Azure AD](/azure/active-directory/devices/azureadjoin-plan)).

Hay pasos que debe seguir en Microsoft 365 Defender, el portal de Intune y el portal de Azure AD.

Es importante tener en cuenta los roles necesarios para acceder a estos portales e implementar el acceso condicional:

- **Microsoft 365 Defender**: deberá iniciar sesión en el portal con un rol de administrador global para activar la integración.
- **Intune**: deberá iniciar sesión en el portal con derechos de administrador de seguridad con permisos de administración.
- **Portal de Azure AD** : tendrá que iniciar sesión como administrador global, administrador de seguridad o administrador de acceso condicional.

> [!NOTE]
> Necesitará un entorno de Microsoft Intune, con dispositivos Intune administrados y unidos a Azure AD Windows 10 y Windows 11.

Siga estos pasos para habilitar el acceso condicional:

- Paso 1: Activar la conexión Microsoft Intune desde Microsoft 365 Defender
- Paso 2: Activar la integración de Defender para punto de conexión en Intune
- Paso 3: Crear la directiva de cumplimiento en Intune
- Paso 4: Asignar la directiva 
- Paso 5: Creación de una directiva de acceso condicional de Azure AD

### <a name="step-1-turn-on-the-microsoft-intune-connection"></a>Paso 1: Activar la conexión Microsoft Intune

1. En el panel de navegación, seleccione **Configuración** \> **Puntos de conexión** **Características** \> avanzadas \> **generales** \> **Microsoft Intune conexión**.
2. Cambie el valor de Microsoft Intune a **Activado**.
3. Haga clic en **Guardar preferencias**.

### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a>Paso 2: Activar la integración de Defender para punto de conexión en Intune

1. Inicie sesión en el [portal de Azure](https://portal.azure.com).
2. Seleccione **Cumplimiento de dispositivos** \> **ATP de Microsoft Defender**.
3. Establezca **Conectar dispositivos Windows 10.0.15063+ en Protección contra amenazas avanzada de Microsoft Defender** **en Activado**.
4. Haga clic en **Guardar**.

### <a name="step-3-create-the-compliance-policy-in-intune"></a>Paso 3: Crear la directiva de cumplimiento en Intune

1. En el [Azure Portal](https://portal.azure.com), seleccione **Todos los servicios**, filtre por **Intune** y seleccione **Microsoft Intune**.
2. Seleccione **Directivas de cumplimiento** \> **de** \> **dispositivos Crear directiva**.
3. Escriba un **nombre** y **una descripción**.
4. En **Plataforma**, seleccione **Windows 10 y versiones posteriores**.
5. En la configuración **de Estado** del dispositivo, establezca **Requerir que el dispositivo esté en el nivel de amenaza del dispositivo o en el nivel de amenaza del dispositivo** en el nivel que prefiera:

   - **Protegido**: este nivel es el más seguro. El dispositivo no puede tener ninguna amenaza existente y seguir teniendo acceso a los recursos de la empresa. Si se encuentra alguna amenaza, el dispositivo se clasificará como no conforme.
   - **Bajo**: el dispositivo se evalúa como compatible solo si hay amenazas de nivel bajo. Los dispositivos con niveles de amenaza medio o alto no son compatibles.
   - **Medio**: el dispositivo se evalúa como compatible si las amenazas que se encuentran en él son de nivel bajo o medio. Si se detectan amenazas de nivel alto, se determinará que el dispositivo no es compatible.
   - **Alto**: este nivel es el menos seguro y permite todos los niveles de amenaza. Por lo tanto, los dispositivos que tienen niveles de amenaza altos, medios o bajos se consideran compatibles.

6. Seleccione **Aceptar** y **Crear** para guardar los cambios (y crear la directiva).

### <a name="step-4-assign-the-policy"></a>Paso 4: Asignar la directiva

1. En el [Azure Portal](https://portal.azure.com), seleccione **Todos los servicios**, filtre por **Intune** y seleccione **Microsoft Intune**.
2. Seleccione **Directivas de cumplimiento** \> de dispositivos> seleccione la directiva de cumplimiento de Microsoft Defender para punto de conexión.
3. Seleccione **Asignaciones**.
4. Incluya o excluya los grupos de Azure AD para asignarles la directiva.
5. Para implementar la directiva en los grupos, seleccione **Guardar**. Los dispositivos de usuario de destino de la directiva se evalúan para el cumplimiento.

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a>Paso 5: Creación de una directiva de acceso condicional de Azure AD

1. En el [Azure Portal](https://portal.azure.com), abra **nueva directiva** **de acceso condicional de** \> **Azure Active Directory**\>.
2. Escriba un **nombre de** directiva y seleccione **Usuarios y grupos**. Utilice las opciones Incluir o Excluir para agregar los grupos para la directiva y seleccione **Listo**.
3. Seleccione **Aplicaciones** en la nube y elija qué aplicaciones proteger. Por ejemplo, elija **Seleccionar aplicaciones** y seleccione **Office 365 SharePoint Online** y **Office 365 Exchange Online**. Seleccione **Listo** para guardar los cambios.

4. Seleccione **Condiciones Aplicaciones** \> **cliente** para aplicar la directiva a aplicaciones y exploradores. Por ejemplo, seleccione **Sí** y habilite **Explorador** y **Aplicaciones móviles y aplicaciones de escritorio**. Seleccione **Listo** para guardar los cambios.

5. Seleccione **Conceder** para aplicar el acceso condicional basado en el cumplimiento del dispositivo. Por ejemplo, seleccione **Conceder acceso** \> **Requerir que el dispositivo se marque como compatible**. Elija **Seleccionar** para guardar los cambios.

6. Seleccione **Habilitar directiva** y luego **crear** para guardar los cambios.

> [!NOTE]
> Puede usar la aplicación Microsoft Defender para punto de conexión junto con la directiva de aplicación cliente aprobada en Intune para establecer directivas de cumplimiento de dispositivos y acceso condicional. No se requiere ninguna exclusión para la aplicación Microsoft Defender para punto de conexión al configurar el acceso condicional. Aunque Microsoft Defender para punto de conexión en Android & iOS (id. de aplicación- dd47d17a-3194-4d86-bfd5-c6ae6f5651e3) no es una aplicación aprobada, tiene permiso para notificar la posición de seguridad del dispositivo. Este permiso permite el flujo de información de cumplimiento al acceso condicional.
> Tenga en cuenta que este cambio estará disponible a partir del 30 de septiembre de 2022.

Para obtener más información, consulte [Exigencia del cumplimiento de Microsoft Defender para punto de conexión con acceso condicional en Intune](/intune/advanced-threat-protection).

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-conditionalaccess-belowfoldlink)
