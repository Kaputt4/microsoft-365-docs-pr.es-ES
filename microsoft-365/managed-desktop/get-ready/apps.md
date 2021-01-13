---
title: Aplicaciones en Escritorio administrado de Microsoft
description: Explica cómo se controlan las aplicaciones, incluido cómo empaquetar, implementar y admitirlas.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 20d68ec007ccda82816ad2288428016019f6d4b2
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840698"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Aplicaciones en Escritorio administrado de Microsoft

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>Aplicaciones en general

Microsoft incluye determinadas aplicaciones clave junto con la licencia de Microsoft 365 E3 o E5 necesaria para participar en el Escritorio administrado de Microsoft. Sin embargo, aunque proporcionamos estas aplicaciones, aún tienes ciertas responsabilidades y acciones que completar.

También puedes implementar aplicaciones adicionales que no son de Microsoft para los usuarios para autoservicio a través del Portal de empresa o una instalación en segundo plano necesaria, todo ello mediante la canalización de implementación de Microsoft Intune. Si tienes la experiencia, puedes migrar las aplicaciones que necesites tú mismo; Como alternativa, los servicios de consultoría de Microsoft (MCS) o los proveedores que no son de Microsoft estarán encantados de ayudarle con un proyecto de empaquetado y migración. Para obtener más información acerca de cómo trabajar con MCS, consulte [Trabajar con servicios de consultoría de Microsoft.](apps-MCS.md)


## <a name="apps-provided-by-microsoft"></a>Aplicaciones proporcionadas por Microsoft

Se incluyen con su licencia de Escritorio administrado de Microsoft las versiones de 64 bits de las aplicaciones de Microsoft 365 Apps for enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype Empresarial y OneNote). Las versiones de Hacer clic y  ejecutar de Microsoft Project y Visio no se incluyen de forma predeterminada, pero puede solicitar que se agregó. Para obtener más información acerca de estas aplicaciones, vea [Instalar Microsoft Project o Microsoft Visio en dispositivos de escritorio administrado de Microsoft.](../get-started/project-visio.md)

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Qué hace Microsoft para admitir las aplicaciones que proporcionamos

Microsoft proporcionará un servicio completo para la implementación, actualización y soporte técnico para las aplicaciones incluidas de Aplicaciones de Microsoft 365 para empresas. Las versiones de Hacer clic y  ejecutar de Microsoft Project y Visio no se incluyen de forma predeterminada, pero Escritorio administrado de Microsoft proporcionará grupos de implementación que permiten al administrador de TI administrar licencias e implementar estas aplicaciones de forma adecuada para su organización. Microsoft admitirá a los usuarios de estas aplicaciones a través de los canales de soporte técnico de Escritorio administrado de Microsoft.

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>Lo que debes hacer para admitir las aplicaciones que proporcionamos

Todavía hay ciertas cosas que debes hacer con estas aplicaciones:

- **Asignar licencias:** usted es responsable de obtener y asignar las licencias adecuadas a los usuarios de Aplicaciones de Microsoft 365 para empresas.
- **Agregar usuarios a grupos de** seguridad: si usa Microsoft Project o Visio, el administrador de TI debe agregarlos a los grupos de implementación adecuados. Los administradores de TI también son responsables de recuperar licencias de esos usuarios si abandonan la compañía.
- Implementar complementos de **Microsoft 365:** si necesitas complementos para cualquiera de las aplicaciones de Aplicaciones de Microsoft 365 para empresas, impleméndalos de forma centralizada como cualquier otra aplicación de Windows 32. 

## <a name="apps-you-provide"></a>Aplicaciones que proporcionas

Probablemente tenga otras aplicaciones que necesite para sus operaciones empresariales. Estas aplicaciones solo se pueden implementar en dispositivos de Escritorio administrado de Microsoft mediante la canalización de implementación de Microsoft Intune. Si la aplicación lo necesita, puede empaquetarlos por un proveedor (que podría ser un proveedor que no es de Microsoft o los Servicios de consultoría de Microsoft (MCS)) o si tiene los medios, puede empaquetarlos usted mismo. A continuación, agregue estos paquetes al portal de Escritorio administrado de Microsoft y asígnelos a grupos de Azure Active Directory para desencadenar la implementación. 

Si actualmente implementas tus aplicaciones con Microsoft Endpoint Configuration Manager, Escritorio administrado de Microsoft puede proporcionarte una consulta para evaluar las aplicaciones y descubrir cuáles están listas para migrar a Microsoft Intune y cuáles pueden requerir algún ajuste.


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Preparar sus propias aplicaciones para su inclusión en el Escritorio administrado de Microsoft
Revisa las aplicaciones y comprueba:

- Ninguna de las aplicaciones está prohibida o tiene un comportamiento restringido, como se describe en los requisitos de aplicaciones de [Escritorio administrado de Microsoft.](https://aka.ms/app-req)
- Las aplicaciones deben estar listas para la administración por Parte de Microsoft Intune. Para obtener más información sobre este tema, consulta Implementación de aplicaciones de [Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) con Microsoft Intune y [Agregar aplicaciones a Microsoft Intune.](https://docs.microsoft.com/intune/apps-add)
- Otros requisitos de empaquetado previo, como proporcionar claves de licencia, un acuerdo con los términos de licencia y establecer previamente conexiones de servidor.

### <a name="decide-how-to-package-apps"></a>Decidir cómo empaquetar aplicaciones

Es posible que algunos editores de software independientes requieran que las aplicaciones se empaqueten antes de que se implementen de forma centralizada. "Empaquetado" significa que el instalador de la aplicación está configurado con opciones como claves de licencia, ubicaciones remotas del servidor o accesos directos de escritorio para que la aplicación se pueda instalar en segundo plano.

Hay tres opciones para empaquetar las aplicaciones: 


- Puede empaquetar aplicaciones usted mismo
- Puede trabajar con un proveedor que no es de Microsoft
- Puedes interactuar con MCS para empaquetar tus aplicaciones. Trabajar con el representante de la cuenta microsoft. Para obtener más información, vea [Trabajar con servicios de consultoría de Microsoft.](apps-MCS.md)



## <a name="deploying-apps"></a>Implementación de aplicaciones

Independientemente del método que use para empaquetar aplicaciones, una vez completado, estará listo para seguir los pasos descritos en Implementar aplicaciones en dispositivos de Escritorio administrado [de Microsoft.](../get-started/deploy-apps.md)


