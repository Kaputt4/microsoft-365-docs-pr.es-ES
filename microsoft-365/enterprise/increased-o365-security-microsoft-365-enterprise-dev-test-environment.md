---
title: Mayor seguridad de Microsoft 365 para el entorno de prueba de Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-security-compliance
ms.custom:
- Ent_TLGs
- admindeeplinkMAC
- admindeeplinkDEFENDER
- admindeeplinkSPO
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use esta guía de laboratorio de pruebas para habilitar la configuración de seguridad adicional de Microsoft 365 en el entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: 83bef240651f86c1a5e357fa2883a730e7da0969
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68208884"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a>Mayor seguridad de Microsoft 365 para el entorno de prueba de Microsoft 365 para empresas

*Esta guía de laboratorio de pruebas solo se puede usar para Microsoft 365 para entornos de prueba empresariales.*

Con las instrucciones de este artículo, configurará opciones adicionales de Microsoft 365 para aumentar la seguridad en el entorno de prueba de Microsoft 365 para empresas.

![Guías de laboratorio de prueba para la nube de Microsoft.](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Haga clic [aquí](../downloads/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual con todos los artículos en la pila de la guías de laboratorio para pruebas de Microsoft 365 para empresas.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Compilación del entorno de prueba de Microsoft 365 para empresas

Si solo quiere configurar una mayor seguridad de Microsoft 365 de forma ligera con los requisitos mínimos, siga las instrucciones de [Configuración base ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea configurar una mayor seguridad de Microsoft 365 en una empresa simulada, siga las instrucciones de [Autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La prueba del aumento de la seguridad de Microsoft 365 no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar las licencias automatizadas y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica. 

## <a name="phase-2-configure-increased-microsoft-365-security"></a>Fase 2: Configuración del aumento de la seguridad de Microsoft 365

En esta fase, habilitará una mayor seguridad de Microsoft 365 para el entorno de prueba de Microsoft 365 para empresas. Para obtener más detalles y opciones de configuración, consulte [Configuración del inquilino para aumentar la seguridad](/office365/securitycompliance/tenant-wide-setup-for-increased-security).

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>Configuración de SharePoint Online para bloquear aplicaciones que no admiten la autenticación moderna

Las aplicaciones que no admiten la autenticación moderna no pueden tener [configuraciones de acceso a dispositivos e identidades](../security/office-365-security/microsoft-365-policies-configurations.md) aplicadas, lo que es un elemento importante para proteger la suscripción de Microsoft 365 y sus recursos digitales. 

1. Vaya a la <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a> e inicie sesión en su suscripción al laboratorio de pruebas de Microsoft 365 con su cuenta de administrador global.
    
  - Si usa el entorno de prueba ligero de Microsoft 365, inicie sesión desde el equipo local.
    
  - Si usa el entorno de prueba de Microsoft 365 empresarial simulado, use el [Azure Portal](https://portal.azure.com) para conectarse a la máquina virtual CLIENT1 e inicie sesión desde CLIENT1.
 
2. En la nueva pestaña **Centro de administración de Microsoft 365**, en **Administración centros** del panel de navegación izquierdo, haga clic en **SharePoint**.
3. En la nueva pestaña **Centro de administración de SharePoint** , seleccione **Directivas** > <a href="https://go.microsoft.com/fwlink/?linkid=2185071" target="_blank">**Control de acceso**</a>.
4. Seleccione **Aplicaciones que no admiten la autenticación moderna**, seleccione **Bloquear acceso** y, a continuación, seleccione **Guardar**.


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>Habilitación de Defender para Office 365 para SharePoint, OneDrive para la Empresa y Microsoft Teams

Defender para Office 365 para SharePoint, OneDrive y Microsoft Teams protege a su organización de compartir involuntariamente archivos malintencionados.

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de cumplimiento de security &</a> e inicie sesión con su cuenta de administrador global.

2. En el panel de navegación izquierdo, en **Administración de amenazas**, haga clic en **Directivay**, a continuación, haga clic en **Datos adjuntos seguros**. 

3. En **Proteger archivos en SharePoint, OneDrive y Microsoft Teams**. seleccione **Activar ATP para SharePoint, OneDrive y Microsoft Teams**.

4. Haga clic en **Guardar**.


### <a name="enable-anti-malware"></a>Habilitación del antimalware

El malware se compone de virus y spyware. Los virus infectan otros programas y datos, y se propagan en todo el equipo en busca de programas que infectar. El spyware se refiere a malware que recopila información de carácter personal, como información de inicio de sesión y datos de carácter personal, y la envía al autor del malware. 

Microsoft 365 tiene funcionalidades integradas de filtrado de malware y correo no deseado que ayudan a proteger los mensajes entrantes y salientes de software malintencionado y le ayudan a protegerse del correo no deseado. Para obtener más información, consulte [Protección contra correo no deseado & antimalware](../security/office-365-security/anti-spam-and-anti-malware-protection.md).

Para asegurarse de que el procesamiento antimalware se realiza en archivos con tipos de archivos adjuntos comunes:

1. Haga clic en el botón Atrás del explorador para volver a la página **Directiva** .
2. Haga clic en **Antimalware**.
3. Haga doble clic en la directiva denominada **Predeterminada**.
4. En la ventana **Directiva antimalware** , haga clic en **Configuración**.
4. En **el filtro Tipos de datos adjuntos comunes**, seleccione **Activado** y, a continuación, haga clic en **Guardar**.


## <a name="phase-3-examine-the-security-dashboard"></a>Fase 3: Examen del panel de seguridad

La administración de amenazas en Microsoft 365 puede ayudarle a controlar y administrar el acceso de dispositivos móviles a los datos de su organización, ayudar a proteger su organización de la pérdida de datos y ayudar a proteger los mensajes entrantes y salientes contra software malintencionado y correo no deseado. También usa la administración de amenazas para proteger la reputación del dominio y determinar si los remitentes están suplantando o no cuentas de su dominio de forma malintencionada. 

Para ver el panel de seguridad:

1. Si es necesario, vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de cumplimiento de seguridad &</a> e inicie sesión con su cuenta de administrador global.

2. En el panel de navegación izquierdo, en **Administración de amenazas**, haga clic en **Panel**.

Eche un vistazo de cerca a todas las tarjetas del panel para familiarizarse con la información proporcionada.

Para obtener más información, vea [Panel de seguridad](../security/office-365-security/security-dashboard.md).


## <a name="phase-4-examine-microsoft-secure-score"></a>Fase 4: Examen de la puntuación segura de Microsoft

Puntuación de seguridad de Microsoft muestra la posición de seguridad como un número, lo que indica el nivel actual en relación con las características que están disponibles en la suscripción. También proporciona una lista de las acciones de mejora que puede realizar para mejorar la puntuación.

1. Cree una nueva pestaña en el explorador, vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a> y, a continuación, haga clic en **Puntuación segura**.
2. En la pestaña **Información general**  , anote la puntuación de seguridad actual y cómo se compara con la media global y las suscripciones con un número similar de licencias.
3. En la pestaña **Acciones de mejora** , lea la lista de acciones que puede realizar para aumentar la puntuación.

Para obtener más información, consulte [Puntuación segura de Microsoft](../security/defender/microsoft-secure-score.md).

## <a name="next-steps"></a>Pasos siguientes

Explore características y funcionalidades adicionales de [protección de la información](m365-enterprise-test-lab-guides.md#information-protection) en el entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](/microsoft-365-enterprise/)
