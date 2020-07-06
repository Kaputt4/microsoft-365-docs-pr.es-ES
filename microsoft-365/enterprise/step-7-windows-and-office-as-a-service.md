---
title: 'Paso 7: Mantenimiento de Windows y Office'
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/20/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Obtenga información sobre cómo prepararse para mantener Windows y Office en su entorno.
ms.openlocfilehash: e9de339c6bc66e5cd3c02af5f6a53c32b7573b1f
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679007"
---
# <a name="step-7-windows-and-office-servicing"></a>Paso 7: Mantenimiento de Windows y Office

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-10.png" alt="Step 7" height="144" width="144" /></td>
<td><p><strong>Paso 7: Mantenimiento de Windows y Office</strong></p>
<p>Both Windows 10 and Microsoft 365 Apps for enterprise continually add new capabilities to keep bringing user experiences and security forward with the latest innovations. Learn how to stay current with semi-annual and monthly updates, how the new servicing model works and the tools and options you have.</p></td>
<td><a href="https://aka.ms/ddev7" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-20.png" alt="Step 7" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>Mantenimiento de Windows y Office es el séptimo paso del ciclo de proceso de implementación recomendado, que cubre los aspectos de planificación para preparar las actualizaciones semianuales. Para ver el proceso de implementación de escritorio completo, visite el [Centro de implementación de escritorio](https://aka.ms/HowToShift).
>

Windows 10 y Aplicaciones de Microsoft 365 para empresas presentan nuevas opciones de mantenimiento, modelos de soporte técnico y escalas de tiempo de actualización. Estos cambios simplifican el proceso para mantenerse al día con las características más recientes. Además de estas actualizaciones, hay nuevas opciones de configuración para habilitar planes de mantenimiento que se adapten a sus necesidades. Veamos cómo puede prepararse para las actualizaciones de canal semestrales que ofrecen nuevas características y funcionalidades en Windows 10 y Aplicaciones de Microsoft 365 para empresas mientras aprovecha nuevas características de la rama actual de Microsoft Endpoint Configuration Manager.

[Ayudar a los clientes a pasar a Aplicaciones de Microsoft 365 para empresas y Windows 10](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/)

## <a name="update-types"></a>Tipos de actualización

Las actualizaciones se dividen en dos categorías principales, actualizaciones de características y actualizaciones de seguridad y de calidad que contienen correcciones de errores, de fiabilidad y de seguridad acumulativas. En cuanto a la cadencia Windows y Office tiene un canal semestral que ofrece nuevas características dos veces al año en marzo y septiembre, mientras que las actualizaciones de seguridad y calidad se producen mensualmente. Además, solo para las aplicaciones de Office 365, le ofrecemos una opción de canal actual totalmente compatible donde las actualizaciones contienen características nuevas y actualizaciones de calidad.

Si está acostumbrado a un ciclo más largo entre el sistema operativo y las actualizaciones de las aplicaciones, puede que se pregunte:

  - ¿Serán compatibles las actualizaciones?

  - ¿Tendré que volver a formar a mis usuarios?

  - ¿Y cuáles son los riesgos?

Para responder a estas preguntas y a las razones para implementar nuevas funcionalidades con más frecuencia, mostraremos algunas de las ventajas de este método

### <a name="feature-update-benefits"></a>Ventajas de la actualización de características

First, we’ve moved away from the model of the past that would introduce huge waves of change around every three years to now incremental smaller changes with feature updates twice per year. Why? With technology trends moving so fast in addition to rapidly evolving security threats, this keeps experiences and protections current. Some of the security related updates for example can’t just be delivered by monthly security updates or antivirus signature files; they may be low-level changes platform, like virtualization-based security.

[Guía rápida de Windows como servicio](https://docs.microsoft.com/windows/deployment/update/waas-quick-start)

[Mitigue las amenazas con las características de seguridad de Windows 10](https://docs.microsoft.com/windows/security/threat-protection/overview-of-threat-mitigations-in-windows-10%20%20)

### <a name="cumulative-update-model-benefits"></a>Ventajas del modelo de actualización acumulativa

Second delivering quality and security updates as a cumulative update package corrects many of the issues of the past. It used to be that you might pick and choose sometimes from a dozen updates or more each month for both Windows and Office. As you can imagine, this creates a nearly impossible set of test matrices for support. Also, if you install a version of Windows or Office that is a year or more old, it might take hours or sometimes days to apply all updates delivered since that version was released.

With the cumulative model, you’re always one update away from being current and in doing so the number of monthly updates that you need to deploy is reduced. Each update builds upon updates from previous months and contains all of the fixes that you need to get current. Cumulative updates are especially helpful when PCs has been turned off for several months because they are in storage waiting to be reassigned to a different user.

### <a name="expanded-validation-of-updates"></a>Validación expandida de las actualizaciones

Otra ventaja es que, antes de distribuir las actualizaciones para una implementación amplia, publicamos compilaciones a través de los programas Insider de [Office](https://products.office.com/office-insider?tab=Windows-Desktop) y [Windows](https://insider.windows.com/), y esto nos permite recopilar datos de diagnóstico y comentarios antes de publicar actualizaciones para todos los usuarios. Ahora los programas Insider están disponibles para todo el mundo de forma que pueda comprender antes las actualizaciones. Cuando se publiquen las actualizaciones habremos recibido datos de diagnóstico de millones de configuraciones, así que cuando distribuimos las actualizaciones, la calidad será intrínsecamente más predecible

Y una cosa más: como las compilaciones de Aplicaciones de Microsoft 365 para empresas Insider reflejan actualizaciones de canal mensuales, si usa un canal semestral para presentar actualizaciones de características de Office dos veces al año alineado con Windows, puede validar esas compilaciones, además de usar el Canal empresarial semestral (vista previa).

### <a name="supporting-management-tools"></a>Compatibilidad con herramientas de administración

We've also thought through how to make the deployment of updates seamless to you. Configuration Manager (Current Branch) is updated frequently to support the roll-out of these updates to Windows and Office and any new capabilities.

[Implementación de actualizaciones de Windows 10 con Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)

[Administrar Aplicaciones de Microsoft 365 para empresas con Configuration Manager](https://docs.microsoft.com/mem/configmgr/sum/deploy-use/manage-office-365-proplus-updates)

## <a name="overview-of-windows-and-office-channels"></a>Información general sobre los canales de Office y Windows

Windows 10 ofrece tres canales de mantenimiento:

- [**El Programa Windows Insider**](https://docs.microsoft.com/windows/deployment/update/waas-overview#windows-insider) para que las organizaciones prueben las características proporcionadas en la próxima actualización de características y envíen comentarios sobre ellas
- **El Canal semianual** proporciona nuevas características con la publicación de Actualización de características dos veces al año
- **El Canal de mantenimiento a largo plazo** está diseñado solo para dispositivos especializados que necesiten una opción mantenimiento más larga

Microsoft 365 ofrece cuatro canales de mantenimiento:

- [**El Programa Office Insider**](https://products.office.com/office-insider) para que las organizaciones prueben las características más recientes y funcionalidades de Office en desarrollo y envíen comentarios sobre ellos
- **El Canal actual** proporciona a los usuarios las características más recientes de Office tan pronto como estén disponibles
- **El Canal empresarial semestral** proporciona nuevas funcionalidades con nuevas características dos veces al año
- **El Canal empresarial semestral (vista previa)** es una versión totalmente compatible de Office que permite a los usuarios piloto y los evaluadores de compatibilidad de la aplicación probar y validar el siguiente Canal empresarial semestral

Para obtener más información acerca de los canales de mantenimiento de Windows y Office revise la siguiente documentación:

- [Overview of Windows as a Service](https://docs.microsoft.com/windows/deployment/update/waas-overview#servicing-channels) (Información general sobre Windows como servicio)
- [Información general sobre los canales de actualización de Aplicaciones de Microsoft 365](https://docs.microsoft.com/DeployOffice/overview-update-channels#BKMK_SAC)

## <a name="phased-deployment-of-updates"></a>Implementación de actualizaciones por fases

Now let’s shift gears to how you will roll out these updates. For any release, we recommend at least three deployment phases for IT – validation, piloting and broad production deployment. Once you’re up and running on Windows 10 and Microsoft 365 Apps for enterprise, you'll use monthly servicing to stay current with critical security and quality updates, then you’ll move to semi-annual servicing for new features.

### <a name="monthly-updating"></a>Actualización mensual

The service model is designed so you can choose to limit the roll-out of new features to twice per year, and if needed you can even skip a semi-annual update and continue receiving quality and security updates. As mentioned, the cumulative nature of monthly updates means each will increase in size per month.

#### <a name="express-updates"></a>Actualizaciones rápidas

Using a technology called "Express Updates" in Windows and Binary Delta Compression in Office, we can reduce the download size significantly. In both approaches, the update engines compare what’s on the PC and finds only the differentials needed to update what’s there.

[Actualizaciones de calidad de Windows 10 explicadas y el final de actualizaciones de delta](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Windows-10-quality-updates-explained-amp-the-end-of-delta/ba-p/214426)

Windows Update para empresas y Windows Server Update Services han sido compatibles con las actualizaciones rápidas durante mucho tiempo, pero ahora hemos extendido esa compatibilidad a la rama actual de Microsoft Endpoint Configuration Manager para que también pueda usar las actualizaciones rápidas.

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-3.png)

#### <a name="binary-delta-compression"></a>Compresión binaria de delta

La compresión binaria de delta en Office solo se usa si está actualizando al a versión más reciente de Aplicaciones de Microsoft 365 para empresas, por lo que no use este enfoque si necesita actualizar a partir de la versión anterior y no puede omitir las actualizaciones.

Windows and Office update channels can be managed via Configuration Manager using the standard approval and targeting process. Additionally, you can use policy settings in Office and Windows to enforce update channels used, as well as related settings.

### <a name="semi-annual-updates"></a>Actualizaciones semianuales

Esas son las consideraciones para las actualizaciones mensuales, pasemos ahora a las actualizaciones semianuales.

Como tratamos en Preparación de dispositivos y aplicaciones, es preferible empezar sus preparativos para las actualizaciones grandes con las mismas herramientas establecidas en el Paso 1 del proceso de implementación.

As for tooling, you can use policy settings with Windows Update for Business, software update management via Microsoft Endpoint Configuration Manager (Current Branch), Windows Server Update Services (WSUS), or update policies set by Microsoft Intune. If you are concerned about network bandwidth, see Step 2: Directory and Network Readiness, to learn about your options to reduce network traffic via Delivery Optimization and other peer to peer caching technologies.

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-4.png)

[Canal semianual de Windows](https://docs.microsoft.com/windows/deployment/update/waas-overview#semi-annual-channel)

[Canal empresarial semestral para aplicaciones de Microsoft 365](https://docs.microsoft.com/DeployOffice/overview-update-channels#BKMK_SAC)

#### <a name="upgrade-task-sequences"></a>Actualizar las secuencias de tareas

Instalar las actualizaciones de características más grandes a través de rutinas de administración de actualización de software estándar es una opción admitida, pero muchas organizaciones optarán por usar una secuencia de tareas de actualización con la rama actual de Microsoft Endpoint Configuration Manager o Microsoft Deployment Toolkit.

Una secuencia de tareas le permite crear comprobaciones o tareas personalizadas antes de instalar la actualización de características y le permite realizar tareas personalizadas tras la instalación de la actualización. Las tareas postactualización podrían incluir suspender servicios de forma temporal en caso necesario durante la actualización, la instalación y sustitución de controladores, la aplicación de mejoras o las características de personalización de la barra de tareas y la aplicación de mejoras personalizadas de Windows 10.

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-5.png)

If you’re already using task sequences to migrate your Windows 7 machines to Windows 10 and are well-versed with those tools, this is a great place to start and provides ultimate control. While you can use a single task sequence for the entire upgrade, it is quite common that organizations use two task sequences. One task sequence for making sure the machines are ready for the upgrade, that silently pre-stages all the required setup files on target computers, and one to do the actual upgrade. This approach ensures that your user productivity is less impacted.

[Creación de una secuencia de tareas para actualizar un sistema operativo en Configuration Manager](https://docs.microsoft.com/mem/configmgr/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system)

#### <a name="semi-annual-channel-support-for-feature-updates"></a>Compatibilidad de canal semianual para actualizaciones características

[Como se anunció en septiembre de 2018](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/), la escala de tiempo de las actualizaciones del canal semianual usará el modelo siguiente.

  - Todas las actualizaciones de características admitidas de Windows 10 Enterprise y educación, empezando con la versión 1607 serán compatibles durante 30 meses a partir de su fecha de salida original.

  - Todas las actualizaciones de características, empezando con la 1809, con un objetivo de septiembre, recibirán 30 meses de compatibilidad a partir de su fecha de salida.

  - Las actualizaciones de características futuras con fecha de salida marzo y empezando por la 1903, seguirán teniendo apoyo durante otros 18 meses a partir de su fecha de salida.

  - Las actualizaciones semianuales de Aplicaciones de Microsoft 365 para empresas seguirán teniendo apoyo durante 18 meses.

#### <a name="additional-setup-automation-options-outside-of-task-sequences"></a>Opciones de automatización adicionales fuera de la secuencia de tareas

Si no usa secuencias de tareas personalizadas, puede ejecutar acciones personalizadas o aplicar archivos de controladores durante la actualización de características en la fase de preinstalación, antes de que la configuración acabe de ejecutar sus pruebas de compatibilidad, o en la fase de precompromiso, antes de que se aplique la actualización.

[Novedades de la configuración de Windows 10, versión 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803%23windows-setup)

## <a name="next-step"></a>Paso siguiente 

## <a name="step-8-user-communications-and-training"></a>[Paso 8: Comunicación con los usuarios y aprendizaje](https://aka.ms/mdd8)

## <a name="previous-step"></a>Paso anterior 

## <a name="step-6-os-deployment-and-feature-updates"></a>[Paso 6: Implementación del sistema operativo y actualizaciones de características](https://aka.ms/mdd6)
