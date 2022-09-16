---
title: Actualización desde Lync Server 2013
ms.author: serdars
author: serdarsoysal
manager: serdars
ms.date: 11/10/2021
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.collection:
- Ent_O365
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: Busque información y recursos para actualizar desde Lync Server 2013. El soporte técnico finaliza el 11 de abril de 2023.
ms.openlocfilehash: 72b161c608ba9ac9430957b174b864943e691b76
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2022
ms.locfileid: "67740771"
---
# <a name="upgrading-from-lync-server-2013"></a>Actualización desde Lync Server 2013

Microsoft Lync Server 2013 finalizará el soporte técnico el **11 de abril de 2023**. En este artículo se proporcionan recursos que le ayudarán a actualizar la implementación existente de Lync Server a Microsoft Teams o Skype Empresarial local.

## <a name="what-is-end-of-support"></a>¿Qué es *el fin del soporte técnico*?

La mayoría de los productos de Microsoft tienen un ciclo de vida de soporte técnico, durante el cual obtienen nuevas características, correcciones de errores, correcciones de seguridad, etc. Después de la fecha de finalización del soporte técnico, el producto no deja de funcionar, pero Microsoft ya no proporciona:

- Soporte técnico para los problemas que pueden producirse.

- Correcciones de errores para problemas que pueden afectar a la estabilidad y facilidad de uso del servidor.

- Correcciones de seguridad para las vulnerabilidades que pueden hacer que el servidor sea vulnerable a infracciones de seguridad.

- Actualizaciones de zona horaria.

Esto significa que no habrá actualizaciones, revisiones ni correcciones adicionales para el producto (incluidas revisiones o correcciones de seguridad). Soporte técnico de Microsoft habrá cambiado por completo sus esfuerzos de soporte técnico a versiones más recientes.

## <a name="plan-ahead"></a>Planear con antelación

Compruebe las fechas en las que finaliza el soporte técnico en el [sitio ciclo de vida del producto](/lifecycle/products/microsoft-lync-server-2013). Planee las actualizaciones o migraciones teniendo en cuenta estas fechas. Recuerde que el producto *no dejará de funcionar* en la fecha indicada. Pero como la instalación ya no se aplicará una revisión después de esa fecha, querrá planear una transición fluida a la siguiente versión del producto. En la tabla siguiente se enumeran las opciones disponibles.

|Producto de fin de soporte técnico|Compatible|Recomendado|
|---|---|---|
|Lync Server 2013|Actualización a Skype Empresarial Server 2015 o 2019|Actualizar a Microsoft Teams

## <a name="whats-next"></a>¿Cuál es el siguiente paso?

Se recomienda actualizar a Microsoft Teams. Microsoft Teams amplía las funcionalidades de Lync Server, reuniendo chat, reuniones, llamadas, colaboración, integración de aplicaciones y almacenamiento de archivos en una sola interfaz. Teams ayuda a simplificar la forma en que los usuarios realizan las cosas, lo que mejora la satisfacción del usuario y acelera los resultados empresariales. Continuamente ampliamos las capacidades de Teams para que puedan comunicarse y colaborar de nuevas maneras, romper las barreras organizativas y geográficas, e impulsar la eficiencia en los procedimientos y la toma de decisiones.

Si no puede actualizar a Microsoft Teams, puede actualizar a Skype Empresarial Server 2015 o 2019. Una consideración de planeación clave que debe tenerse en cuenta es que ambos productos llegarán al final del soporte técnico el 14 de octubre de 2025. Para obtener más información, consulte las siguientes páginas de ciclo de vida de soporte técnico:

- [información del ciclo de vida de soporte técnico de Skype Empresarial Server 2015](/lifecycle/products/skype-for-business-server-2015)
- [información del ciclo de vida de soporte técnico de Skype Empresarial Server 2019](/lifecycle/products/skype-for-business-server-2019)

### <a name="upgrade-to-microsoft-teams"></a>Actualizar a Microsoft Teams

Tenemos instrucciones detalladas sobre cómo actualizar a Microsoft Teams desde la implementación local. En primer lugar, vamos a cubrir algunos requisitos técnicos clave. Tendrá que establecer la conectividad híbrida, lo que le permitirá mover los usuarios a Teams. [Planear la conectividad híbrida](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) proporciona información general sobre la configuración de un entorno híbrido. Aunque el artículo se centra en Skype Empresarial, todos los conceptos también se aplican a Lync Server 2013. Consulte la sección [de requisitos de versión del servidor](/SkypeForBusiness/hybrid/plan-hybrid-connectivity#server-version-requirements) para obtener detalles específicos de Lync Server 2013.

También debe asegurarse de que la implementación de Lync Server 2013 está totalmente actualizada. Publicamos una [lista de todas las actualizaciones más recientes para Lync Server 2013](https://support.microsoft.com/topic/updates-for-lync-server-2013-a2a042ac-79f0-2665-7453-0a541fb25164) Sin embargo, la siguiente actualización es un requisito previo para una actualización a Microsoft Teams:

- [Actualización acumulativa de septiembre de 2021 5.0.8308.1149 para Lync Server 2013, Componentes principales](https://support.microsoft.com/topic/september-2021-cumulative-update-5-0-8308-1149-for-lync-server-2013-core-components-6755903a-fc9a-44d2-b835-2a6d01f14043): esta actualización reemplaza la autenticación de Live ID por el protocolo de autenticación de OAuth para el `Move-CSUser` cmdlet, que se usa para mover usuarios locales a Microsoft Teams.

Aunque la experiencia del usuario en Microsoft Teams es mucho más rica y superior a Lync, también es dramáticamente diferente. Por lo tanto, también tendrá que preparar su organización y los usuarios para garantizar una adopción rápida de Microsoft Teams. Tenemos una gran cantidad de información disponible sobre cómo preparar su organización, planear la actualización a Teams y garantizar un lanzamiento correcto.

**Le recomendamos que comience en nuestro [portal de actualización de Teams](/MicrosoftTeams/upgrade-skype-teams)** , donde puede encontrar información técnica, recursos de entrenamiento, vínculos a sesiones de Ignite, recursos de ayuda disponibles, casos prácticos y mucho más.

:::image type="content" source="../media/teams-upgrade-portal.png" alt-text="Captura de pantalla del portal de actualización de Teams":::

### <a name="upgrade-to-skype-for-business-server"></a>Actualizar a Skype Empresarial Server

La ruta de acceso a Skype Empresarial Server va a ser diferente en función de la versión a la que elija actualizar. Skype Empresarial Server 2015 admite una actualización local de Lync Server 2013. Por otro lado, para actualizar a Skype Empresarial Server 2019, primero deberá introducir Skype Empresarial Server 2019 en la instalación de Lync Server 2013 mediante la adición de uno o más servidores nuevos y, a continuación, transferir las operaciones a los nuevos servidores 2019 que haya agregado.

Un punto importante a tener en cuenta es que la fase de soporte técnico actual para cada producto: Skype Empresarial 2019 está en soporte estándar y Skype Empresarial 2015 está actualmente en soporte extendido.  Por lo tanto, se recomienda actualizar a Skype Empresarial Server 2019. Para obtener más información sobre la diferencia entre el soporte estándar y el soporte extendido, consulte [Directiva de ciclo de vida fijo](/lifecycle/policies/fixed).

Consulte los siguientes recursos para obtener información detallada sobre cada escenario de actualización.

- [Actualización a Skype Empresarial Server 2019](/skypeforbusiness/migration/migration-to-skype-for-business-server-2019)
- [Actualización a Skype Empresarial Server 2015](/skypeforbusiness/deploy/upgrade-to-skype-for-business-server)
