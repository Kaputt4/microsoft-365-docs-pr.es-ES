---
title: Actualización desde Lync Server 2013
ms.author: serdars
author: serdarsoysal
manager: serdars
ms.date: 11/10/2021
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
ms.collection:
- Ent_O365
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: Busque información y recursos para actualizar desde Lync Server 2013. El soporte técnico finaliza el 11 de abril de 2023.
ms.openlocfilehash: a770ce6acab4320bc84e920b1c527e9c63e72bbb
ms.sourcegitcommit: 16e3a6e6df253de1153e46d058941cd9a2bbf2b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2021
ms.locfileid: "60889904"
---
# <a name="upgrading-from-lync-server-2013"></a>Actualización desde Lync Server 2013

Microsoft Lync Server 2013 llegará al final de la compatibilidad el **11 de abril de 2023**. En este artículo se proporcionan recursos que le ayudarán a actualizar la implementación existente de Lync Server Microsoft Teams o Skype Empresarial local.

## <a name="what-is-end-of-support"></a>¿Qué es *el fin de la compatibilidad?*

La mayoría de los productos de Microsoft tienen un ciclo de vida de soporte técnico, durante el cual obtienen nuevas características, correcciones de errores, correcciones de seguridad, y así sucesivamente. Después de la fecha de finalización de la compatibilidad, el producto no deja de funcionar, pero Microsoft ya no proporciona:

- Soporte técnico para los problemas que pueden producirse.

- Correcciones de errores para problemas que pueden afectar a la estabilidad y facilidad de uso del servidor.

- Correcciones de seguridad para vulnerabilidades que pueden hacer que el servidor sea vulnerable a infracciones de seguridad.

- Actualizaciones de zona horaria.

Esto significa que no habrá más actualizaciones, revisiones o correcciones para el producto (incluidas revisiones o correcciones de seguridad). El soporte técnico de Microsoft habrá cambiado completamente sus esfuerzos de soporte técnico a versiones más recientes.

## <a name="plan-ahead"></a>Planear con antelación

Compruebe las fechas en que finaliza la compatibilidad en el [sitio ciclo de vida del producto.](/lifecycle/products/lync-server-2013) Planee las actualizaciones o las migraciones con estas fechas en mente. Recuerde que el producto *no dejará de funcionar* en la fecha indicada. Pero como la instalación ya no se parchea después de esa fecha, querrá planear una transición sin problemas a la siguiente versión del producto. En la tabla siguiente se enumeran las opciones disponibles.

|Fin del producto de soporte técnico|Compatible|Recomendado|
|---|---|---|
|Lync Server 2013|Actualizar a Skype Empresarial Server 2015 o 2019|Actualizar a Microsoft Teams

## <a name="whats-next"></a>¿Cuál es el siguiente paso?

Se recomienda actualizar a Microsoft Teams. Microsoft Teams las capacidades de Lync Server, que reúnen chat, reuniones, llamadas, colaboración, integración de aplicaciones y almacenamiento de archivos en una sola interfaz. Teams ayuda a simplificar la forma en que los usuarios hacen las cosas, mejorando la satisfacción de los usuarios y acelerando los resultados empresariales. Continuamente ampliamos las capacidades de Teams para que puedan comunicarse y colaborar de nuevas maneras, romper las barreras organizativas y geográficas, e impulsar la eficiencia en los procedimientos y la toma de decisiones.

Si no puede actualizar a Microsoft Teams, puede actualizar a Skype Empresarial Server 2015 o 2019. Una consideración de planeación clave para saber es que ambos productos llegarán a su fin el 14 de octubre de 2025. Para obtener más información, consulte las siguientes páginas del ciclo de vida de soporte técnico:

- [Skype Empresarial Server de ciclo de vida de soporte técnico de 2015](/lifecycle/products/skype-for-business-server-2015)
- [Skype Empresarial Server de ciclo de vida de soporte técnico de 2019](/lifecycle/products/skype-for-business-server-2019)

### <a name="upgrade-to-microsoft-teams"></a>Actualizar a Microsoft Teams

Tenemos instrucciones detalladas sobre cómo actualizar a Microsoft Teams desde la implementación local. En primer lugar, vamos a cubrir algunos requisitos técnicos clave. Deberá establecer una conectividad híbrida que le permita mover a los usuarios a Teams. [Plan hybrid connectivity](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) gives an overview of setting up hybrid. Aunque el artículo se centra en Skype Empresarial, todos los conceptos se aplican también a Lync Server 2013. Consulte la [sección requisitos de versión del](/SkypeForBusiness/hybrid/plan-hybrid-connectivity#server-version-requirements) servidor para obtener información específica de Lync Server 2013.

También debe asegurarse de que la implementación de Lync Server 2013 esté totalmente actualizada. Publicamos una lista de todas las actualizaciones más recientes para [Lync Server 2013](https://support.microsoft.com/topic/updates-for-lync-server-2013-a2a042ac-79f0-2665-7453-0a541fb25164) Sin embargo, la siguiente actualización es un requisito previo para una actualización a Microsoft Teams:

- Actualización acumulativa de septiembre de [2021 5.0.8308.1149 para Lync Server 2013, Componentes](https://support.microsoft.com/topic/september-2021-cumulative-update-5-0-8308-1149-for-lync-server-2013-core-components-6755903a-fc9a-44d2-b835-2a6d01f14043)principales: Esta actualización reemplaza la autenticación de Live ID por el protocolo de autenticación de OAuth para el cmdlet, que se usa para mover usuarios locales `Move-CSUser` a Microsoft Teams.

Aunque la experiencia del usuario en Microsoft Teams es mucho más rica y superior a Lync, también es muy diferente. Por lo tanto, también tendrá que preparar su organización y los usuarios para garantizar una adopción rápida de Microsoft Teams. Tenemos una gran cantidad de información disponible sobre cómo preparar su organización, planear la actualización a Teams y garantizar una implementación correcta. 

**Le recomendamos [](/MicrosoftTeams/upgrade-skype-teams)** que comience en nuestro portal de actualización de Teams donde encontrará información técnica, recursos de aprendizaje, vínculos a sesiones de Ignite, recursos de ayuda disponibles, casos prácticos y mucho más.

:::image type="content" source="../media/teams-upgrade-portal.png" alt-text="Captura de pantalla del portal Teams actualización":::

### <a name="upgrade-to-skype-for-business-server"></a>Actualizar a Skype Empresarial Server

La ruta de Skype Empresarial Server va a ser diferente en función de la versión a la que elija actualizar. Skype Empresarial Server 2015 admite una actualización local de Lync Server 2013. Por otra parte, para actualizar a Skype Empresarial Server 2019, primero deberá introducir Skype Empresarial Server 2019 en su organización de Lync Server 2013 y, a continuación, transferir operaciones al nuevo servidor. 

Un punto importante a tener en cuenta es que la fase de soporte actual para cada producto: Skype Empresarial 2019 está en soporte estándar y Skype Empresarial 2015 está actualmente en soporte extendido.  Por lo tanto, se recomienda actualizar a Skype Empresarial Server 2019. Para obtener más información sobre la diferencia entre el soporte estándar y el soporte extendido, consulte [Fixed Lifecycle Policy](/lifecycle/policies/fixed).

Vea los siguientes recursos para obtener información detallada acerca de cada escenario de actualización.

- [Actualizar a Skype Empresarial Server 2019](/skypeforbusiness/migration/migration-to-skype-for-business-server-2019)
- [Actualizar a Skype Empresarial Server 2015](/skypeforbusiness/deploy/upgrade-to-skype-for-business-server)
