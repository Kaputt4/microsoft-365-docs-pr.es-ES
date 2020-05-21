---
title: Pasos para que los Socios puedan registrar dispositivos
description: Cómo pueden los socios registrar los dispositivos para que puedan ser administrados por el escritorio administrado por Microsoft
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: f1b1a8f03b7a11a0467826281bc2b789140dbcee
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327061"
---
# <a name="steps-for-partners-to-register-devices"></a>Pasos para que los Socios puedan registrar dispositivos


En este tema se describen los pasos que deben seguir los socios para registrar los dispositivos. El proceso para registrar los dispositivos usted mismo está documentado en [registrar los dispositivos en el escritorio administrado por Microsoft](register-devices-self.md).



## <a name="prepare-for-registration"></a>Preparar el registro 
Antes de completar el registro de un cliente, primero debe establecer una relación con ellos en el [centro de Partners](https://partner.microsoft.com/dashboard). Consulte la [documentación de consentimiento](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#csp-authorization) para obtener más información sobre el proceso. Cualquier socio de CSP puede agregar dispositivos en nombre de cualquier cliente, siempre que el cliente lo conenvíe. También puede obtener más información acerca de las relaciones de los socios y los permisos de AutoPilot en la [ayuda del centro de asociados](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#windows-autopilot).


> [!NOTE]
> Esta documentación es solo para partners y OEM. El proceso de registro automático está documentado en los [dispositivos de registro del escritorio administrado por Microsoft](register-devices-self.md).


## <a name="register-devices-by-using-partner-center"></a>Registrar dispositivos mediante el centro de Partners

Una vez que haya establecido la relación con sus clientes, puede aprovechar el centro de asociados para agregar dispositivos a un piloto automático para cualquiera de los clientes con los que tiene una relación, siguiendo estos pasos:

1. Ir al [centro de asociados](https://partner.microsoft.com/dashboard)
2. Seleccione **clientes** en el menú Centro para socios y, a continuación, seleccione el cliente cuyos dispositivos desee administrar.
3. En la página de detalles del cliente, seleccione **dispositivos**.
4. En **aplicar perfiles** a dispositivos, seleccione **Agregar dispositivos**.
5. Escriba **Microsoft365Managed_Autopilot** para el nombre de grupo y, a continuación, seleccione **examinar** para cargar la lista de clientes (en formato de archivo. csv) en el centro de asociados.


> [!IMPORTANT]
> El nombre del grupo debe coincidir con **Microsoft365Managed_Autopilot** exactamente, incluido el carácter de mayúsculas y caracteres especiales. Esto permitirá que los dispositivos recién registrados se asignen con el perfil de Microsoft Managed Desktop AutoPilot.

>[!NOTE]
> Debe haber recibido este archivo. csv con la compra de su dispositivo. Si no recibió un archivo. csv, puede crear uno solo si sigue los pasos que se indican en [Agregar dispositivos a Windows AutoPilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell). El script de Windows PowerShell es diferente del que se usa para el [portal de administración de escritorio administrado de Microsoft](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/register-devices-self?view=o365-worldwide#obtain-the-hardware-hash). Los partners deben usar [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) para registrar dispositivos para dispositivos de escritorio administrados por Microsoft en el centro de asociados.

Si recibe un mensaje de error al intentar cargar el archivo. csv, compruebe el formato del archivo. Puede usar solo el hash de hardware, el nombre de OEM, el número de serie y el modelo (en ese orden de columnas) o el identificador de producto de Windows. También puede usar el archivo. csv de ejemplo que se proporciona en el vínculo junto a **Agregar dispositivos** para crear una lista de dispositivos. 

Para obtener más información acerca de AutoPilot en escenarios de asociados, consulte [Agregar dispositivos a una cuenta de cliente](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account).


## <a name="register-devices-by-using-the-oem-api"></a>Registrar dispositivos con la API de OEM

Antes de completar el registro de un cliente, primero debe establecer una relación con ellos. Debe tener un vínculo único para proporcionar a sus clientes respectivos. Vea [cómo establecer una relación de OEM](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#oem-authorization).

Una vez que haya establecido la relación, puede empezar a registrar dispositivos para clientes que usen la etiqueta de grupo **Microsoft365Managed_Autopilot**.

> [!IMPORTANT]
> El nombre del grupo debe coincidir con **Microsoft365Managed_Autopilot** exactamente, incluido el carácter de mayúsculas y caracteres especiales. Esto permitirá que los dispositivos recién registrados se asignen con el perfil de Microsoft Managed Desktop AutoPilot.
