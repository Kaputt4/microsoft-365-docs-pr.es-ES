---
title: Mayor Microsoft 365 seguridad para su Microsoft 365 entorno de prueba empresarial
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use esta Guía del laboratorio de pruebas para habilitar la configuración Microsoft 365 seguridad adicional de su Microsoft 365 entorno de prueba empresarial.
ms.openlocfilehash: d1bff8b736e5074f621a173d206f7c5f77841b25
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198356"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a>Mayor Microsoft 365 seguridad para su Microsoft 365 entorno de prueba empresarial

*Esta Guía del laboratorio de pruebas solo se puede usar Microsoft 365 entornos de prueba empresariales.*

Con las instrucciones de este artículo, se configuran opciones Microsoft 365 adicionales para aumentar la seguridad en el entorno Microsoft 365 de prueba empresarial.

![Guías del laboratorio de pruebas para la nube de Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Haga clic [aquí](../downloads/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual con todos los artículos en la pila de la guías de laboratorio para pruebas de Microsoft 365 para empresas.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Crear su Microsoft 365 entorno de prueba empresarial

Si solo desea configurar una mayor seguridad Microsoft 365 de forma ligera con los requisitos mínimos, siga las instrucciones de [Configuración base ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea configurar una mayor seguridad Microsoft 365 en una empresa simulada, siga las instrucciones de [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Las pruebas Microsoft 365 seguridad no requieren el entorno de prueba de empresa simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar las licencias automatizadas y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica. 

## <a name="phase-2-configure-increased-microsoft-365-security"></a>Fase 2: Configurar una mayor Microsoft 365 seguridad

En esta fase, se habilita una mayor Microsoft 365 seguridad para su Microsoft 365 entorno de prueba empresarial. Para obtener más detalles y opciones de configuración, consulte [Configure your tenant for increased security](/office365/securitycompliance/tenant-wide-setup-for-increased-security).

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>Configurar SharePoint Online para bloquear aplicaciones que no admiten la autenticación moderna

Las aplicaciones que no admiten la autenticación moderna no pueden tener configuraciones de identidad y acceso a [dispositivos aplicadas,](../security/office-365-security/microsoft-365-policies-configurations.md) lo que es un elemento importante para proteger la suscripción Microsoft 365 y sus activos digitales. 

1. Vaya al Centro de Microsoft 365 de administración ( ) e inicie sesión en su Microsoft 365 de laboratorio de [https://portal.microsoft.com](https://portal.microsoft.com) pruebas con su cuenta de administrador global.
    
  - Si usa el entorno de prueba Microsoft 365 ligero, inicie sesión desde el equipo local.
    
  - Si usa el entorno de prueba simulado de Microsoft 365 empresa, use [Azure Portal](https://portal.azure.com) para conectarse a la máquina virtual CLIENT1 y, a continuación, inicie sesión desde CLIENT1.
 
2. En la nueva **pestaña Microsoft 365 centro** de administración, en Centros de **administración** en el panel de navegación izquierdo, haga clic **en SharePoint**.
3. En la nueva **pestaña SharePoint centro de administración,** haga clic en Directivas > control de **acceso**.
4. Haga **clic en Aplicaciones que no admiten la autenticación moderna,** seleccione Bloquear **acceso** y, a continuación, haga clic en **Guardar**.


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>Habilitar Defender para Office 365 para SharePoint, OneDrive para la Empresa y Microsoft Teams

Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.

1. Vaya al [Centro de seguridad & cumplimiento e](https://protection.office.com) inicie sesión con su cuenta de administrador global.

2. En el panel de navegación izquierdo, en **Administración de** amenazas, haga **clic** en Directiva y, a continuación, haga clic Caja fuerte **datos adjuntos**. 

3. En **Proteger archivos en SharePoint, OneDrive y Microsoft Teams**. seleccione **Activar ATP para SharePoint, OneDrive y Microsoft Teams**.

4. Haga clic en **Guardar**.


### <a name="enable-anti-malware"></a>Habilitar antimalware

El malware se compone de virus y spyware. Los virus infectan otros programas y datos, y se propagan en todo el equipo en busca de programas que infectar. El spyware se refiere a malware que recopila información de carácter personal, como información de inicio de sesión y datos de carácter personal, y la envía al autor del malware. 

Microsoft 365 capacidades integradas de filtrado de correo no deseado y malware que ayudan a proteger los mensajes entrantes y salientes de software malintencionado y le ayudan a protegerse del correo no deseado. Para obtener más información, vea [Anti-spam & anti-malware protection](../security/office-365-security/anti-spam-and-anti-malware-protection.md).

Para asegurarse de que el procesamiento antimalware se realiza en archivos con tipos de archivos adjuntos comunes:

1. Haga clic en el botón Atrás del explorador para volver a la **página** Directiva.
2. Haga **clic en Antimalware**.
3. Haga doble clic en la directiva denominada **Default**.
4. En la ventana **Directiva antimalware,** haga clic **en Configuración**.
4. En **Filtro de tipos comunes de datos adjuntos,** seleccione **Activar** y, a continuación, haga clic **en Guardar**.


## <a name="phase-3-examine-the-security-dashboard"></a>Fase 3: Examinar el panel de seguridad

La administración de amenazas en Microsoft 365 puede ayudarle a controlar y administrar el acceso de dispositivos móviles a los datos de su organización, ayudar a proteger su organización de la pérdida de datos y ayudar a proteger los mensajes entrantes y salientes de software malintencionado y correo no deseado. También usa la administración de amenazas para proteger la reputación de su dominio y determinar si los remitentes suplanta de forma malintencionada cuentas de su dominio. 

Para ver el panel de seguridad:

1. Si es necesario, vaya al Centro de [seguridad & cumplimiento e](https://protection.office.com) inicie sesión con su cuenta de administrador global.

2. En el panel de navegación izquierdo, en **Administración de amenazas,** haga clic en **Panel**.

Echa un vistazo de cerca a todas las tarjetas del panel para familiarizarte con la información proporcionada.

Para obtener más información, vea [Panel de seguridad](../security/office-365-security/security-dashboard.md).


## <a name="phase-4-examine-microsoft-secure-score"></a>Fase 4: Examinar la puntuación segura de Microsoft

Puntuación segura de Microsoft muestra su posición de seguridad como un número, que indica el nivel actual con respecto a las características que están disponibles en su suscripción. También te ofrece una lista de acciones de mejora que puedes realizar para mejorar tu puntuación.

1. Cree una nueva pestaña en el explorador y vaya al centro de seguridad Microsoft 365 [y,](https://security.microsoft.com/)a continuación, haga clic en **Puntuación segura**.
2. En la **pestaña Información**  general, anote su puntuación segura actual y cómo se compara con el promedio global y las suscripciones con un número similar de licencias.
3. En la **pestaña Acciones de** mejora, lee la lista de acciones que puedes realizar para aumentar la puntuación.

Para obtener más información, vea [Puntuación segura de Microsoft](../security/defender/microsoft-secure-score.md).

## <a name="next-steps"></a>Pasos siguientes

Explore características [y capacidades adicionales](m365-enterprise-test-lab-guides.md#information-protection) de protección de la información en el entorno de prueba.

## <a name="see-also"></a>Consulte también

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](/microsoft-365-enterprise/)