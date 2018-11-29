---
title: Prepare la organización para Windows 10 Enterprise
description: Proporciona una orientación de alto nivel en los pasos que necesarios para implementar Windows 10 Enterprise en los equipos como parte de Microsoft 365 Enterprise.
keywords: Microsoft, Microsoft 365 Enterprise, Microsoft 365 documentación, Enterprise del 10 de Windows, la implementación de 365
author: JoeDavies-MSFT
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: josephd
ms.openlocfilehash: 21a4198c688e1865a029f18ff3ceeb2155d419e4
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871693"
---
# <a name="step-1-prepare-your-organization-for-windows-10-enterprise"></a>Paso 1: Preparar la organización para Windows 10 Enterprise

*En este artículo se aplica a la E3 y E5 versiones de Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Antes de actualizar los dispositivos de Windows 10 Enterprise, tenga en cuenta lo siguiente:

- **Los dominios deben ser agregados y comprobados** <br>Con una suscripción a Microsoft 365, obtenga un nombre de dominio predeterminado que termina en onmicrosoft.com (por ejemplo, contoso.onmicrosoft.com). La mayoría de las organizaciones prefieren usar uno o varios de los dominios que poseen para finalizan sus direcciones de correo electrónico en su propio nombre de dominio (como username@contoso.com). Para usar su propio dominio, debe agregarlo a Microsoft 365 y compruebe que es propietario. Se recomienda que agregue y compruebe los dominios ahora para que estén listos para ir siempre que se establezca los servicios de Microsoft 365, como correo electrónico y Skype para la empresa.
- **No es necesario agregar usuarios en este momento** <br>Para usar los servicios de Microsoft 365 o instalar los productos de Microsoft 365, los usuarios necesitan cuentas en Microsoft 365 y que necesitan licencias de producto. Cómo agregar usuarios a Microsoft 365 depende del número de usuarios y si actualmente dispone de Active Directory local. Si no dispone de Active Directory (o tener Active Directory pero no desea sincronizar a Microsoft 365), puede agregar los usuarios directamente a Microsoft 365 y asignar licencias, individualmente o de forma masiva.<br>Si dispone de Active Directory local, se puede [sincronizar con Microsoft 365](identity-azure-ad-connect-health.md) para crear cuentas de usuario en el directorio de la nube utilizado por Microsoft 365 de Azure AD. Con este método, puede crear cuentas para los usuarios y grupos de seguridad que se usan para administrar los permisos a los recursos (como documentos o colecciones de sitios de SharePoint Online). Sincronización de Active Directory con Microsoft 365 no asigna licencias a los usuarios.
- **No es necesario que los usuarios de la licencia en este momento** <br>Antes de que los usuarios pueden usar los servicios de Microsoft 365 o instalar software desde el portal de Microsoft 365, que necesitan licencias de producto. Como un administrador de control de usuario o global, puede asignar directamente las licencias de productos de Microsoft 365 individualmente o de forma masiva. También puede usar [basadas en grupos de licencias](identity-group-based-licensing.md) para asignar automáticamente licencias cuando se agregan usuarios a un grupo determinado. 
- **Instale Office 365 ProPlus por separado** <br>Obtención de una licencia de Microsoft 365 no instala automáticamente Office 365 ProPlus en los equipos cliente. Vea [fase 4: Office 365 ProPlus](office365proplus-infrastructure.md) para obtener más información. 

## <a name="set-windows-diagnostics-data-level"></a>Establecer nivel de datos de diagnóstico de Windows

Microsoft utiliza datos de diagnóstico para ayudar a mantener Windows dispositivos seguro mediante la identificación de tendencias de malware y otras amenazas y para mejorar la calidad de los servicios de Windows y Microsoft. Debe asegurarse de que el servicio de diagnóstico está habilitado en un nivel mínimo de básica en todos los extremos de la organización. *De forma predeterminada, este servicio está habilitado y configurado con el nivel mejorado.* Sin embargo, es recomendable comprobar y asegúrese de que se reciben datos de detección. Establecer niveles de a través de las directivas de invalida la configuración de nivel de dispositivo. 

**Niveles de datos de diagnóstico de sistema operativo Windows 10**

Puede configurar la configuración de datos de diagnóstico de sistema operativo mediante las herramientas de administración que ya está utilizando, por ejemplo, directiva de grupo, MDM y aprovisionamiento de Windows. Puede cambiar manualmente la configuración mediante el Editor del registro. Establecer los niveles de datos de diagnóstico a través de una directiva de administración, invalida cualquier configuración de nivel de dispositivo.

Utilice el valor adecuado en la tabla siguiente al configurar la directiva de administración.

| Nivel | Datos recopilados | Valor |
|:--- |:--- |:--- |
| Seguridad | Datos de seguridad. | 0 |
| Basic | Datos de seguridad y del sistema básicos y datos de calidad. | 1  |
| Mejorado | Datos de seguridad, sistema básico y datos de calidad y conocimientos mejoradas y datos de confiabilidad avanzada. | 2  |
| Full | Datos de seguridad, sistema básico y datos de calidad, conocimientos mejoradas y datos de confiabilidad avanzada y datos de diagnóstico completa. | 3  |

Puede habilitar los datos de diagnóstico a través de cualquiera de estos métodos:

* **Microsoft Intune** - si tiene previsto usar Intune para administrar los dispositivos, puede crear una directiva de configuración para habilitar los datos de diagnóstico mediante la configuración de la directiva del sistema <a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SystemAllowTelemetry</a> . Para obtener más información acerca de cómo configurar las directivas de configuración, vea [Administrar la configuración y características de los dispositivos con Microsoft Intune directivas](https://aka.ms/intuneconfigpolicies).
* **El Editor del registro** , puede usar el Editor del registro para habilitar de forma manual los datos de diagnóstico en cada dispositivo en la organización. Como alternativa, puede escribir una secuencia de comandos para modificar el registro. Si ya existe una directiva de administración, como la directiva de grupo o MDM, invalidará esta configuración del registro.
* **Directiva de grupo** - si no planea inscribirse dispositivos en Intune, puede usar un objeto de directiva de grupo para establecer el nivel de datos de diagnóstico de la organización.
* **El símbolo del sistema** - puede establecer datos de diagnóstico de Windows 10 y el servicio se inicie automáticamente con el símbolo del sistema. Este método es mejor si está probando el servicio en solo unos dispositivos. Habilitar el servicio se inicie automáticamente con este comando no va a configurar el nivel de datos de diagnóstico. Si no ha configurado un nivel de datos de diagnóstico mediante las herramientas de administración, el servicio funcionará con el valor predeterminado de nivel mejorado.

Ver [datos de diagnóstico de configuración de Windows en su organización](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization) para obtener más información acerca de los datos de diagnóstico de Windows y cómo se puede habilitar que se basa en el método que elija.

Como control provisional, puede consultar los [criterios de salida](windows10-exit-criteria.md#crit-windows10-step1) correspondientes a este paso.

## <a name="next-step"></a>Paso siguiente

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [Implementar Enterprise del 10 de Windows para dispositivos existentes como una actualización en contexto](windows10-deploy-inplaceupgrade.md) |






