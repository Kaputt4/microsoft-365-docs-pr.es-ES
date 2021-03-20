---
title: Pasos para que los Socios puedan registrar dispositivos
description: Cómo los partners pueden registrar dispositivos para que puedan ser administrados por Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: be314b20573cecfdb020caf778e51a684a9b6df8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909075"
---
# <a name="steps-for-partners-to-register-devices"></a>Pasos para que los Socios puedan registrar dispositivos


En este tema se describen los pasos que deben seguir los partners para registrar dispositivos. El proceso para registrar dispositivos usted mismo se documenta en Registrar dispositivos [en Microsoft Managed Desktop usted mismo.](register-devices-self.md)



## <a name="prepare-for-registration"></a>Prepararse para el registro 
Antes de completar el registro de un cliente, primero debe establecer una relación con ellos en el [Centro de partners](https://partner.microsoft.com/dashboard). Consulta la [documentación de consentimiento](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) para obtener más información sobre ese proceso. Cualquier partner csp puede agregar dispositivos en nombre de cualquier cliente, siempre que el cliente consiente. También puede obtener más información sobre las relaciones de partners y los permisos de Autopilot en la [ayuda del Centro de partners.](/partner-center/customers_revoke_admin_privileges#windows-autopilot)


> [!NOTE]
> Esta documentación es solo para partners y OEM. El proceso de autoinscripción se documenta en Registrar dispositivos [en Microsoft Managed Desktop usted mismo.](register-devices-self.md)


## <a name="register-devices-by-using-partner-center"></a>Registrar dispositivos mediante el Centro de partners

Una vez establecida la relación con los clientes, puede aprovechar el Centro de partners para agregar dispositivos a Autopilot para cualquiera de los clientes con los que tenga una relación siguiendo estos pasos:

1. Vaya al [Centro de partners](https://partner.microsoft.com/dashboard)
2. Selecciona **Clientes** en el menú Centro de partners y, a continuación, selecciona el cliente cuyos dispositivos quieres administrar.
3. En la página de detalles del cliente, seleccione **Dispositivos**.
4. En Aplicar perfiles a **dispositivos,** seleccione **Agregar dispositivos**.
5. Escriba **Microsoft365Managed_Autopilot** nombre del grupo y,  a continuación, seleccione Examinar para cargar la lista del cliente (en formato de archivo .csv) al Centro de partners.


> [!IMPORTANT]
> El nombre del grupo debe coincidir **Microsoft365Managed_Autopilot** exactamente, incluida la mayúscula y los caracteres especiales. Esto permitirá que los dispositivos recién registrados se asignen con el perfil de Microsoft Managed Desktop Autopilot.

>[!NOTE]
> Deberías haber recibido este archivo .csv con la compra del dispositivo. Si no has recibido un archivo .csv, puedes crear uno tú mismo siguiendo los pasos descritos en Agregar dispositivos a [Windows Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell). El Windows PowerShell script es diferente del que se usa para el portal de administración de [Escritorio administrado de Microsoft](./register-devices-self.md?view=o365-worldwide#obtain-the-hardware-hash). Los partners deben [usar Get-WindowsAutoPilotInfo para](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) registrar dispositivos para dispositivos de Escritorio administrado de Microsoft en el Centro de partners.

Si recibe un mensaje de error al intentar cargar el archivo .csv, compruebe el formato del archivo. Asegúrate de que el orden de columna coincida con lo que se describe en Usar perfiles de [Windows Autopilot](/partner-center/autopilot#add-devices-to-a-customers-account)en nuevos dispositivos para personalizar la experiencia de un cliente de forma personalizada. También puedes usar el archivo .csv de ejemplo proporcionado desde el vínculo junto a **Agregar dispositivos** para crear una lista de dispositivos. 

Para obtener más información acerca de Autopilot en escenarios de partners, vea [Agregar dispositivos a la cuenta de un cliente.](/partner-center/autopilot#add-devices-to-a-customers-account)


## <a name="register-devices-by-using-the-oem-api"></a>Registrar dispositivos mediante la API oem

Antes de completar el registro de un cliente, primero debe establecer una relación con ellos. Debe tener un vínculo único para proporcionar a sus respectivos clientes. Consulte [How to establish OEM relationship](/windows/deployment/windows-autopilot/registration-auth#oem-authorization).

Una vez establecida la relación, puede empezar a registrar dispositivos para clientes mediante la etiqueta **de grupo Microsoft365Managed_Autopilot**.

> [!IMPORTANT]
> El nombre del grupo debe coincidir **Microsoft365Managed_Autopilot** exactamente, incluida la mayúscula y los caracteres especiales. Esto permitirá que los dispositivos recién registrados se asignen con el perfil de Microsoft Managed Desktop Autopilot.