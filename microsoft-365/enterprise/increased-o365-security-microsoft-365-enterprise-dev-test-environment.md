---
title: Aumentó la seguridad de Microsoft 365 para su entorno de prueba de Microsoft 365 para empresas.
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
description: Use esta guía del entorno de pruebas para habilitar opciones de seguridad de Microsoft 365 adicionales para el entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: d385688a6e59ee500442bcf1b815dfd165102242
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847005"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a>Aumentó la seguridad de Microsoft 365 para su entorno de prueba de Microsoft 365 para empresas.

*Esta guía del entorno de pruebas solo puede usarse para entornos de prueba de empresa de Microsoft 365.*

Con las instrucciones de este artículo, se configuran opciones adicionales de configuración de Microsoft 365 para aumentar la seguridad en el entorno de prueba de Microsoft 365 para empresas.

![Guías del laboratorio de pruebas para la nube de Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Haga clic [aquí](../downloads/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual con todos los artículos en la pila de la guías de laboratorio para pruebas de Microsoft 365 para empresas.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: crear el entorno de prueba de Microsoft 365 para empresas

Si solo quiere configurar la seguridad mejorada de Microsoft 365 de forma ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea configurar una seguridad mejorada de Microsoft 365 en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La prueba de la seguridad mejorada de Microsoft 365 no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar la concesión de licencias automatizada y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica. 

## <a name="phase-2-configure-increased-microsoft-365-security"></a>Fase 2: configurar una mayor seguridad de Microsoft 365

En esta fase, se habilita una mayor seguridad de Microsoft 365 para el entorno de prueba de Microsoft 365 para empresas. Para obtener más detalles y configuraciones, vea [Configure Your tenant for mayor Security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>Configurar SharePoint Online para bloquear aplicaciones que no son compatibles con la autenticación moderna

Las aplicaciones que no admiten la autenticación moderna no pueden tener aplicadas [configuraciones de identidad y acceso a dispositivos](../security/office-365-security/microsoft-365-policies-configurations.md) , que es un elemento importante de la protección de la suscripción de Microsoft 365 y sus activos digitales. 

1. Vaya al centro de administración de 365 de Microsoft ( [https://portal.microsoft.com](https://portal.microsoft.com) ) e inicie sesión en su suscripción de laboratorio de pruebas de microsoft 365 con su cuenta de administrador global.
    
  - Si usa el entorno de prueba ligero de Microsoft 365, inicie sesión desde el equipo local.
    
  - Si usa el entorno de prueba de Enterprise de Microsoft 365 simulado, use [Azure portal](https://portal.azure.com) para conectarse a la máquina virtual CLIENT1 y, a continuación, inicie sesión desde cliente1.
 
2. En la nueva pestaña **centro de administración de 365 de Microsoft** , en centros de **Administración** , en el panel de navegación izquierdo, haga clic en **SharePoint**.
3. En la nueva pestaña **centro de administración de SharePoint** , haga clic en **directivas > control de acceso**.
4. Haga clic en **aplicaciones que no admiten la autenticación moderna** , seleccione **Bloquear acceso** y, a continuación, haga clic en **Guardar**.


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>Habilitar defender para Office 365 para SharePoint, OneDrive para la empresa y Microsoft Teams

Defender para Office 365 para SharePoint, OneDrive y Microsoft Teams protege a su organización de archivos malintencionados que se comparten de forma inadvertida.

1. Vaya al [centro de seguridad & cumplimiento](https://protection.office.com) e inicie sesión con su cuenta de administrador global.

2. En el panel de navegación izquierdo, en **Administración de amenazas** , haga clic en **Directiva** y, a continuación, en **datos adjuntos seguros**. 

3. En **proteger archivos en SharePoint, OneDrive y Microsoft Teams**. Seleccione **Activar ATP para SharePoint, OneDrive y Microsoft Teams**.

4. Haga clic en **Guardar**.


### <a name="enable-anti-malware"></a>Habilitar anti-malware

El malware se compone de virus y spyware. Los virus infectan otros programas y datos, y se propagan en todo el equipo en busca de programas que infectar. El spyware se refiere a malware que recopila información de carácter personal, como información de inicio de sesión y datos de carácter personal, y la envía al autor del malware. 

Microsoft 365 tiene capacidades integradas de filtrado de correo no deseado y malware que ayudan a proteger los mensajes entrantes y salientes de software malintencionado y ayudan a protegerse del correo no deseado. Para obtener más información, consulte [protección contra el correo no deseado & anti-malware](../security/office-365-security/anti-spam-and-anti-malware-protection.md).

Para asegurarse de que el procesamiento antimalware se realice en archivos con tipos de archivos adjuntos comunes:

1. Haga clic en el botón atrás del explorador para volver a la página de la **Directiva** .
2. Haga clic en **anti-malware**.
3. Haga doble clic en la Directiva denominada **default**.
4. En la ventana **Directiva contra malware** , haga clic en **configuración**.
4. En **filtro de tipos de datos adjuntos comunes** , seleccione **activado** y haga clic en **Guardar**.


## <a name="phase-3-examine-the-security-dashboard"></a>Fase 3: examinar el panel de seguridad

La administración de amenazas de Microsoft 365 puede ayudarle a controlar y administrar el acceso de dispositivos móviles a los datos de su organización, a proteger su organización de la pérdida de datos y a proteger los mensajes entrantes y salientes del software malintencionado y el correo no deseado. También se usa la administración de amenazas para proteger la reputación del dominio y para determinar si los remitentes se falsifican de su dominio de una mala parte de las cuentas. 

Para ver el panel de seguridad:

1. Si es necesario, vaya al [centro de seguridad & cumplimiento](https://protection.office.com) e inicie sesión con su cuenta de administrador global.

2. En el panel de navegación izquierdo, en **Administración de amenazas** , haga clic en **Panel**.

Eche un vistazo a todas las tarjetas del panel para familiarizarse con la información proporcionada.

Para obtener más información, consulte [Panel de seguridad](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).


## <a name="phase-4-examine-microsoft-secure-score"></a>Fase 4: examinar la calificación segura de Microsoft

La puntuación segura de Microsoft muestra su postura de seguridad como un número, que indica el nivel actual en relación con las características que están disponibles en la suscripción. También le ofrece una lista de acciones de mejora que puede realizar para mejorar su calificación.

1. Cree una nueva pestaña en el explorador y vaya al [centro de seguridad 365 de Microsoft](https://security.microsoft.com/)y, a continuación, haga clic en **puntuación segura**.
2. En la ficha **información general**  , anote la puntuación segura actual y la forma en que se compara con la media global y las suscripciones con un número de licencias similar.
3. En la pestaña **acciones de mejora** , lea la lista de acciones que puede realizar para aumentar el resultado.

Para obtener más información, consulte [calificación segura de Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).

## <a name="next-steps"></a>Pasos siguientes

Explore otras características y funcionalidades de protección de la [información](m365-enterprise-test-lab-guides.md#information-protection) en su entorno de prueba.

## <a name="see-also"></a>Recursos adicionales

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación de Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
