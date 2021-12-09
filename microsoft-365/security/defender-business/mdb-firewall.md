---
title: Firewall en Microsoft Defender para empresas
description: Obtenga información sobre Windows Defender firewall en Microsoft Defender para empresas, incluidas las opciones de configuración
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/08/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 1d85544d88004d3aa7654449eca4fb55db67e966
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2021
ms.locfileid: "61375459"
---
# <a name="firewall-in-microsoft-defender-for-business"></a>Firewall en Microsoft Defender para empresas

> [!IMPORTANT]
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. En este artículo se incluyen vínculos al contenido en línea que podrían describir algunas características que no se incluyen en Microsoft Defender para empresas (versión preliminar).

Microsoft Defender para empresas incluye funcionalidades de firewall [con Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security). La protección del firewall ayuda a proteger los dispositivos con reglas que determinan qué tráfico de red puede entrar o fluir desde dispositivos. 

Puede usar la protección de firewall para especificar si se permiten o bloquean las conexiones en dispositivos en distintas ubicaciones. Por ejemplo, la configuración del firewall puede permitir conexiones entrantes en dispositivos conectados a la red interna de la empresa, pero evitar esas conexiones cuando el dispositivo está en una red con dispositivos que no son de confianza.

**En este artículo se describe**:

- [Configuración predeterminada del firewall en Defender para empresas](#default-firewall-settings-in-defender-for-business)
- [Configuración del firewall que puede configurar en Defender para empresas](#firewall-settings-you-can-configure-in-defender-for-business)

## <a name="default-firewall-settings-in-defender-for-business"></a>Configuración predeterminada del firewall en Defender para empresas

Microsoft Defender para empresas incluye las directivas de firewall predeterminadas y la configuración para ayudar a proteger los dispositivos de su empresa desde el primer día. Tan pronto como los dispositivos de su empresa se incorpore a Microsoft Defender para empresas, la directiva de firewall predeterminada funciona de la siguiente manera:

- Las conexiones salientes desde dispositivos se permiten de forma predeterminada, independientemente de la ubicación.
- Cuando los dispositivos están conectados a la red de su empresa, todas las conexiones entrantes se permiten de forma predeterminada.
- Cuando los dispositivos están conectados a una red pública o a una red privada, todas las conexiones entrantes se bloquean de forma predeterminada.

En Microsoft Defender para empresas, puede definir excepciones para bloquear o permitir conexiones entrantes. Estas excepciones se definen mediante la creación de reglas personalizadas. Consulte [Administrar reglas personalizadas para directivas de firewall.](mdb-custom-rules-firewall.md)

## <a name="firewall-settings-you-can-configure-in-defender-for-business"></a>Configuración del firewall que puede configurar en Defender para empresas

Microsoft Defender para empresas incluye protección de firewall a través Windows Defender firewall. En la tabla siguiente se enumeran las opciones que se pueden configurar para la protección de firewall en Microsoft Defender para empresas. <br/><br/>

| Configuración | Descripción |
|--|--|
| **Red de dominio** | El perfil de red de dominio se aplica a la red de su empresa. La configuración de firewall de la red de dominio se aplica a las conexiones entrantes que se inician en otros dispositivos que están en la misma red. De forma predeterminada, las conexiones entrantes están establecidas **en Permitir todo**.  |
| **Red pública** | El perfil de red pública se aplica a una red que puede usar en una ubicación pública, como una cafetería o un aeropuerto. La configuración del firewall para redes públicas se aplica a las conexiones entrantes que se inician en otros dispositivos que están en la misma red. Dado que una red pública puede incluir dispositivos que no conoces o no confías, las conexiones entrantes se establecen en **Bloquear todo** de forma predeterminada.  |
| **Red privada** | El perfil de red privada se aplica a una red en una ubicación privada, como su hogar. La configuración del firewall para redes privadas se aplica a las conexiones entrantes que se inician en otros dispositivos que están en la misma red. En general, en una red privada, se supone que todos los demás dispositivos de la misma red son dispositivos de confianza. Sin embargo, de forma predeterminada, las conexiones entrantes se establecen **en Bloquear todo**. |
| **Reglas personalizadas** | [Las reglas personalizadas](mdb-custom-rules-firewall.md) permiten bloquear o permitir conexiones específicas. Por ejemplo, supongamos que desea bloquear todas las conexiones entrantes en dispositivos que están conectados a una red privada, excepto las conexiones a través de una aplicación específica en un dispositivo. En este caso, establecería la **red privada** para bloquear todas las conexiones entrantes y, a continuación, agregaría una regla personalizada para definir la excepción. <br/><br/>Puede usar reglas personalizadas para definir excepciones para archivos o aplicaciones específicos, una dirección IP o un rango de direcciones IP. <br/><br/>Según el tipo de regla personalizada que cree, estos son algunos valores de ejemplo que puede usar: <br/><br/>Ruta de acceso del archivo de aplicación: `C:\Windows\System\Notepad.exe or %WINDIR%\Notepad.exe` <br/><br/>IP: una dirección IPv4/IPv6 válida, como `192.168.1.0` o `192.168.1.0/24` <br/><br/>IP: un intervalo de direcciones IPv4/IPv6 válido, con formato like `192.168.1.0-192.168.1.9` (sin espacios incluidos) |

## <a name="next-steps"></a>Siguientes pasos

- [Administrar la configuración del firewall en Microsoft Defender para empresas](mdb-custom-rules-firewall.md)

- [Obtenga más información sobre Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)

- [Ver y administrar incidentes en Microsoft Defender para empresas](mdb-view-manage-incidents.md)

- [Responder y mitigar amenazas en Microsoft Defender para empresas](mdb-respond-mitigate-threats.md)

- [Revisar acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)