---
title: Pasos para que los Socios puedan registrar dispositivos
description: Cómo los partners pueden registrar dispositivos para que puedan ser administrados por escritorio administrado de Microsoft
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 7e40a5eb7144fef3d330e0e8fc3c711af15d4c49
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071448"
---
# <a name="steps-for-partners-to-register-devices"></a>Pasos para que los Socios puedan registrar dispositivos


En este tema se describen los pasos que deben seguir los partners para registrar dispositivos. El proceso para registrar dispositivos usted mismo se documenta en Registrar dispositivos en escritorio administrado de Microsoft usted [mismo.](register-devices-self.md)



## <a name="prepare-for-registration"></a>Prepararse para el registro 
Antes de completar el registro de un cliente, primero debes establecer una relación con ellos en el [Centro de partners.](https://partner.microsoft.com/dashboard) Consulte la [documentación de consentimiento](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#csp-authorization) para obtener más información sobre ese proceso. Cualquier partner de CSP puede agregar dispositivos en nombre de cualquier cliente, siempre y cuando el cliente consiente. También puedes obtener más información sobre las relaciones de partners y los permisos de Autopilot en la ayuda [del Centro de partners.](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#windows-autopilot)


> [!NOTE]
> Esta documentación es solo para partners y OEM. El proceso de registro propio se documenta en Registrar dispositivos en escritorio administrado de Microsoft usted [mismo.](register-devices-self.md)


## <a name="register-devices-by-using-partner-center"></a>Registrar dispositivos mediante el Centro de partners

Una vez establecida la relación con los clientes, puedes aprovechar el Centro de partners para agregar dispositivos a Autopilot para cualquiera de los clientes con los que tienes una relación siguiendo estos pasos:

1. Navegar al [Centro de partners](https://partner.microsoft.com/dashboard)
2. Selecciona **Clientes** en el menú del Centro de partners y, a continuación, selecciona el cliente cuyos dispositivos quieres administrar.
3. En la página de detalles del cliente, selecciona **Dispositivos.**
4. En Aplicar perfiles a **dispositivos,** **seleccione Agregar dispositivos.**
5. Escribe **Microsoft365Managed_Autopilot** nombre del grupo y,  a continuación, selecciona Examinar para cargar la lista del cliente (en formato de archivo .csv) en el Centro de partners.


> [!IMPORTANT]
> El nombre del grupo debe coincidir **exactamente Microsoft365Managed_Autopilot,** incluidas las mayúsculas y los caracteres especiales. Esto permitirá que los dispositivos recién registrados se asignen con el perfil de Microsoft Managed Desktop Autopilot.

>[!NOTE]
> Deberías haber recibido este archivo .csv con la compra del dispositivo. Si no recibió un archivo .csv, puede crear uno usted mismo siguiendo los pasos descritos en Agregar dispositivos a [Windows Autopilot.](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell) El Windows PowerShell script es diferente del que se usa para el portal de administración de [escritorio administrado de Microsoft.](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/register-devices-self?view=o365-worldwide#obtain-the-hardware-hash) Los partners deben [usar Get-WindowsAutoPilotInfo para](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) registrar dispositivos para dispositivos de Escritorio administrado de Microsoft en el Centro de partners.

Si recibe un mensaje de error al intentar cargar el archivo .csv, compruebe el formato del archivo. Asegúrate de que el orden de columna coincide con lo que se describe en Usar perfiles de Windows Autopilot en nuevos dispositivos para personalizar la experiencia de configuración de [un cliente.](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account) También puedes usar el archivo .csv de ejemplo proporcionado desde el vínculo junto a **Agregar dispositivos** para crear una lista de dispositivos. 

Para obtener más información sobre Autopilot en escenarios de partners, consulta [Agregar dispositivos a la cuenta de un cliente.](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account)


## <a name="register-devices-by-using-the-oem-api"></a>Registrar dispositivos mediante la API de OEM

Antes de completar el registro de un cliente, primero debe establecer una relación con él. Debes tener un vínculo único para proporcionar a tus respectivos clientes. Consulta [Cómo establecer una relación oem.](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#oem-authorization)

Una vez que hayas establecido la relación, puedes empezar a registrar dispositivos para los clientes mediante la etiqueta **de grupo Microsoft365Managed_Autopilot**.

> [!IMPORTANT]
> El nombre del grupo debe coincidir **exactamente Microsoft365Managed_Autopilot,** incluidas las mayúsculas y los caracteres especiales. Esto permitirá que los dispositivos recién registrados se asignen con el perfil de Microsoft Managed Desktop Autopilot.
