---
title: Actualizar los usuarios de Microsoft 365 para empresas al último cliente de Office
f1.keywords:
- NOCSH
ms.author: kwekuako
author: kwekuako
manager: scotv
audience: Admin
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.custom:
- fwlink 824861; CampaignID O365_Comm_SR_UpgradeOffice
- AdminSurgePortfolio
ms.assetid: f6b00895-b5fd-4af6-a656-b7788ea20cbb
description: Obtenga información sobre cómo actualizar a los usuarios al último cliente de Office.
ms.openlocfilehash: fb2513b2112dd8427222d43d14184895df3b594b
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "44778882"
---
# <a name="upgrade-your-microsoft-365-for-business-users-to-the-latest-office-client"></a>Actualizar los usuarios de Microsoft 365 para empresas al último cliente de Office

## <a name="office-2010-reaches-end-of-support"></a>Office 2010 alcanza la finalización del soporte técnico

Office 2010 alcanzará su fin de soporte el 13 de octubre de 2020. Cuando Office 2010 llegue a su fin de soporte técnico, Microsoft dejará de proporcionar lo siguiente:

- Soporte técnico para problemas

- Correcciones de errores para problemas detectados

- Revisiones de seguridad de vulnerabilidades detectadas

Para obtener más información, consulte [Office 2010 End of Support Roadmap](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap) .

 **¿Es este el tema adecuado para usted?**
  
 Si es el administrador responsable de la suscripción a Microsoft 365 para empresas en su organización, está en el punto correcto. Los administradores suelen ser responsables de tareas como la administración de usuarios, el restablecimiento de contraseñas, la administración de instalaciones de Office y la adición o eliminación de licencias.

 Si no es un administrador y tiene un producto de la [familia de Microsoft 365](https://support.microsoft.com/office/28cbc8cf-1332-4f04-9123-9b660abb629e#BKMK_OfficePlans) , vea [¿Cómo puedo actualizar Office](https://support.microsoft.com/office/ee68f6cf-422f-464a-82ec-385f65391350) para obtener información sobre cómo actualizar la versión de Office más antigua y de uso doméstico).

## <a name="get-ready-to-upgrade"></a>Prepararse para la actualización

Como administrador, puede controlar qué versión de los usuarios de Office de su organización puede instalar. Se recomienda encarecidamente que los usuarios de la organización que ejecutan versiones anteriores de Office como Office 2010, Office 2013 o Office 2016 se actualicen a la versión más reciente para aprovechar sus mejoras de seguridad y productividad.

## <a name="upgrade-steps"></a>Pasos de la actualización

Los pasos siguientes le guiarán a través del proceso de actualización de los usuarios al cliente de escritorio de Office más reciente. Le recomendamos que lea estos pasos antes de comenzar el proceso de actualización.
  
## <a name="step-1---check-system-requirements"></a>Paso 1: comprobar los requisitos del sistema

[Compruebe los requisitos del sistema](https://products.office.com/office-system-requirements) para Office para asegurarse de que los dispositivos son compatibles con la última versión de Office. Por ejemplo, las versiones más recientes de Office no se pueden instalar en equipos que ejecuten Windows XP o Windows Vista.
  
> [!TIP]
> Si tiene usuarios en su organización que ejecutan versiones anteriores de Windows en sus PC o portátiles, le recomendamos que actualice a Windows 10. Windows 7 ha llegado al final del soporte técnico. La [compatibilidad de lectura con Windows 7 finaliza en el 2020 de enero](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) para obtener más información.

Consulte los [requisitos del sistema de Windows 10](https://www.microsoft.com/windows/windows-10-specifications) para ver si puede actualizar sus sistemas operativos.

### <a name="check-application-compatibility"></a>Comprobar la compatibilidad de aplicaciones

Para asegurarse de que la actualización se realiza correctamente, se recomienda identificar las aplicaciones de Office (incluidas las secuencias de comandos VBA, macros, Complementos de terceros, hojas de cálculo y documentos complejos) y evaluar la compatibilidad con la última versión de Office.
  
Por ejemplo, si está usando complementos de terceros con su instalación actual de Office, póngase en contacto con el fabricante para asegurarse de que son compatibles con la última versión de Office.
  
## <a name="step-2---check-your-existing-subscription-plan"></a>Paso 2: comprobar el plan de suscripción existente

Algunos planes de Microsoft 365 no incluyen las versiones de escritorio completas de Office y los pasos para la actualización son diferentes si el plan no incluye Office.
  
¿No está seguro de qué plan de suscripción tiene? Vea [¿Qué es la suscripción de Microsoft 365 para empresas?](../admin-overview/what-subscription-do-i-have.md)
  
Si el plan existente incluye Office, vaya al [paso 3: desinstalar Office](#step-3---uninstall-office).
  
Si el plan existente no incluye Office, seleccione una de las siguientes opciones:
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a>Opciones de actualización para los planes que no incluyen Office

 **Opción 1: cambiar las suscripciones de Office**

Cambie a una suscripción que incluya Office. Consulte [cambiar a otro plan de Microsoft 365 para empresas](../../commerce/subscriptions/switch-to-a-different-plan.md).

**Opción 2: comprar una compra individual de una sola vez de Office o comprar Office a través de una licencia por volumen**

 - Compre una compra individual y de pago único de Office. Consulte [Office hogar &amp; Business](https://products.office.com/home-and-business) o [Office profesional](https://products.office.com/professional)

     O

 - Compre varias copias de Office a través de una licencia por volumen. Consulte [comparar conjuntos disponibles a través de licencias por volumen](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison).

## <a name="step-3---uninstall-office"></a>Paso 3: desinstalar Office

Antes de instalar la última versión de Office, le recomendamos que desinstale todas las versiones anteriores de Office. Sin embargo, si cambia de opinión sobre la actualización de Office, tenga en cuenta los siguientes casos en los que no podrá reinstalar Office después de desinstalarlo.
  
Se recomienda si tiene complementos de terceros, póngase en contacto con el fabricante para ver si hay una actualización que funcione con la última versión de Office.

### <a name="select-the-version-of-office-you-want-to-uninstall"></a>Seleccione la versión de Office que desea desinstalar

- [Desde un equipo PC](https://support.microsoft.com/office/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8)

- [Desde un equipo Mac](https://support.microsoft.com/office/eefa1199-5b58-43af-8a3d-b73dc1a8cae3)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a>Problemas conocidos al intentar reinstalar versiones anteriores de Office después de una desinstalación

 **Office a través de una licencia por volumen** Si ya no tiene acceso a los archivos de origen de estas versiones de licencia por volumen de Office, no podrá volver a instalarlo.

 **Office preinstalado en el equipo** Si ya no tiene una clave de disco o de producto (si Office venía con una) no podrá volver a instalarla.

 **Suscripciones no admitidas** Si su copia de Office se obtuvo a través de suscripciones discontinuas, como Office 365 Small Business Premium u Office 365 mediana empresa, no podrá instalar una versión anterior de Office a menos que tenga la clave del producto que venía con la suscripción.

Si prefiere instalar la versión anterior de Office en paralelo con la versión más reciente, puede ver una lista de las versiones en las que se admite esto, [instalar y usar diferentes versiones de Office en el mismo PC](https://support.microsoft.com/office/6ebb44ce-18a3-43f9-a187-b78c513788bf). Una instalación en paralelo puede ser la opción adecuada para usted, por ejemplo, si ha instalado complementos de terceros que está usando con su versión anterior de Office y no está seguro de que son compatibles con la versión más reciente.

## <a name="step-4---assign-office-licenses-to-users"></a>Paso 4: asignar licencias de Office a los usuarios

Si aún no lo ha hecho, asigne licencias a cualquier usuario de su organización que necesite instalar Office, vea [asignar licencias a usuarios en Microsoft 365 para empresas](../manage/assign-licenses-to-users.md).
  
## <a name="step-5---install-office"></a>Paso 5: instalar Office

Una vez que haya comprobado que todos los usuarios que desea actualizar tienen licencias, el último paso consiste en hacer que instalen Office, vea [Descargar e instalar o volver a instalar Office en su PC o Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658).
  
> [!TIP]
> Si no desea que los usuarios instalen Office ellos mismos, consulte [administrar la configuración de descarga de software en office 365](https://docs.microsoft.com/DeployOffice/manage-software-download-settings-office-365). Puede usar la [herramienta de implementación de Office](https://docs.microsoft.com/DeployOffice/overview-office-deployment-tool) para descargar el software de Office en la red local y, a continuación, implementar Office con el método de implementación de software que suela usar.
