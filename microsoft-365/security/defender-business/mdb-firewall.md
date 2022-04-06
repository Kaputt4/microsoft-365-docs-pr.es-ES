---
title: Firewall en Microsoft Defender para Empresas
description: Obtenga información sobre Windows Defender Firewall en Microsoft Defender para Empresas, incluida la configuración
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 03/15/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: fb506a1d2cc28329f9d6ef9975a10b0661379bb9
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664620"
---
# <a name="firewall-in-microsoft-defender-for-business"></a>Firewall en Microsoft Defender para Empresas

> [!IMPORTANT]
> Microsoft Defender para Empresas se está implementando para [Microsoft 365 Empresa Premium](../../business-premium/index.md) clientes, a partir del 1 de marzo de 2022. Defender for Business como una suscripción independiente está en versión preliminar y se implementará gradualmente para los clientes y asociados de TI que [se registren aquí](https://aka.ms/mdb-preview) para solicitarla. La versión preliminar incluye un [conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios) y vamos a agregar funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a los productos o servicios preliminares que se pueden modificar sustancialmente antes de que se publiquen comercialmente. Microsoft no ofrece ninguna garantía, expresa o implícita, de la información que se proporciona aquí. 

Microsoft Defender para Empresas incluye funcionalidades de firewall con [Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security). La protección del firewall ayuda a proteger los dispositivos con reglas que determinan qué tráfico de red puede entrar o fluir desde los dispositivos. 

Puede usar la protección de firewall para especificar si desea permitir o bloquear conexiones en dispositivos en varias ubicaciones. Por ejemplo, la configuración del firewall puede permitir conexiones entrantes en dispositivos que están conectados a la red interna de la empresa, pero evitar esas conexiones cuando el dispositivo está en una red con dispositivos que no son de confianza.

**En este artículo se describe lo siguiente**:

- [Configuración predeterminada del firewall en Defender para empresas](#default-firewall-settings-in-defender-for-business)

- [Configuración de firewall que puede configurar en Defender para empresas](#firewall-settings-you-can-configure-in-defender-for-business)

>
> **¿Tiene un minuto?**
> Realice nuestra <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">breve encuesta sobre Microsoft Defender para Empresas</a>. Nos encantaría conocer su opinión.
>

## <a name="default-firewall-settings-in-defender-for-business"></a>Configuración predeterminada del firewall en Defender para empresas

Microsoft Defender para Empresas incluye directivas de firewall y configuración predeterminadas para ayudar a proteger los dispositivos de la empresa desde el primer día. En cuanto los dispositivos de su empresa se incorpore a Microsoft Defender para Empresas, la directiva de firewall predeterminada funciona de la siguiente manera:

- Las conexiones salientes desde dispositivos se permiten de forma predeterminada, independientemente de la ubicación.
- Cuando los dispositivos están conectados a la red de la empresa, todas las conexiones entrantes se bloquean de forma predeterminada.
- Cuando los dispositivos están conectados a una red pública o a una red privada, todas las conexiones entrantes se bloquean de forma predeterminada.

En Microsoft Defender para Empresas, puede definir excepciones para bloquear o permitir conexiones entrantes. Estas excepciones se definen mediante la creación de reglas personalizadas. Consulte [Administración de reglas personalizadas para directivas de firewall](mdb-custom-rules-firewall.md).

## <a name="firewall-settings-you-can-configure-in-defender-for-business"></a>Configuración de firewall que puede configurar en Defender para empresas

Microsoft Defender para Empresas incluye protección contra firewalls a través de Windows Defender Firewall. En la tabla siguiente se enumeran los valores que se pueden configurar para la protección del firewall en Microsoft Defender para Empresas. <br/><br/>

| Valor | Descripción |
|--|--|
| **Red de dominio** | El perfil de red de dominio se aplica a la red de su empresa. La configuración de firewall de la red de dominio se aplica a las conexiones entrantes que se inician en otros dispositivos que se encuentran en la misma red. De forma predeterminada, las conexiones entrantes se establecen en **Bloquear todo**.  |
| **Red pública** | El perfil de red pública se aplica a una red que se puede usar en una ubicación pública, como una cafetería o un aeropuerto. La configuración de firewall de las redes públicas se aplica a las conexiones entrantes que se inician en otros dispositivos que se encuentran en la misma red. Dado que una red pública puede incluir dispositivos que no conoce o en los que no confía, las conexiones entrantes se establecen en **Bloquear todo** de forma predeterminada.  |
| **Red privada** | El perfil de red privada se aplica a una red en una ubicación privada, como su hogar. La configuración de firewall de las redes privadas se aplica a las conexiones entrantes que se inician en otros dispositivos que se encuentran en la misma red. En general, en una red privada, se supone que todos los demás dispositivos de la misma red son dispositivos de confianza. Sin embargo, de forma predeterminada, las conexiones entrantes se establecen en **Bloquear todo**. |
| **Reglas personalizadas** | [Las reglas personalizadas](mdb-custom-rules-firewall.md) permiten bloquear o permitir conexiones específicas. Por ejemplo, supongamos que desea bloquear todas las conexiones entrantes en dispositivos conectados a una red privada, excepto las conexiones a través de una aplicación específica en un dispositivo. En este caso, establecería **Red privada** para bloquear todas las conexiones entrantes y, a continuación, agregaría una regla personalizada para definir la excepción. <br/><br/>Puede usar reglas personalizadas para definir excepciones para archivos o aplicaciones específicos, una dirección de protocolo de Internet (IP) o un intervalo de direcciones IP. <br/><br/>En función del tipo de regla personalizada que esté creando, estos son algunos valores de ejemplo que puede usar: <br/><br/>Ruta de acceso del archivo de aplicación: `C:\Windows\System\Notepad.exe or %WINDIR%\Notepad.exe` <br/><br/>IP: una dirección IPv4/IPv6 válida, como `192.168.11.0` o `192.168.1.0/24` <br/><br/>IP: intervalo de direcciones IPv4/IPv6 válido, con formato similar `192.168.1.0-192.168.1.9` (sin espacios incluidos) |

## <a name="next-steps"></a>Siguientes pasos

- [Administración de la configuración del firewall en Microsoft Defender para Empresas](mdb-custom-rules-firewall.md)

- [Más información sobre Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)

- [Visualización y administración de incidentes en Microsoft Defender para Empresas](mdb-view-manage-incidents.md)

- [Respuesta y mitigación de amenazas en Microsoft Defender para Empresas](mdb-respond-mitigate-threats.md)

- [Revisión de las acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)