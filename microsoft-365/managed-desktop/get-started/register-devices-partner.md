---
title: Pasos para que los Socios puedan registrar dispositivos
description: Cómo los partners pueden registrar dispositivos para que puedan ser administrados por Microsoft Managed Desktop
ms.service: m365-md
author: tiaraquan
f1.keywords:
  - NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
---

# <a name="steps-for-partners-to-register-devices"></a>Pasos para que los Socios puedan registrar dispositivos

En este artículo se describen los pasos para que los partners registren dispositivos. El proceso para registrar dispositivos usted mismo se documenta en Registrar dispositivos [en Microsoft Managed Desktop usted mismo](register-devices-self.md).

## <a name="prepare-for-registration"></a>Prepararse para el registro

Antes de completar el registro de un cliente, primero debe establecer una relación con ellos en el [Centro de partners](https://partner.microsoft.com/dashboard). Para obtener más información sobre ese proceso, consulte la [documentación del consentimiento](/windows/deployment/windows-autopilot/registration-auth#csp-authorization). Cualquier partner csp puede agregar dispositivos en nombre de cualquier cliente, siempre que el cliente consiente. También puede obtener más información sobre las relaciones de partners y los permisos de Autopilot en la [ayuda del Centro de partners](/partner-center/customers_revoke_admin_privileges#windows-autopilot).

> [!NOTE]
> Esta documentación es solo para partners y OEM. El proceso de autoinscripción se documenta en Registrar dispositivos [en Microsoft Managed Desktop](register-devices-self.md).

## <a name="register-devices-using-the-partner-center"></a>Registrar dispositivos con el Centro de partners

Una vez establecida la relación con los clientes, puedes usar el Centro de partners para agregar dispositivos a Autopilot para cualquiera de los clientes.

**Para registrar dispositivos con el Centro de partners:**

1. Vaya al [Centro de partners](https://partner.microsoft.com/dashboard).
2. Selecciona **Clientes** en el menú Centro de partners y, a continuación, selecciona el cliente cuyos dispositivos quieres administrar.
3. En la página de detalles del cliente, seleccione **Dispositivos**.
4. En **Aplicar perfiles a dispositivos** , selecciona **Agregar dispositivos**.
5. Escribe la etiqueta de grupo adecuada para el perfil de dispositivo que has seleccionado (como se muestra en la tabla siguiente) y, a continuación, selecciona Examinar para cargar la lista del cliente (en formato de archivo .csv) al Centro de partners.

| [Perfil de dispositivo](../service-description/profiles.md) | Etiqueta de grupo |
| ----- | -----|
| Datos confidenciales | **Microsoft365ManagedSensitiveData\_** |
| Power user | **Microsoft365ManagedPowerUser\_** |
| Estándar | **Microsoft365ManagedStandard\_** |

> [!IMPORTANT]
> El nombre del grupo debe coincidir exactamente con los enumerados en la tabla, incluidas las mayúsculas y los caracteres especiales. Esto permitirá que los dispositivos recién registrados se asignen con el perfil de Microsoft Managed Desktop Autopilot.

>[!NOTE]
> Deberías haber recibido este archivo .csv con la compra del dispositivo. Si no recibió un archivo .csv, puede crear uno usted mismo siguiendo los pasos descritos en Agregar dispositivos a Windows [Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell). Requisitos: <ul><li>No se admiten columnas adicionales.</li> <li>No se admiten las comillas.</li> <li>Solo se pueden usar archivos de texto con formato ANSI (no Unicode).</li> <li>Los encabezados distinguen mayúsculas de minúsculas.</li></ul> Editar el archivo en Excel guardarlo como un archivo CSV no generará un archivo utilizable debido a estos requisitos. Asegúrese de conservar los ceros iniciales en los números de serie del dispositivo. Los partners deben [usar Get-WindowsAutoPilotInfo para](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) registrar dispositivos para dispositivos de Escritorio administrado de Microsoft en el Centro de partners.

Si recibe un mensaje de error al intentar cargar el archivo .csv, compruebe el formato del archivo. Asegúrese de que el orden de columna coincide con lo que se describe en Usar Windows perfiles de [Autopilot en dispositivos](/partner-center/autopilot#add-devices-to-a-customers-account) nuevos para personalizar la experiencia de un cliente de forma personalizada. También puedes usar el archivo de .csv de ejemplo proporcionado desde el vínculo junto a **Agregar dispositivos** para crear una lista de dispositivos.

Para obtener más información acerca de Autopilot en escenarios de partners, consulta [Agregar dispositivos a la cuenta de un cliente](/partner-center/autopilot#add-devices-to-a-customers-account).

## <a name="register-devices-by-using-the-oem-api"></a>Registrar dispositivos mediante la API oem

Antes de completar el registro de un cliente, primero debe establecer una relación con ellos. Debe tener un vínculo único para proporcionar a sus respectivos clientes. Consulte [How to establish OEM relationship](/windows/deployment/windows-autopilot/registration-auth#oem-authorization).

Una vez establecida la relación, puedes empezar a registrar dispositivos para clientes con la etiqueta de grupo adecuada para cada perfil de dispositivo que haya seleccionado:

| Perfil de dispositivo | Etiqueta de grupo |
| ----- | ----- |
| Datos confidenciales | **Microsoft365ManagedSensitiveData\_** |
| Power user | **Microsoft365ManagedPowerUser\_** |
| Estándar | **Microsoft365ManagedStandard\_** |

> [!IMPORTANT]
> Las etiquetas de grupo deben coincidir exactamente con las que aparecen en la tabla, incluidas las mayúsculas y los caracteres especiales. Esto permitirá que los dispositivos recién registrados se asignen con el perfil de Microsoft Managed Desktop Autopilot.
