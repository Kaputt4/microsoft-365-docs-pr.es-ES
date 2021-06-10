---
title: Aplicaciones en Escritorio administrado de Microsoft
description: Explica cómo se administran las aplicaciones, incluido cómo empaquetar, implementar y admitirlas.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 571acc9c240fc0243998050ac3013258a2f85a3e
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2021
ms.locfileid: "52028949"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Aplicaciones en Escritorio administrado de Microsoft

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>Aplicaciones en general

Microsoft incluye determinadas aplicaciones clave junto con la licencia Microsoft 365 E3 o E5 necesaria para participar en Escritorio administrado de Microsoft. Sin embargo, aunque proporcionamos estas aplicaciones, aún tienes ciertas responsabilidades y acciones que completar.

También puedes implementar aplicaciones adicionales que no son de Microsoft para que los usuarios puedan autoservicio a través de la Portal de empresa o una instalación en segundo plano necesaria, todo con la canalización de implementación de Microsoft Intune. 

## <a name="apps-provided-by-microsoft"></a>Aplicaciones proporcionadas por Microsoft

Se incluyen con la licencia de Escritorio administrado de Microsoft las versiones de 64 bits de las aplicaciones de Aplicaciones Microsoft 365 para empresas Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype Empresarial y OneNote). Las versiones de hacer clic y ejecutar de Microsoft Project  y Visio no se incluyen de forma predeterminada, pero puede solicitar que se agregó. Para obtener más información acerca de estas aplicaciones, [vea Install Microsoft Project or Microsoft Visio on Escritorio administrado de Microsoft devices](../get-started/project-visio.md).

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Qué hace Microsoft para admitir las aplicaciones que proporcionamos

Microsoft proporcionará un servicio completo para la implementación, actualización y compatibilidad con las aplicaciones Aplicaciones Microsoft 365 para empresas incluidas. Las versiones de hacer clic y ejecutar de  Microsoft Project y Visio no se incluyen de forma predeterminada, pero Escritorio administrado de Microsoft proporcionará grupos de implementación que permiten al administrador de TI administrar licencias e implementar estas aplicaciones adecuadamente para su organización. Microsoft admitirá a los usuarios de estas aplicaciones a través Escritorio administrado de Microsoft de soporte técnico.

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>Qué debes hacer para admitir las aplicaciones que proporcionamos

Todavía hay ciertas cosas que debes hacer con estas aplicaciones:

- **Asignar licencias:** es responsable de obtener y asignar las licencias adecuadas a los usuarios para Aplicaciones Microsoft 365 para empresas.
- **Agregar usuarios a grupos** de seguridad: si usa Microsoft Project o Visio, el administrador de TI debe agregarlos a los grupos de implementación adecuados. Los administradores de TI también son responsables de reclamar licencias a esos usuarios si abandonan la compañía.
- **Implementar Microsoft 365 complementos:** si necesitas complementos para cualquiera de las aplicaciones de Aplicaciones Microsoft 365 para empresas, impleméntelos de forma centralizada como cualquier otra aplicación Windows 32. 

## <a name="apps-you-provide"></a>Aplicaciones que proporcionas

Probablemente tenga otras aplicaciones que necesite para sus operaciones empresariales. Estas aplicaciones solo se pueden implementar en Escritorio administrado de Microsoft dispositivos mediante la canalización de Microsoft Intune de implementación de Microsoft Intune. Para obtener más información acerca de la implementación de aplicaciones, siga los pasos descritos en [Deploy apps to Escritorio administrado de Microsoft devices](../get-started/deploy-apps.md).

### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Preparar tus propias aplicaciones para su inclusión en Escritorio administrado de Microsoft
Revisa tus aplicaciones y comprueba:

- Ninguna de las aplicaciones está prohibida o tiene un comportamiento restringido, como se describe en [Escritorio administrado de Microsoft requisitos de la aplicación.](../service-description/mmd-app-requirements.md)
- Las aplicaciones deben estar listas para la administración Microsoft Intune. Para obtener más información sobre este tema, consulta [Windows 10 implementación de aplicaciones con Microsoft Intune](/intune/apps-windows-10-app-deploy) y Agregar aplicaciones a [Microsoft Intune](/intune/apps-add).
- Otros requisitos de empaquetado previo, como proporcionar claves de licencia, acuerdo con términos de licencia y establecer previamente conexiones de servidor.

## <a name="steps-to-get-ready"></a>Pasos para prepararse

1. Revisar [Requisitos previos para Escritorio administrado de Microsoft](prerequisites.md).
2. Usar [herramientas de evaluación de preparación](readiness-assessment-tool.md).
3. [Requisitos previos para las cuentas de invitado](guest-accounts.md)
4. [Configuración de red para el Escritorio administrado de Microsoft](network.md)
5. [Preparar los certificados y los perfiles de red para el Escritorio administrado de Microsoft](certs-wifi-lan.md)
6. [Preparar el acceso a los recursos locales para el Escritorio administrado de Microsoft](authentication.md)
7. [Aplicaciones en Escritorio administrado de Microsoft](apps.md) (este artículo)
8. [Preparar unidades asignadas para el Escritorio administrado de Microsoft](mapped-drives.md)
9. [Preparar recursos de impresión para el Escritorio administrado de Microsoft](printing.md)
