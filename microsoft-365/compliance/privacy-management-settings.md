---
title: Administrar la configuración de administración de privacidad (versión preliminar)
f1.keywords:
- CSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- M365-privacy-management
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre las opciones de configuración global para la administración de privacidad.
ms.openlocfilehash: b656070c5470ae651bb3b361cfc8481dd9b09212
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "58255072"
---
# <a name="manage-privacy-management-settings-preview"></a>Administrar la configuración de administración de privacidad (versión preliminar)

En este artículo: obtenga información sobre las **opciones de configuración** para la administración de privacidad.

Las opciones de configuración global para la administración de privacidad se encuentran en el icono de engranaje de la esquina superior derecha de las páginas principales. Estas opciones le permiten establecer preferencias de alto nivel y personalizar las propiedades clave. En esta página se proporciona información general sobre las Configuración categorías principales.

## <a name="anonymization"></a>Anonimización

Esta característica permite mostrar versiones anónimas de nombres de usuario dentro de las características de administración de privacidad a los usuarios en determinados roles. Reemplazará los nombres para mostrar identificables por una etiqueta genérica con el fin de ayudar a enmascarar las identidades de los usuarios al revisar los datos confidenciales. Esta opción no se aplica al módulo de solicitud de derechos del sujeto.

## <a name="user-notification-emails"></a>Mensajes de correo electrónico de notificación de usuario  

Las directivas de administración de privacidad le permiten establecer parámetros para evaluar posibles riesgos de privacidad en su entorno. Cuando detectamos una coincidencia de directiva, la administración de privacidad puede enviar un correo electrónico a los usuarios con acciones correctivas que deben realizarse y un vínculo a la formación en privacidad. En Configuración, puede habilitar o deshabilitar la funcionalidad de notificación de correo electrónico de la administración de privacidad en su conjunto. Puede activar notificaciones individuales, establecer la frecuencia del correo electrónico y especificar una dirección URL de aprendizaje al crear o editar una directiva. Si la funcionalidad de notificación está desactivada en Configuración, se deshabilitará cualquier configuración de nivel de directiva para correos de notificación específicos. Para obtener más información sobre las directivas, vea [Create and manage policies](privacy-management-policies.md).

## <a name="teams-collaboration"></a>Colaboración de Teams  

Integre Microsoft Teams con la administración de privacidad para mejorar la colaboración con las partes interesadas. Cada vez que se crea una solicitud de derechos de sujeto, se creará un equipo asociado. Los usuarios se pueden agregar a un equipo desde la pestaña Colaboradores de la solicitud. Para obtener más información acerca de las solicitudes de derechos de sujeto, vea [Manage subject rights requests](privacy-management-subject-rights-requests.md).

## <a name="power-automate-flows"></a>Power Automate flujos  

Use Power Automate para administrar automáticamente procesos y tareas relacionados con la privacidad. Puede crear flujos en la sección Configuración con plantillas de administración de privacidad integradas o usar la consola Power Automate para crear flujos personalizados. Para obtener más información sobre Power Automate, consulte la [Power Automate](/power-automate/) documentación.

## <a name="data-matching"></a>Coincidencia de datos  

Use esta sección para cargar esquemas de datos que describen los atributos de los interesados, lo que le ayudará a identificar al interesado correcto al buscar datos personales en su entorno Microsoft 365 datos. Los esquemas y paquetes de reglas se crean y cargan en formato XML. En Carga de datos personales, también puede enviar datos personales que coincidan con un esquema proporcionado. Puede crear y cargar su propio archivo o elegir cargar datos personales de Azure. Para obtener más información acerca de las solicitudes de derechos de sujeto, vea [Manage subject rights requests](privacy-management-subject-rights-requests.md).

## <a name="data-retention-periods"></a>Períodos de retención de datos  

Para las solicitudes de derechos de sujeto, elija cuánto tiempo desea conservar los datos recopilados y los informes generados. Puede seleccionar entre 30 o 90 días después de cerrar la solicitud. Para obtener más información acerca de las solicitudes de derechos de sujeto, vea [Manage subject rights requests](privacy-management-subject-rights-requests.md).

## <a name="data-review-tags"></a>Etiquetas de revisión de datos  

Administre las etiquetas que usará para marcar los archivos recuperados en una solicitud de derechos de sujeto. En esta sección, puede editar los nombres y descripciones de las etiquetas personalizadas. También puede editar las descripciones de etiquetas de las etiquetas integradas proporcionadas por el sistema. Los nombres de las etiquetas del sistema no se pueden cambiar. Para obtener más información acerca de las solicitudes de derechos de sujeto, vea [Manage subject rights requests](privacy-management-subject-rights-requests.md).
