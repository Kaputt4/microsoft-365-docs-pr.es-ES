---
title: Seguridad en el escritorio administrado por Microsoft
description: ''
keywords: Servicio de escritorio administrado de Microsoft, Microsoft 365, documentación
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 0ea0bbc6a8055ee8459fadd85a6fa4ddac14bdb7
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871784"
---
# <a name="security-in-microsoft-managed-desktop"></a>Seguridad en el escritorio administrado por Microsoft

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Mediante el uso de diversas tecnologías de Microsoft, es posible garantizar que los dispositivos de escritorio administrado de Microsoft son seguros y que el equipo de operaciones de seguridad de escritorio administrado de Microsoft puede evitar, detectar y responder a las amenazas avanzadas. No se permiten los productos de seguridad de terceros, aplicaciones y servicios. Microsoft aplicará una línea de base de directiva estándar para asegurarse de dispositivos, identidad, red y datos corporativos se protegen y protegidos.

Estas categorías de exigencia de seguridad se documentan en las secciones siguientes:

- [Seguridad de los datos](#data-security) : ¿cómo asegurarnos de los datos se almacena y se cumpla los requisitos para el posicionamiento de la seguridad de Azure
- [Seguridad de dispositivos](#device-security) : ¿cómo asegurarnos de dispositivos de escritorio administrado de Microsoft son seguros
- [Seguridad de la identidad](#identity-security) : ¿cómo asegurarnos de los usuarios en el lugar de trabajo moderno no están en riesgo
- [Seguridad de red](#network-security) : ¿cómo asegurarnos de un acceso seguro a recursos corporativos
- [Seguridad de la información](#information-security) : ¿cómo asegurarnos de datos corporativos es segura
- [Cuenta con privilegios de acceso](#privileged-account-access) : ¿cómo se restringir el acceso

## <a name="data-security"></a>Seguridad de datos

Datos que se transmiten desde el inquilino se almacenan en las bases de datos de SQL Azure en el inquilino de Microsoft hospedado en los Estados Unidos. Los datos se almacenan y cumpla los requisitos para el posicionamiento de la seguridad de Azure. 

Para obtener más información, vea [seguridad de Microsoft Azure](https://www.microsoft.com/TrustCenter/Security/azure-security).

Esta lista resume los tipos de datos que se transmiten entre Microsoft y su inquilino. 

- De Microsoft en su inquilino
    - Nombres de grupo
    - Configuración de directiva de seguridad
    - Pedidos de dispositivo
    - Cuentas de usuario (msadmin, mstest, Desktop_soc_ro administradas de Microsoft, Desktop_wdgsoc administradas de Microsoft)
    - Asignación de licencias de E5 a los usuarios de 4 anteriores
    - Windows actualización las directivas de actualización de anillos
    - En el futuro, aún más las capacidades se desarrollará para permitir el registro de otros tipos de contenido de configuración incluidas aplicaciones, las directivas y la configuración.
- Desde el inquilino de Microsoft
    - Datos de actualización, el uso y la confiabilidad de dispositivo
    - Datos de implementación y la confiabilidad de la aplicación
    - Datos de implementación de directivas de seguridad y actualización
    - Usuarios asignados a los dispositivos



## <a name="device-security"></a>Seguridad de dispositivos

Para evitar que las infracciones de seguridad, es importante para asegurarse de que todos los dispositivos de escritorio administrado de Microsoft están protegidos y en buen estado. Es igualmente importante para asegurarse de que podemos detectar dispositivos en mal estado y reducir el riesgo tan pronto como sea posible.

En la siguiente tabla se enumera los servicios proporcionados para asegurarse de dispositivos de escritorio administrado de Microsoft son de confianza, buen estado y seguro.

Servicio | Descripción
--- | ---
Antivirus | Se asegurará de:<br>-Windows Defender AV está instalado y configurado<br>-Las definiciones de Windows Defender AV estén actualizadas
Cifrado de volumen completo |    BitLocker de Windows es la solución de cifrado de datos para los dispositivos de escritorio administrado de Microsoft.<br><br>Una vez que una organización se onboarded en el servicio, se cifrarán dispositivos con Windows BitLocker con confianza plataforma Module (TPM) integrado para evitar el acceso no autorizado a los datos locales cuando el dispositivo está en modo de suspensión, o desactivar. 
Supervisión |    Protección de amenaza avanzada de Windows Defender (Windows Defender ATP) es la solución para todos los dispositivos de escritorio de Microsoft administrado de supervisión de amenaza de seguridad. Windows Defender ATP permite a los clientes de empresa detectar, investigar y responder a las amenazas avanzadas en su red corporativa. Para obtener más información, vea [protección de amenaza avanzada de Windows Defender.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
Actualizaciones de software |  Microsoft se asegurará de que los dispositivos de escritorio de Microsoft administrado siempre se protegen con la actualización de seguridad más reciente para Windows y Office, mediante Windows Update para la empresa.
Recuperación |  Datos corporativos se almacenan en OneDrive para la empresa y pueden restaurarse fácilmente para dispositivos de escritorio administrado de Microsoft. Para obtener más información, vea [OneDrive para la empresa.](https://support.office.com/article/Restore-a-previous-version-of-a-file-in-OneDrive-159cad6d-d76e-4981-88ef-de6e96c93893?ui=en-US&rs=en-US&ad=US) 



## <a name="identity-security"></a>Seguridad de la identidad

Administración de identidades y acceso protege los activos corporativos y datos críticos para el negocio. Azure Active Directory (AD Azure) proporciona servicios de identidad en la nube y habilitar autenticación basada en la nube que garantiza que sólo los usuarios de confianza puede tener acceso a recursos corporativos desde dispositivos de escritorio administrado de Microsoft.

Servicio | Descripción
--- | ---
Proveedor de autenticación de remuneración de empresa |  Utilizado por Microsoft Azure ediciones de AD Premium proporcionan un servicio de alta disponibilidad hospedado en centros de datos distribuida globalmente. El servicio administra miles de millones de autenticaciones cada día a partir de más de 200 millones de usuarios activos y le proporciona un SLA 99,9%.
Autenticación biométrica |  Hola de Windows permite a los usuarios iniciar sesión utilizando su cara o un PIN, lo más difícil olvida o robar las contraseñas. Esto podría requerir trabajo adicional para configurar. Para obtener más información, vea [Windows Hola.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)
Autenticación en varias fases | Autenticación multifactor Azure impide el acceso no autorizado a local y la nube de aplicaciones al proporcionar un nivel adicional de la autenticación mediante un teléfono móvil, así como self-service de restablecimiento de contraseña. 
Permisos de usuario estándar |  Para proteger el sistema y que sea más seguro, el usuario se asignará permisos de usuario estándar. Esto se asigna como parte de la experiencia de fábrica de piloto automático de Windows.



## <a name="network-security"></a>Seguridad de red

Los clientes son responsables de la seguridad de red. 

Servicio | Descripción
--- | ---
VPN | Los clientes poseen su infraestructura de VPN, para asegurarse de que se pueden exponer los recursos corporativos limitados fuera de la intranet.<br><br>El requisito mínimo: escritorio de Microsoft Managed requiere una solución VPN 10 de Windows compatible y compatible. Si su organización necesita una solución de VPN, necesita admitir Windows 10 y ser empaquetada y que se pueden implementar a través de Intune. Para obtener más información, póngase en contacto con su compañía de software.<br><br>Recomendación:<br>-Microsoft recomienda una solución VPN moderno que podría implementarse fácilmente a través de Intune a los perfiles VPN de inserción. Esto proporciona una manera siempre en, sin problemas, confiable y segura para tener acceso a la red corporativa. Para obtener más información, vea Configuración de VPN en Intune.<br>-Los clientes VPN gruesas o los clientes heredados de VPN, no se recomiendan por Microsoft durante el uso de escritorio de Microsoft administrado tal y como puede influir en el entorno del usuario final.<br>-Microsoft recomienda que el tráfico web saliente irán directamente a Internet sin tener que pasar a través de la VPN para evitar los problemas de rendimiento.<br>-Ideal, Microsoft recomienda el uso de Azure Proxy de aplicación de Active Directory en lugar de una red privada virtual.


## <a name="information-security"></a>Seguridad de la información

Los clientes pueden configurar estos servicios opcionales para ayudar a proteger los activos corporativos de gran valor. 

Servicio | Descripción
--- | ---
Acceso condicional |    Permitir el acceso a recursos corporativos y servicios solo cuando es compatible con el dispositivo.
Recuperación de datos  | Información almacenada en carpetas clave en el dispositivo se hace una copia a OneDrive para Bbusiness. Escritorio administrado de Microsoft no es responsable de los datos que no se sincronizan con OneDrive para la empresa. 
Windows Information Protection |    Para las empresas que requieren altos niveles de seguridad de la información, se recomienda la [Protección de la información de Windows](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) y [protección de la información de Azure.](https://www.microsoft.com/cloud-platform/azure-information-protection). 


## <a name="privileged-account-access"></a>Cuenta con privilegios de acceso

En la actualidad, nos restringir el acceso a las credenciales de MSAdmin de atención al cliente y la aplicación a través de estos mecanismos:

- **Operadores** – completo-tiempo-empleados de Microsoft que se encuentra en los Estados Unidos que haya completado correctamente una comprobación periódica de fondo y de seguridad.
- Protege la **identidad del operador** – según los estándares establecidos por Microsoft. Para obtener más información, vea [administrar las identidades de usuario y acceso seguro en Microsoft](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft). 
- **El registro** se realiza en el entorno de operador y en el inquilino del cliente. Datos de registro y la información personal se conservan dentro de los entornos respectivos y no atraviesan entornos. 

