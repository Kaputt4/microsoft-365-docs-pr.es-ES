---
title: Características de protección de Azure Information Protection implementación en inquilinos existentes
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: En este artículo se explican los cambios que se están implementando en las características de protección de Azure Information Protection
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: b4d57227e07695f334a70cd8ad5f28e34f8a3895
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67472774"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-tenants"></a>Características de protección de Azure Information Protection implementación en inquilinos existentes

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Para ayudar con el paso inicial para proteger la información, a partir de julio de 2018 todos los inquilinos válidos de Azure Information Protection tendrán las características de protección en Azure Information Protection activadas de forma predeterminada. Las características de protección de Azure Information Protection se conocían anteriormente en Office 365 como Rights Management o Azure RMS. Si su organización tiene un plan de servicio de Office E3 o un plan de servicio superior, ahora obtendrá una ventaja para proteger la información a través de Azure Information Protection cuando implementemos estas características.

## <a name="changes-beginning-july-1-2018"></a>Cambios a partir del 1 de julio de 2018

A partir del 1 de julio de 2018, Microsoft habilitará la funcionalidad de protección en Azure Information Protection para todas las organizaciones con uno de los siguientes planes de suscripción:

- Office 365 el cifrado de mensajes se ofrece como parte de Office 365 E3 y E5, Microsoft E3 y E5, Office 365 A1, A3 y A5, y Office 365 G3 y G5. No necesita licencias adicionales para recibir las nuevas funcionalidades de protección con tecnología de Azure Information Protection.

- También puede agregar Azure Information Protection Plan 1 a los siguientes planes para recibir las nuevas funcionalidades de cifrado de mensajes de Office 365: Exchange Online Plan 1, Exchange Online Plan 2, Office 365 F1, Microsoft 365 Empresa Básico, Microsoft 365 Empresa Estándar o Office 365 Enterprise E1.

- Cada usuario que se beneficie de Office 365 cifrado de mensajes debe tener licencia para ser cubierto por la característica.

- Para obtener la lista completa, consulte las [descripciones del servicio Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) para Office 365 cifrado de mensajes.

Los administradores de inquilinos pueden comprobar el estado de protección en el portal de administrador de Office 365.

:::image type="content" source="../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png" alt-text="La administración de derechos en Office 365 que se activa" lightbox="../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png":::

## <a name="why-are-we-making-this-change"></a>¿Por qué hacemos este cambio?

Office 365 Message Encryption aprovecha las funcionalidades de protección de Azure Information Protection. En el centro de las mejoras recientes en Office 365 cifrado de mensajes y en nuestras inversiones más amplias en la protección de la información en Microsoft 365, facilitamos a las organizaciones activar y usar nuestras capacidades de protección, ya que históricamente, las tecnologías de cifrado han sido difíciles de configurar. Al activar las características de protección en Azure Information Protection de forma predeterminada, puede empezar a proteger rápidamente los datos confidenciales.

## <a name="does-this-impact-me"></a>¿Esto me afecta?

Si su organización ha adquirido una licencia de Office 365 apta, este cambio afectará al inquilino.

> [!IMPORTANT]
> Si usa Active Directory Rights Management Services (AD RMS) en el entorno local, debe rechazar este cambio inmediatamente o migrar a Azure Information Protection antes de implementar este cambio en los próximos 30 días. Para obtener información sobre cómo optar por no participar, consulte "Uso AD RMS, ¿cómo puedo optar por no participar?". más adelante en este artículo. Si prefiere migrar, consulte [Migración de AD RMS a Azure Information Protection.](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>¿Puedo usar Azure Information Protection con Active Directory Rights Management Services (AD RMS)?

No. Este no es un escenario de implementación compatible. Sin realizar los pasos adicionales de exclusión, es posible que algunos equipos empiecen a usar automáticamente el servicio Azure Rights Management y también se conecten al clúster de AD RMS. Este escenario no se admite y tiene resultados poco confiables, por lo que es importante que se desocupe de este cambio en los próximos 30 días antes de implementar estas nuevas características. Para obtener información sobre cómo optar por no participar, consulte "Uso AD RMS, ¿cómo puedo optar por no participar?". más adelante en este artículo. Si prefiere migrar, consulte [Migración de AD RMS a Azure Information Protection.](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="how-do-i-know-if-im-using-ad-rms"></a>Cómo saber si estoy usando AD RMS?

Use estas instrucciones de [Preparación del entorno para Azure Rights Management cuando también tenga Active Directory Rights Management Services (AD RMS)](/azure/information-protection/deploy-use/prepare-environment-adrms) para comprobar si ha implementado AD RMS:

1. Aunque es opcional, la mayoría de las implementaciones de AD RMS publican el punto de conexión de servicio (SCP) en Active Directory para que los equipos de dominio puedan detectar el clúster de AD RMS.

   Use ADSI Edit para ver si tiene un SCP publicado en Active Directory: CN=Configuration [nombre del servidor], CN=Services, CN=RightsManagementServices, CN=SCP

2. Si no usa un SCP, los equipos Windows que se conectan a un clúster de AD RMS deben configurarse para la detección de servicios del lado cliente o el redireccionamiento de licencias mediante el Registro de Windows: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation`.

Para obtener más información sobre estas configuraciones del Registro, consulte [Habilitación de la detección de servicios del lado cliente mediante el registro de Windows](/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) y [Redirección del tráfico del servidor de licencias](/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic).

## <a name="i-use-ad-rms-how-do-i-opt-out"></a>Uso AD RMS, ¿cómo puedo optar por no participar?

Para no participar en el próximo cambio, complete estos pasos:

1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el cmdlet Set-IRMConfiguration con la sintaxis siguiente:

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>¿Qué puedo esperar después de que se haya realizado este cambio?

Una vez habilitado esto, siempre que no haya optado por no participar, puede empezar a usar la nueva versión de Office 365 Cifrado de mensajes que se anunció en [Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) y aprovecha las funcionalidades de cifrado y protección de Azure Information Protection.

:::image type="content" source="../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png" alt-text="Un mensaje protegido con OME en Outlook en la Web" lightbox="../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png":::

Para obtener más información sobre las nuevas mejoras, vea [Office 365 Cifrado de mensajes](../../compliance/ome.md).
