---
title: Cómo configurar directivas y permisos de cuarentena
description: Los pasos para configurar directivas y permisos de cuarentena en distintos grupos, como AdminOnlyPolicy, acceso limitado, acceso completo y proporcionar a los administradores de seguridad y a los usuarios una manera sencilla de administrar carpetas falsas positivas.
search.product: ''
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
ms.technology: mdo
search.appverid: met150
ms.openlocfilehash: 3fe7656e4d930b4cf251e3536ae2a53daa6745d2
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67693485"
---
# <a name="how-to-configure-quarantine-permissions-and-policies"></a>Cómo configurar directivas y permisos de cuarentena

Proporcionar a los administradores de seguridad y a los usuarios una manera muy sencilla de administrar carpetas falsas positivas es vital dado el aumento de la demanda de una posición de seguridad más agresiva con la evolución del trabajo híbrido. Si se aplica un enfoque prescriptivo, los administradores y los usuarios pueden lograrlo con las instrucciones siguientes.

> [!TIP]
> Para ver un breve vídeo dirigido a los administradores que intentan establecer directivas y permisos de cuarentena, [consulte este vínculo](https://www.youtube.com/watch?v=vnar4HowfpY). Si es un usuario final, opte por esta [información general de 1 minuto](https://www.youtube.com/watch?v=s-vozLO43rI) del proceso.

## <a name="what-you-will-need"></a>Lo que necesitará
- Permisos suficientes (rol administrador de seguridad)
- 5 minutos para realizar los pasos siguientes.

## <a name="creating-custom-quarantine-policies-with-request-release-flow"></a>Creación de directivas de cuarentena personalizadas con el flujo de versión de solicitud

Nuestras directivas personalizadas ofrecen a los administradores la capacidad de decidir qué elementos pueden evaluar sus usuarios en la carpeta ***Falso positivo** _ con una capacidad ampliada de permitir que el usuario solicite el _release* de esos elementos de la carpeta.

1. Decida qué categoría de veredictos (bulk, spam, phish, high confidence phish o malware) de los elementos que desea que el usuario triage y no triage.
1. Para las categorías que no desea que los usuarios triagen, asigne los elementos a **AdminOnlyPolicy**. En cuanto a la categoría que desea que los usuarios triagen con acceso limitado, puede *crear una directiva personalizada* con un acceso de versión de solicitud y asignar usuarios a esa categoría.
1. Se **recomienda encarecidamente** que el malware y los elementos de phish de alta confianza se asignen a **AdminOnlyPolicy**, a los elementos de phish de confianza normal se les asigne *acceso limitado con la versión de la solicitud*, mientras que el correo no deseado y masivo se pueden dejar como acceso completo para los usuarios.

> [!IMPORTANT]
> Para obtener más información sobre cómo se pueden crear directivas personalizadas pormenorizadas, consulte [Directivas de cuarentena: Office 365 | Microsoft Docs](../../office-365-security/quarantine-policies.md).

## <a name="assigning-quarantine-policies-and-enabling-notification-with-organization-branding"></a>Asignación de directivas de cuarentena y habilitación de la notificación con personalización de marca de la organización

Una vez que se ha decidido que las categorías de elementos que los usuarios pueden evaluar o no evaluar, y crear las directivas de cuarentena correspondientes, los administradores deben asignar estas directivas a los usuarios respectivos y habilitar las notificaciones.

1. Identifique los usuarios, grupos o dominios que desea incluir en la categoría *de acceso completo* frente a la categoría *de acceso limitado*, frente a la categoría *solo Administración*.
1. Inicie sesión en el [portal de seguridad de Microsoft](https://security.microsoft.com).
1. Seleccione **Email & directivas de colaboración** > **& reglas**.
1. Seleccione **Directivas de amenazas**.
1. Seleccione cada una de las siguientes opciones: **Directivas contra correo no deseado**, **Directiva contra suplantación de identidad (Anti-phishing**) y **Directiva antimalware**.
1. Seleccione **Crear directiva** y elija **Entrante**.
1. Agregue el nombre de directiva, los usuarios, los grupos o los dominios a los que aplicar la directiva y **Siguiente**.
1. En la pestaña **Acciones** , seleccione **Mensaje de cuarentena** para las categorías. Observará un panel adicional para *seleccionar la directiva de cuarentena*, use esa lista desplegable para seleccionar la directiva de cuarentena que creó anteriormente.
1. Vaya a la sección **Revisar** y haga clic en el botón **Confirmar** para crear la nueva directiva.
1. Repita estos mismos pasos para las demás directivas: directiva **anti phishing**, directiva **antimalware** y **directiva de datos adjuntos seguros**.

> [!TIP]
> Para obtener información más detallada sobre lo que ha aprendido hasta ahora, consulte [Configuración de directivas de filtro de correo no deseado: Office 365 | ](../../office-365-security/configure-your-spam-filter-policies.md)|  Microsoft Docs [Configurar directivas contra suplantación de identidad en EOP: Office 365 | ](../../office-365-security/configure-anti-phishing-policies-eop.md) |  Microsoft Docs [Configurar directivas de antimalware: Office 365 | ](../../office-365-security/configure-anti-malware-policies.md)|  Microsoft Docs [Configuración de directivas de datos adjuntos seguros en Microsoft Defender para Office 365: Office 365 | Microsoft Docs](../../office-365-security/set-up-safe-attachments-policies.md)

## <a name="next-steps"></a>Pasos siguientes

- Use **la directiva global** disponible en la directiva de cuarentena para habilitar el logotipo, el nombre para mostrar y la declinación de responsabilidades de la organización.
- Establezca también la **frecuencia de usuario en 1 día** para la notificación de cuarentena.

## <a name="more-information"></a>Más información

Obtenga más información sobre la personalización de marca de la organización y la configuración de notificaciones aquí [Directivas de cuarentena: Office 365 | Microsoft Docs](../../office-365-security/quarantine-policies.md)
