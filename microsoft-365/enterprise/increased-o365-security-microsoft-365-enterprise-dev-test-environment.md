---
title: Mayor seguridad de Microsoft 365 para su entorno de prueba de Microsoft 365 para empresas
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
description: Use esta Guía del entorno de pruebas para habilitar configuraciones de seguridad adicionales de Microsoft 365 en el entorno de pruebas de Microsoft 365 para empresas.
ms.openlocfilehash: d385688a6e59ee500442bcf1b815dfd165102242
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847005"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a>Mayor seguridad de Microsoft 365 para su entorno de prueba de Microsoft 365 para empresas

*Esta guía del entorno de pruebas solo se puede usar para Entornos de prueba de Microsoft 365 para empresas.*

Con las instrucciones de este artículo, puede configurar opciones adicionales de Microsoft 365 para aumentar la seguridad en su entorno de prueba de Microsoft 365 para empresas.

![Guías del laboratorio de pruebas para la nube de Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Haga clic [aquí](../downloads/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual con todos los artículos en la pila de la guías de laboratorio para pruebas de Microsoft 365 para empresas.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Crear el entorno de prueba de Microsoft 365 para empresas

Si solo quiere configurar una mayor seguridad de Microsoft 365 de forma ligera con los requisitos mínimos, siga las instrucciones de [la configuración básica ligera.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Si desea configurar una mayor seguridad de Microsoft 365 en una empresa simulada, siga las instrucciones de autenticación [de paso a través.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Las pruebas que aumentan la seguridad de Microsoft 365 no requieren el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar las licencias automatizadas y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica. 

## <a name="phase-2-configure-increased-microsoft-365-security"></a>Fase 2: Configurar una mayor seguridad de Microsoft 365

En esta fase, habilitará una mayor seguridad de Microsoft 365 para su entorno de prueba de Microsoft 365 para empresas. Para obtener más detalles y opciones de configuración, [consulte Configurar el espacio empresarial para aumentar la seguridad.](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>Configurar SharePoint Online para bloquear aplicaciones que no admiten la autenticación moderna

Las aplicaciones que no admiten la autenticación moderna no pueden tener aplicadas configuraciones de acceso de [dispositivos](../security/office-365-security/microsoft-365-policies-configurations.md) e identidades, lo que es un elemento importante para proteger su suscripción a Microsoft 365 y sus activos digitales. 

1. Go to the Microsoft 365 admin center ( [https://portal.microsoft.com](https://portal.microsoft.com) ) and sign in to your Microsoft 365 test lab subscription with your global administrator account.
    
  - Si usa el entorno de prueba ligero de Microsoft 365, inicie sesión desde el equipo local.
    
  - Si usa el entorno de prueba de Microsoft 365 de empresa simulada, use [Azure Portal](https://portal.azure.com) para conectarse a la máquina virtual CLIENT1 y, a continuación, inicie sesión desde CLIENT1.
 
2. En la nueva pestaña Centro de administración  de **Microsoft 365,** en Centros de administración en el panel de navegación izquierdo, haga clic **en SharePoint.**
3. En la nueva pestaña **Centro de administración de SharePoint,** haga clic en Directivas > control de **acceso.**
4. Haga **clic en Aplicaciones que no admiten la autenticación moderna,** seleccione Bloquear **acceso** y, a continuación, haga clic en **Guardar.**


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>Habilitar Defender para Office 365 para SharePoint, OneDrive para la Empresa y Microsoft Teams

Defender para Office 365 para SharePoint, OneDrive y Microsoft Teams protege su organización contra el uso compartido involuntario de archivos malintencionados.

1. Vaya al Centro [de seguridad & cumplimiento](https://protection.office.com) e inicie sesión con su cuenta de administrador global.

2. En el panel de navegación izquierdo, **en** Administración de amenazas, haga clic en **Directiva** y, a continuación, haga clic en **Datos adjuntos seguros.** 

3. En **Proteger archivos en SharePoint, OneDrive y Microsoft Teams.** seleccione **Activar ATP para SharePoint, OneDrive y Microsoft Teams.**

4. Haga clic en **Guardar**.


### <a name="enable-anti-malware"></a>Habilitar antimalware

El malware se compone de virus y spyware. Los virus infectan otros programas y datos, y se propagan en todo el equipo en busca de programas que infectar. El spyware se refiere a malware que recopila información de carácter personal, como información de inicio de sesión y datos de carácter personal, y la envía al autor del malware. 

Microsoft 365 tiene capacidades integradas de filtrado de correo no deseado y malware que ayudan a proteger los mensajes entrantes y salientes de software malintencionado y le ayudan a protegerse contra el correo no deseado. Para obtener más información, vea [Protección contra correo & antimalware.](../security/office-365-security/anti-spam-and-anti-malware-protection.md)

Para asegurarse de que el procesamiento antimalware se realiza en archivos con tipos comunes de archivos adjuntos:

1. Haga clic en el botón Atrás del explorador para volver a la **página Directiva.**
2. Haga **clic en Antimalware.**
3. Haga doble clic en la directiva denominada **Default**.
4. En la ventana **Directiva antimalware,** haga clic en **Configuración.**
4. En **Filtro de tipos comunes de datos adjuntos,** seleccione **Activar** y, a continuación, haga clic en **Guardar**.


## <a name="phase-3-examine-the-security-dashboard"></a>Fase 3: Examinar el panel de seguridad

La administración de amenazas en Microsoft 365 puede ayudarle a controlar y administrar el acceso de dispositivos móviles a los datos de su organización, ayudar a proteger su organización de la pérdida de datos y ayudar a proteger los mensajes entrantes y salientes de software malintencionado y correo no deseado. También usa la administración de amenazas para proteger la reputación de su dominio y para determinar si los remitentes son o no cuentas de suplantación de identidad malintencionadas de su dominio. 

Para ver el panel de seguridad:

1. Si es necesario, vaya al Centro de [seguridad & cumplimiento](https://protection.office.com) e inicie sesión con su cuenta de administrador global.

2. En el panel de navegación izquierdo, en Administración **de amenazas,** haga clic en **Panel.**

Echa un vistazo a todas las tarjetas del panel para familiarizarte con la información proporcionada.

Para obtener más información, vea [Panel de seguridad.](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard)


## <a name="phase-4-examine-microsoft-secure-score"></a>Fase 4: Examinar la puntuación de seguridad de Microsoft

Puntuación de seguridad de Microsoft muestra su posición de seguridad como un número, que indica su nivel actual con respecto a las características que están disponibles en su suscripción. También le proporciona una lista de las acciones de mejora que puede realizar para mejorar su puntuación.

1. Cree una nueva pestaña en el explorador, vaya al Centro de seguridad de [Microsoft 365](https://security.microsoft.com/)y, a continuación, haga clic en **Puntuación de seguridad.**
2. En la **pestaña**  Información general, anote su puntuación de seguridad actual y cómo se compara con el promedio global y las suscripciones con un número similar de licencias.
3. En la **pestaña Acciones de** mejora, lee la lista de acciones que puedes realizar para aumentar la puntuación.

Para obtener más información, vea [Puntuación de seguridad de Microsoft.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)

## <a name="next-steps"></a>Pasos siguientes

Explore características [y capacidades adicionales](m365-enterprise-test-lab-guides.md#information-protection) de protección de la información en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
