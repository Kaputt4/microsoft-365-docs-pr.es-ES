---
title: Aplicaciones en el escritorio administrado de Microsoft
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: a24212cf69df50d00a32f17e8daf1939657dd602
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632856"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Aplicaciones en el escritorio administrado de Microsoft

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>Aplicaciones en general

Microsoft incluye ciertas aplicaciones clave junto con la licencia de Microsoft 365 E3 o E5 necesaria para participar en el escritorio administrado de Microsoft. Sin embargo, aunque proporcionamos estas aplicaciones, aún tiene ciertas responsabilidades y acciones para completarse.

También puede implementar aplicaciones adicionales que no son de Microsoft para los usuarios finales para el autoservicio a través del portal de la empresa o una instalación en segundo plano obligatoria, todo con la canalización de implementación de Microsoft Intune. Si tiene la experiencia, puede migrar las aplicaciones que necesita; como alternativa, los servicios de consultoría de Microsoft (MCS) o proveedores que no son de Microsoft se alegrarán de ayudarle con un proyecto de empaquetado y migración. Para obtener más información sobre cómo trabajar con MCS, vea [Working with Microsoft Consulting Services](apps-MCS.md).


## <a name="apps-provided-by-microsoft"></a>Aplicaciones proporcionadas por Microsoft

Con su licencia de escritorio administrado de Microsoft se incluyen las versiones de 64 bits de las aplicaciones de Microsoft 365 apps for Enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype empresarial y OneNote). Las versiones de hacer clic y ejecutar de Microsoft Project y Visio *no* se incluyen de forma predeterminada, pero puede solicitar que se agreguen. Para obtener más información sobre estas aplicaciones, vea [instalar Microsoft Project o Microsoft Visio en dispositivos de escritorio administrados por Microsoft](../get-started/project-visio.md).

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Qué hace Microsoft para admitir las aplicaciones que proporcionamos

Microsoft proporcionará servicio completo para la implementación, actualización y soporte para las aplicaciones de Microsoft 365 aplicaciones para empresas incluidas. Las versiones de hacer clic y ejecutar de Microsoft Project y Visio *no* se incluyen de forma predeterminada, pero el escritorio administrado de Microsoft proporcionará grupos de implementación que permitan al administrador de ti administrar las licencias e implementarlas de forma adecuada para la organización. Microsoft proporcionará soporte a los usuarios finales de estas aplicaciones a través de los canales de soporte técnico de Microsoft administrados para equipos de escritorio.

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>Qué necesita hacer para admitir las aplicaciones que proporcionamos

Todavía hay algunas cosas que debe hacer con estas aplicaciones:

- **Asignar licencias** : es responsable de obtener y asignar las licencias adecuadas a los usuarios finales para las aplicaciones de Microsoft 365 para empresas.
- **Agregar usuarios a los grupos de seguridad** : Si está usando Microsoft Project o Visio, el administrador de TI debe agregar dichos usuarios a los grupos de implementación adecuados. Los administradores de ti también son responsables de reclamar las licencias de esos usuarios si dejan la compañía.
- **Implementación de complementos de microsoft 365** : Si necesita complementos para alguna de las aplicaciones para empresas de Microsoft 365, impleméntelo de forma centralizada como cualquier otra aplicación de Windows 32. 

## <a name="apps-you-provide"></a>Aplicaciones que proporciona

Por supuesto, probablemente tenga varias aplicaciones que necesita para las operaciones de la empresa. Solo se pueden implementar en dispositivos de escritorio administrados por Microsoft mediante la canalización de implementación de Microsoft Intune. Si la aplicación lo necesita, puede hacer que un proveedor lo empaquete (que puede ser un proveedor que no sea de Microsoft o un servicio de consultoría de Microsoft (MCS)) o, si tiene los medios, puede empaquetarlos usted mismo. A continuación, agregue estos paquetes al portal de escritorio administrado de Microsoft y asígnelos a los grupos de Azure Active Directory para desencadenar la implementación. 

Si actualmente implementa sus aplicaciones con el administrador de configuración de Microsoft Endpoint, Microsoft Managed Desktop puede proporcionarle una consulta para evaluar sus aplicaciones y detectar cuáles están listas para que se migren a Microsoft Intune y cuáles podrían requerir algún ajuste.


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Preparar sus propias aplicaciones para su inclusión en el escritorio administrado de Microsoft
Revisa tus aplicaciones y comprueba lo siguiente:

- Ninguna de las aplicaciones está prohibida o tiene un comportamiento restringido, como se describe en requisitos de la [aplicación de escritorio administrada de Microsoft](https://aka.ms/app-req).
- Las aplicaciones deben estar listas para la administración por parte de Microsoft Intune. Para obtener más información sobre esto, vea la implementación de aplicaciones de [Windows 10 con Microsoft Intune](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) y [agregar aplicaciones a Microsoft Intune](https://docs.microsoft.com/intune/apps-add).
- Otros requisitos previos al empaquetado, como el suministro de claves de licencia, el acuerdo con los términos de licencia y las conexiones de servidor preconfiguradas.

### <a name="decide-how-to-package-apps"></a>Decidir cómo empaquetar aplicaciones

Es posible que algunos proveedores de software independientes necesiten que las aplicaciones estén empaquetadas antes de que se implementen de forma centralizada. "Empaquetado" significa que el instalador de la aplicación está configurado con ajustes como claves de licencia, ubicaciones de servidor remoto o accesos directos de escritorio para que la aplicación pueda instalarse en segundo plano.

Hay tres opciones para empaquetar las aplicaciones: 


- Puede empaquetar las aplicaciones usted mismo
- Puede trabajar con un proveedor que no sea de Microsoft
- Puede participar con MCS para empaquetar sus aplicaciones. Trabaje con el representante de su cuenta de Microsoft. Para obtener más información, vea [Working with Microsoft Consulting Services](apps-MCS.md).







## <a name="deploying-apps"></a>Implementación de aplicaciones

Independientemente del método que use para obtener las aplicaciones, una vez que se haya completado, estará listo para seguir los pasos descritos en [deploy apps to Microsoft Managed Desktop Devices](../get-started/deploy-apps.md).


