---
title: Mayor seguridad de Office 365 para el entorno de pruebas de Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use esta guía de laboratorio de prueba para habilitar la configuración de seguridad adicionales de Office 365 su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: 18e7b682d20c2212ae73783d668250d28b04075f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871426"
---
# <a name="increased-office-365-security-for-your-microsoft-365-enterprise-test-environment"></a>Mayor seguridad de Office 365 para el entorno de pruebas de Microsoft 365 Enterprise

Con las instrucciones de este artículo, configura opciones adicionales de Office 365 para aumentar la seguridad en su entorno de prueba de Microsoft 365 Enterprise.

![Guías del laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Haga clic [aquí](https://aka.ms/m365etlgstack) para acceder a un mapa visual de todos los artículos de la pila Guía del laboratorio de pruebas de Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Generar el entorno de prueba de Microsoft 365 Enterprise

Si desea configurar la seguridad de Office 365 mayor en una forma sencilla con los requisitos mínimos, siga las instrucciones de [configuración básica ligero](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea configurar una mayor seguridad de Office 365 en una empresa simulada, siga las instrucciones que aparecen en la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Pruebas de mayor seguridad de Office 365 no requieren que el entorno de prueba simulado enterprise, que incluye una intranet simulada conectada a Internet y sincronización de Active directory para un bosque de Windows Server AD. Se proporciona aquí como una opción para que pueda probar licencias automatizada y la pertenencia a grupos y experimentar con él en un entorno que representa una organización típica. 


## <a name="phase-2-configure-increased-office-365-security"></a>Fase 2: Configuración de mayor seguridad de Office 365

En esta fase, se habilita una mayor seguridad de Office 365 para el entorno de prueba de Microsoft 365 Enterprise. Para obtener más información y la configuración, vea [Configure el inquilino de Office 365 para aumentar la seguridad](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>Configurar SharePoint Online para bloquear las aplicaciones que no admiten la autenticación moderna

Aplicaciones que no admiten la autenticación moderna no pueden tener una [identidad y dispositivo de acceso a las configuraciones de](microsoft-365-policies-configurations.md) aplica a ellos, que es un elemento importante de la seguridad de su suscripción de 365 de Microsoft y a sus activos digitales. 

1. Vaya al portal de Office 365 ([https://portal.office.com](https://portal.office.com)) e inicie sesión en su suscripción de prueba de Office 365 con su cuenta de administrador global.
    
  - Si está utilizando el entorno de prueba de Microsoft 365 ligero, inicie sesión desde el equipo local.
    
  - Si está utilizando el entorno de prueba de enterprise simulado 365 de Microsoft, use el [portal de Azure](https://portal.azure.com) para conectarse a la máquina virtual CLIENT1 y, a continuación, iniciar sesión en desde CLIENT1.
 
2. En la ficha del **Centro de administración de Microsoft 365** , haga clic en **Admin**.
3. En la ficha del **Centro de administración de Microsoft 365** nuevo, haga clic en **centros de administración > SharePoint**.
4. En la nueva ficha del **Centro de administración de SharePoint** , haga clic en **control de acceso**.
5. En las **aplicaciones que no admiten la autenticación moderna**, haga clic en **bloque > Aceptar**.


### <a name="enable-advanced-threat-protection-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Habilitación de Advanced la protección contra amenazas (ATP) para SharePoint, OneDrive y equipos de Microsoft

Protección de amenaza avanzada de Office 365 (ATP) es una característica de Exchange Online Protection (EOP) que ayuda a mantener el malware fuera de su correo electrónico. Con ATP, crear directivas en el centro de administración de Exchange (EAC) o la seguridad & Centro de cumplimiento que ayudan a garantizar a los usuarios obtener acceso sólo vínculos o datos adjuntos en mensajes de correo electrónico que se identifican como no malintencionado. Para obtener más información, consulte [protección contra amenazas avanzadas para los datos adjuntos seguros y vínculos seguros](https://docs.microsoft.com/office365/securitycompliance/office-365-atp).

1. En la ficha del **Centro de administración de Microsoft 365** del explorador, haga clic en **centros de administración > seguridad y cumplimiento**.
2. En la ficha nuevo de **seguridad y cumplimiento** , haga clic en **administración de amenazas > directiva**.
3. Haga clic en **datos adjuntos seguros de ATP**.
4. En el panel **datos adjuntos seguros** , seleccione **Activar ATP para SharePoint, OneDrive y los equipos de Microsoft**y, a continuación, haga clic en **Guardar**.

### <a name="enable-anti-malware"></a>Habilitar anti-malware

Malware se compone de virus y spyware. Virus infectan otros programas y datos, y se propagan a lo largo de su equipo buscando programas a infectan. Spyware hace referencia al código malintencionado que recopila su información personal, como información de inicio de sesión y los datos personales y lo envía a su autor de malware. 

Office 365 tiene capacidades que ayudan a proteger los mensajes entrantes y salientes de software malintencionado y ayudar a protegerle contra correo no deseado de filtrado de spam y malware incorporadas. Para obtener más información, consulte [protección contra correo no deseado y antimalware en Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)

Para asegurarse de que se lleva a cabo el procesamiento de anti-malware en archivos con tipos de archivo de datos adjuntos comunes:

1. Haga clic en el botón Atrás del explorador para volver a la página de **Directiva** .
2. Haga clic en **Anti-malware**.
3. Haga doble clic en la directiva de llamada **predeterminada**.
4. En la ventana **Directiva de Anti-malware** , haga clic en **configuración**.
4. En **el filtro de tipos comunes de los datos adjuntos**, haga clic en **en > Guardar**.


## <a name="phase-3-examine-office-365-security-tools-and-logs"></a>Fase 3: Examinar los registros y las herramientas de seguridad de Office 365

En esta fase, examine los servicios integrados que informan acerca de los eventos de seguridad y medir su posición de seguridad general.

### <a name="threat-management-dashboard"></a>Panel de administración de amenaza

Administración de Office 365 amenaza puede ayudarle a controlar y administrar el acceso de dispositivo móvil a los datos de la organización, ayudar a proteger su organización contra la pérdida de datos y ayudar a proteger los mensajes entrantes y salientes de correo no deseado y otro software malintencionado. También use cuentas de administración para proteger la reputación de su dominio y para determinar si los remitentes se suplantación de identidad malintencionada desde su dominio de amenaza. Para obtener más información, vea [administración de amenaza en el centro de cumplimiento y seguridad de Office 365](https://docs.microsoft.com/office365/securitycompliance/threat-management).

Siga estos pasos para ver el panel de administración de Office 365 amenaza:

1. En la ficha del **Centro de administración de Microsoft 365** del explorador, haga clic en **centros de administración > seguridad y cumplimiento**.
2. En la ficha nuevo de **seguridad y cumplimiento** , haga clic en **administración de amenazas > panel**.
3. En la ficha de **panel de** nuevo en el explorador, tenga en cuenta las tendencias de malware, conocimientos y otras secciones del panel.

### <a name="office-365-cloud-app-security-dashboard"></a>Panel de seguridad de la aplicación en la nube de Office 365

Office 365 en la nube seguridad de la aplicación, anteriormente conocido como Office 365 administración avanzada de seguridad, le permite crear directivas que supervisión e informan de las actividades sospechosas en su suscripción de Office 365, para que pueda investigar y tomar posibles acción de corrección. Para obtener más información, vea [Información general de Office 365 en la nube seguridad de la aplicación](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).

1. En la ficha del **Centro de administración de Microsoft 365** del explorador, haga clic en **centros de administración > seguridad y cumplimiento**.
2. En la ficha nuevo de **seguridad y cumplimiento** , haga clic en **alertas > Administrar avanzada alertas > Ir a la seguridad de la aplicación de nube de Office 365**.
3. En la ficha **Seguridad de la aplicación en la nube** de nuevo, tenga en cuenta la vista de panel y la lista de directivas predeterminadas que supervisar diversas actividades en su suscripción de Office 365.
4. Haga clic en el icono de panel para ver un resumen de las actividades de seguridad de la aplicación en la nube que se realiza un seguimiento.
5. Haga clic en **investigar** (el icono de anteojos) y, a continuación, en **el registro de actividad** para ver la lista de inicios de sesión recientes y otras actividades.

### <a name="secure-score"></a>Puntuación de seguro

1. Crear una ficha nueva en el explorador y vaya a **securescore.office.com**.
2. En la **ficha de panel**, tenga en cuenta la puntuación seguro actual y la lista de acciones en la cola para aumentar la puntuación.

Vea el paso [Configure mayor seguridad para Office 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) en la fase de **protección de la información** para obtener información y vínculos para configurar estas opciones de configuración de producción.

## <a name="next-step"></a>Paso siguiente

Explorar las características adicionales de [protección de la información](m365-enterprise-test-lab-guides.md#information-protection) y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implementar Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentación y recursos de Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)

