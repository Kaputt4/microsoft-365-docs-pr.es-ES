---
title: Preparar la organización para Windows 10 Enterprise
description: Proporciona instrucciones de alto nivel sobre los pasos necesarios para implementar Windows 10 Enterprise en equipos PC como parte de Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, documentación de Microsoft 365, Windows 10 Enterprise, implementación
author: JoeDavies-MSFT
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
f1.keywords:
- NOCSH
ms.author: josephd
ms.openlocfilehash: 9b83082a4dc859c10db03608de2edebdbb633cbe
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085529"
---
# <a name="step-1-prepare-your-organization-for-windows-10-enterprise"></a>Paso 1: preparar la organización para Windows 10 Enterprise

*Este artículo se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*

![Fase 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Antes de actualizar los dispositivos a Windows 10 Enterprise, tenga en cuenta lo siguiente:

- **Los dominios deben agregarse y comprobarse** <br>
  Con una suscripción de Microsoft 365, obtiene un nombre de dominio predeterminado que termina en onmicrosoft.com (por ejemplo, contoso.onmicrosoft.com). La mayoría de las organizaciones prefieren usar uno o más de los dominios que poseen, por lo que sus direcciones de correo electrónico terminan en su propio nombre de dominio (como username@contoso.com). Para usar su propio dominio, tiene que agregarlo a Microsoft 365 y comprobar que es el propietario. Le recomendamos que agregue y compruebe sus dominios ahora para que estén listos para usar cuando configure los servicios de Microsoft 365, como el correo electrónico y Skype empresarial.
- **No es necesario agregar usuarios en este momento.** <br>
  Para usar los servicios de Microsoft 365 o instalar los productos de la 365 de Microsoft, los usuarios necesitan cuentas en Microsoft 365 y necesitan licencias de producto. La forma en que se agregan usuarios a Microsoft 365 depende del número de usuarios y de si actualmente tiene Active Directory local. Si no tiene Active Directory (o tiene Active Directory pero no desea sincronizarlo con Microsoft 365), puede Agregar usuarios directamente a Microsoft 365 y asignar licencias, de forma individual o en masa. <br>
  Si tiene Active Directory local, puede [sincronizarlo con Microsoft 365](identity-add-user-accounts.md#identity-sync) para crear cuentas de usuario en Azure ad, el directorio de la nube usado por Microsoft 365. Con este método, puede crear cuentas para los usuarios y para los grupos de seguridad que use para administrar los permisos de los recursos (como los documentos o colecciones de sitios de SharePoint Online). La sincronización de Active Directory con Microsoft 365 no asignará licencias a los usuarios.
- **No es necesario que tenga licencia para los usuarios en este momento** <br>
  Para que los usuarios puedan usar los servicios de Microsoft 365 o instalar software desde el portal de Microsoft 365, necesitan licencias de producto. Como administrador global o de administración de usuarios, puede asignar directamente licencias de productos en Microsoft 365 de forma individual o en masa. También puede usar [licencias basadas en grupos](identity-use-group-management.md#identity-group-license) para asignar licencias automáticamente cuando se agregan usuarios a un grupo determinado. 
- **Instale Office 365 ProPlus por separado** <br>
  La obtención de una licencia de 365 de Microsoft no instala automáticamente Office 365 ProPlus en los equipos cliente. Consulte [Phase 4: Office 365 ProPlus](office365proplus-infrastructure.md) para obtener más información. 

## <a name="set-windows-diagnostics-data-level"></a>Establecer el nivel de datos de diagnósticos de Windows

Microsoft usa datos de diagnóstico para ayudar a proteger los dispositivos Windows mediante la identificación de tendencias de malware y otras amenazas, así como ayudarnos a mejorar la calidad de Windows y de los servicios de Microsoft. Debe asegurarse de que el servicio de diagnóstico esté habilitado con un nivel mínimo de Basic en todos los puntos de conexión de la organización. *De forma predeterminada, este servicio está habilitado y establecido en el nivel mejorado.* Sin embargo, es aconsejable comprobar y asegurarse de que reciben datos del sensor. La configuración de niveles mediante directivas invalida la configuración de nivel de dispositivo. 

**Niveles de datos de diagnóstico del sistema operativo Windows 10**

Puede establecer la configuración de datos de diagnóstico del sistema operativo con las herramientas de administración que ya está usando, como Directiva de grupo, MDM o aprovisionamiento de Windows. También puede cambiar manualmente la configuración con el editor del registro. La configuración de los niveles de datos de diagnóstico a través de una directiva de administración invalida cualquier configuración de nivel de dispositivo.

Use el valor adecuado de la tabla siguiente cuando configure la Directiva de administración.

| Nivel | Datos recopilados | Valor |
|:--- |:--- |:--- |
| Seguridad | Solo datos de seguridad. | comprendi |
| Básica | Datos de seguridad y datos básicos del sistema y de calidad. | 1 |
| Mejor | Datos de seguridad, datos básicos del sistema y de calidad, y datos mejorados y datos de confiabilidad avanzada. | segundo |
| Full | Datos de seguridad, datos básicos del sistema y de calidad, conocimientos mejorados y datos de confiabilidad avanzada y datos de diagnóstico completos. | 3 |

Puede habilitar los datos de diagnóstico a través de cualquiera de estos métodos:

* **Microsoft Intune** : Si planea usar Intune para administrar los dispositivos, puede crear una directiva de configuración para habilitar los datos de diagnóstico mediante la configuración de la Directiva del sistema <a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SystemAllowTelemetry</a> . Para obtener más información sobre cómo configurar las directivas de configuración, consulte [administrar la configuración y las características en los dispositivos con las directivas de Microsoft Intune](https://aka.ms/intuneconfigpolicies).
* **Editor del** registro: puede usar el editor del registro para habilitar manualmente los datos de diagnóstico en cada dispositivo de la organización. Como alternativa, puede escribir un script para editar el registro. Si ya existe una directiva de administración, como la Directiva de grupo o MDM, invalidará esta configuración del registro.
* **Directiva de grupo** : Si no tiene previsto inscribir dispositivos en Intune, puede usar un objeto de directiva de grupo para establecer el nivel de datos de diagnóstico de su organización.
* **Símbolo del sistema** : puede establecer que los datos y el servicio de diagnóstico de Windows 10 se inicien automáticamente con el símbolo del sistema. Este método es el mejor si está probando el servicio solo en algunos dispositivos. Si se habilita el servicio para que se inicie automáticamente con este comando, no se configurará el nivel de datos de diagnóstico. Si no ha configurado un nivel de datos de diagnóstico con las herramientas de administración, el servicio funcionará con el nivel mejorado predeterminado.

Consulte [Configure Windows Diagnostic Data in your Organization](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization) para obtener más información sobre los datos de diagnóstico de Windows y cómo habilitarlos en función del método que elija.

Como control provisional, puede consultar los [criterios de salida](windows10-exit-criteria.md#crit-windows10-step1) correspondientes a este paso.

## <a name="next-step"></a>Siguiente paso

|||
|:-------|:-----|
|![Paso 2](../media/stepnumbers/Step2.png)| [Implementación de Windows 10 Enterprise para dispositivos existentes como actualización local](windows10-deploy-inplaceupgrade.md) |






