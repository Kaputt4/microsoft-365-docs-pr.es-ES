---
title: Aumentó la seguridad de Microsoft 365 para su entorno de prueba empresarial de Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use esta guía del entorno de pruebas para habilitar la configuración adicional de seguridad de Microsoft 365 su entorno de prueba empresarial de Microsoft 365.
ms.openlocfilehash: f430acb4a7fd1842a4ae26025ad5a63cccf8392f
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640372"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a>Aumentó la seguridad de Microsoft 365 para su entorno de prueba empresarial de Microsoft 365

Con las instrucciones de este artículo, se configuran opciones adicionales de configuración de Microsoft 365 para aumentar la seguridad en el entorno de pruebas de Microsoft 365 Enterprise.

![Guías del laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Haga clic [aquí](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Crear el entorno de pruebas de Microsoft 365 Enterprise

Si solo quiere configurar la seguridad mejorada de Microsoft 365 de forma ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea configurar una seguridad mejorada de Microsoft 365 en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La prueba de la seguridad mejorada de Microsoft 365 no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar la concesión de licencias automatizada y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica. 


## <a name="phase-2-configure-increased-microsoft-365-security"></a>Fase 2: configurar una mayor seguridad de Microsoft 365

En esta fase, se habilita una mayor seguridad de Microsoft 365 para su entorno de prueba empresarial de Microsoft 365. Para obtener más detalles y opciones de configuración, consulte [configurar el inquilino de Office 365 para aumentar la seguridad](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>Configurar SharePoint Online para bloquear aplicaciones que no son compatibles con la autenticación moderna

Las aplicaciones que no admiten la autenticación moderna no pueden tener aplicadas [configuraciones de identidad y acceso a dispositivos](microsoft-365-policies-configurations.md) , que es un elemento importante de la protección de la suscripción de Microsoft 365 y sus activos digitales. 

1. Vaya al centro de administración de 365 de[https://portal.microsoft.com](https://portal.microsoft.com)Microsoft () e inicie sesión en su suscripción de laboratorio de pruebas de Office 365 con su cuenta de administrador global.
    
  - Si usa el entorno de prueba ligero de Microsoft 365, inicie sesión desde el equipo local.
    
  - Si usa el entorno de prueba de Enterprise de Microsoft 365 simulado, use [Azure portal](https://portal.azure.com) para conectarse a la máquina virtual CLIENT1 y, a continuación, inicie sesión desde cliente1.
 
2. En la nueva pestaña **centro de administración de 365 de Microsoft** , haga clic en centros de **Administración > SharePoint**.
3. En la nueva pestaña **centro de administración de SharePoint** , haga clic en control de **acceso**.
4. En **aplicaciones que no admiten la autenticación moderna**, haga clic en **bloquear**y, a continuación, haga clic en **Aceptar**.


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>Habilitación de la protección contra amenazas avanzada para SharePoint, OneDrive para la empresa y Microsoft Teams

Office 365 Advanced Threat Protection (ATP) para SharePoint, OneDrive y Microsoft Teams protege su organización de archivos malintencionados que se comparten de forma inadvertida.

1. Vaya al [centro de cumplimiento de & de seguridad de Office 365](https://protection.office.com) e inicie sesión con su cuenta de administrador global.

2. En el panel de navegación izquierdo, en **Administración de amenazas**, elija **Directiva > datos adjuntos seguros**. 

3. Seleccione **Activar ATP para SharePoint, OneDrive y Microsoft Teams**.

4. Haga clic en **Guardar **.


### <a name="enable-anti-malware"></a>Habilitar anti-malware

El malware se compone de virus y spyware. Los virus infectan otros programas y datos, y se propagan en todo el equipo en busca de programas que infectar. El spyware se refiere a malware que recopila información de carácter personal, como información de inicio de sesión y datos de carácter personal, y la envía al autor del malware. 

Office 365 tiene capacidades integradas de filtrado de correo no deseado y malware que ayudan a proteger los mensajes entrantes y salientes de software malintencionado y ayudan a protegerse del correo no deseado. Para obtener más información, consulte [protección antimalware & contra el correo no deseado en Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)

Para asegurarse de que el procesamiento antimalware se realice en archivos con tipos de archivos adjuntos comunes:

1. Haga clic en el botón atrás del explorador para volver a la página de la **Directiva** .
2. Haga clic en **anti-malware**.
3. Haga doble clic en la Directiva denominada **default**.
4. En la ventana **Directiva contra malware** , haga clic en **configuración**.
4. En **filtro de tipos de datos adjuntos comunes**, haga clic **en > guardar**.


## <a name="phase-3-examine-the-threat-management-dashboard"></a>Fase 3: examinar el panel de administración de amenazas

La administración de amenazas de Office 365 puede ayudarle a controlar y administrar el acceso de dispositivos móviles a los datos de su organización, a proteger su organización de la pérdida de datos y a proteger los mensajes entrantes y salientes del software malintencionado y el correo no deseado. También se usa la administración de amenazas para proteger la reputación del dominio y para determinar si los remitentes se falsifican de su dominio de una mala parte de las cuentas. Para obtener más información, vea [Threat Management en el centro de seguridad de Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/threat-management).

<!--
### Office 365 Cloud App Security dashboard

Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action. For more information, see [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).

### Microsoft 365 Secure Score

1. Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.
2. On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.
!-->


## <a name="next-steps"></a>Pasos siguientes

Consulte el paso [configurar mayor seguridad para Microsoft 365](infoprotect-configure-increased-security-office-365.md) en la fase de protección de la **información** para obtener información y vínculos para configurar estas opciones en producción.

Explore otras características y funcionalidades de protección de la [información](m365-enterprise-test-lab-guides.md#information-protection) en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implementar Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentación y recursos de Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)

