---
title: Aplicaciones en Escritorio administrado de Microsoft
description: Explica cómo se administran las aplicaciones, incluido cómo empaquetar, implementar y admitirlas.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: ce43080c284c4c15be5a8799f70a43de611ff9ba
ms.sourcegitcommit: cafca45069819a44c7cf8c67f6c1e105de1b3393
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2022
ms.locfileid: "62520444"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Aplicaciones en Escritorio administrado de Microsoft

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->

## <a name="apps-generally"></a>Aplicaciones en general

Microsoft incluye determinadas aplicaciones clave junto con la licencia Microsoft 365 E3 o E5 necesaria para participar en Microsoft Managed Desktop. Sin embargo, aunque proporcionamos estas aplicaciones, aún tienes ciertas responsabilidades y acciones que completar.

También puedes implementar aplicaciones adicionales que no son de Microsoft para los usuarios a través del autoservicio a través del Portal de empresa, o una instalación en segundo plano necesaria mediante la canalización de implementación de Microsoft Intune.

## <a name="apps-provided-by-microsoft"></a>Aplicaciones proporcionadas por Microsoft

La licencia de Escritorio administrado de Microsoft incluye versiones de 64 bits de las aplicaciones de Aplicaciones Microsoft 365 para Enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Teams y OneNote).)

Las versiones de hacer clic y ejecutar de Microsoft Project y Visio no se incluyen de forma  predeterminada, pero puede solicitar que se agregó. Para obtener más información acerca de estas aplicaciones, [consulte Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Qué hace Microsoft para admitir las aplicaciones que proporcionamos

Microsoft proporcionará un servicio completo para la implementación, actualización y compatibilidad con las aplicaciones Aplicaciones Microsoft 365 para empresas incluidas. Las versiones de hacer clic y ejecutar Microsoft Project y Visio *no se* incluyen de forma predeterminada. Sin embargo, Microsoft Managed Desktop proporcionará grupos de implementación para permitir que el administrador de TI administre las licencias e implemente estas aplicaciones adecuadamente para su organización. Microsoft admitirá a los usuarios de estas aplicaciones a través de los canales de soporte técnico de Escritorio administrado de Microsoft.

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>Qué debes hacer para admitir las aplicaciones que proporcionamos

Todavía hay ciertas cosas que debes hacer con estas aplicaciones:

| Tarea | Descripción |
| ------ | ------ |
| Asignar licencias | Es responsable de obtener y asignar las licencias adecuadas a los usuarios para Aplicaciones Microsoft 365 para empresas. |
| Agregar usuarios a grupos de seguridad | Si está usando Microsoft Project o Visio, el administrador de TI debe agregar esos usuarios a los grupos de implementación adecuados. Los administradores de TI también son responsables de reclamar licencias a esos usuarios si abandonan la compañía. |
| Implementar Microsoft 365 complementos | Si necesitas complementos para cualquiera de las aplicaciones Aplicaciones Microsoft 365 para empresas, impleméntelas de forma centralizada como cualquier otra aplicación Windows 32.

## <a name="apps-you-provide"></a>Aplicaciones que proporcionas

Probablemente tenga otras aplicaciones que necesite para sus operaciones empresariales. Estas aplicaciones solo se pueden implementar en dispositivos de Escritorio administrado de Microsoft mediante la canalización de Microsoft Intune de implementación de microsoft. Para obtener más información acerca de la implementación de aplicaciones, siga los pasos descritos [en Implementar aplicaciones en dispositivos de Escritorio administrado de Microsoft](../get-started/deploy-apps.md).

### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Preparar tus propias aplicaciones para su inclusión en Microsoft Managed Desktop

Revisa tus aplicaciones y comprueba:

- Ninguna de las aplicaciones está prohibida o tiene un comportamiento restringido, como se describe en [Requisitos de aplicaciones de Escritorio administrado de Microsoft](../service-description/mmd-app-requirements.md).
- Las aplicaciones deben estar listas para la administración Microsoft Intune. Para obtener más información, [consulta Windows 10 implementación de aplicaciones con Microsoft Intune](/intune/apps-windows-10-app-deploy) [y Agregar aplicaciones a Microsoft Intune](/intune/apps-add).
- Otros requisitos de empaquetado previo, como proporcionar claves de licencia, acuerdo con términos de licencia y establecer previamente conexiones de servidor.

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>Pasos para prepararse para El escritorio administrado de Microsoft

1. Revisar los [requisitos previos del Escritorio administrado de Microsoft](prerequisites.md)
1. Ejecutar las [herramientas para evaluar la preparación](readiness-assessment-tool.md).
1. Comprar el [Portal de empresa](../get-started/company-portal.md).
1. Revisar los [requisitos previos para las cuentas de invitado](guest-accounts.md).
1. Comprobar la [configuración de red](network.md).
1. [Preparar los certificados y perfiles de red](certs-wifi-lan.md).
1. [Preparar el acceso de usuario a los datos](authentication.md).
1. Preparar aplicaciones (en este artículo).
1. [Preparar las unidades asignadas](mapped-drives.md).
1. [Preparar los recursos de impresión](printing.md).
1. [Nombres del dispositivo](address-device-names.md) de dirección.
