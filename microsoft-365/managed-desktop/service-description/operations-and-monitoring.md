---
title: Supervisión y operaciones de Escritorio administrado de Microsoft
description: Quién lo que hace para varios procesos de cambio
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
ms.openlocfilehash: 6b1771660cb25ccd9d23c97d1e3fcf6edd27feaa
ms.sourcegitcommit: 559df2c86a7822463ce0597140537bab260c746a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2022
ms.locfileid: "62825232"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Supervisión y operaciones de Escritorio administrado de Microsoft

<!-- Operations and monitoring: -->

## <a name="change-management"></a>Administración de cambios

En la oferta de servicio, el equilibrio de responsabilidad del mantenimiento de hardware y las actualizaciones de seguridad cambia al proveedor de servicios (Microsoft) en lugar del cliente (usted). Sin embargo, debe asegurarse de que el software que no sea de Microsoft y personalizado siga funcionando como se esperaba cuando se desarollan las actualizaciones.

En el caso de los productos locales, la organización asume toda la responsabilidad de administrar los cambios.

### <a name="balance-of-responsibility"></a>Equilibrio de responsabilidades

| Responsabilidad | Servicio de Escritorio administrado de Microsoft | Microsoft 365 cliente | Clientes y servidores locales | Software que no es de Microsoft y personalizado
| ----- | ----- | ----- | ----- | ----- |
| Proporciona nuevas funciones | Microsoft | Microsoft | Ambas | Clientes
| Probar las características nuevas como control de calidad |  Microsoft | Microsoft | Ambas | Clientes
| Comunicar las características nuevas | Ambas | Ambas | Ambas | Clientes
| Integrar software personalizado | Ambas | Ambas | Clientes | Clientes
| Aplicar las actualizaciones de seguridad | Microsoft | Microsoft | Clientes | Clientes
| Mantener el software del sistema | Microsoft | Microsoft | Clientes | Clientes
| Paquete para la implementación | Microsoft | Microsoft | Clientes | Clientes

### <a name="change-process-overview"></a>Introducción al proceso de cambio

A continuación se muestra un resumen de cómo se comparte el proceso de cambio entre Microsoft y los clientes:

| Escenario | Rol de Microsoft | Rol del cliente |
| ----- | ----- | ----- |
| Antes de un cambio | <ul><li>Establecer las expectativas en relación con los cambios en el servicio.</li><li>Notifique a los clientes con 5 días de antelación los cambios que requieran una acción de administrador.</li><li>Para los cambios de emergencia, aplique una mitigación antes de notificar.</li></ul> | <ul><li>Comprender qué esperar de los cambios y las comunicaciones.</li><li>Lea El Centro de mensajes de Escritorio administrado de Microsoft con regularidad.</li><li>Revisar y actualizar los procesos de administración de cambios internos.</li><li>Comprender y comprobar el cumplimiento de los requisitos de Microsoft Managed Desktop. </li><li>Confirme y apruebe, cuando sea necesario.</li></ul>
| Durante un cambio | <ul><li>Libere e implemente actualizaciones mensuales de seguridad y no de seguridad para Windows 10 y Office 365 clientes.</li><li>Supervisar las señales de datos y las colas de soporte técnico en busca de impacto.</li></ul> | <ul><li>Compruebe el Centro de mensajes de Escritorio administrado de Microsoft y revise cualquier información adicional.</li><li>Realizar cualquier acción necesaria, si procede, y probar aplicaciones.</li><li>Si se experimenta un escenario de interrupción o corrección, cree una solicitud de soporte técnico.</li></ul> |
| Después de un cambio | <ul><li>Recopila los comentarios de los clientes para mejorar la implementación de futuros cambios.</li><li>Supervisar las señales de datos y las colas de soporte técnico en busca de impacto.</li></ul> | <ul><li>Trabaje con personas de su organización para adoptar el cambio.</li><li>Revise los procesos de administración de cambios y adopción para obtener oportunidades para obtener eficiencias.</li><li>Proporcionar comentarios generales y comentarios específicos en la herramienta de comentarios del administrador.</li><li>Entrena a los usuarios para que proporcionen comentarios específicos de la aplicación mediante el Centro de opiniones sobre Windows y el botón Smile en Office aplicaciones.</li></ul> |

### <a name="change-types"></a>Tipos de cambio

Hay varios tipos de cambios que se hacen en el servicio con regularidad. El canal de comunicación de esos cambios y las acciones de las que eres responsable varían.

No todos los cambios tienen el mismo efecto en los usuarios o requieren acción. Algunas están planeadas y otras no planeadas. Por ejemplo, las actualizaciones que no son de seguridad y las actualizaciones de seguridad no suelen planearse.

Según el tipo de cambio, el canal de comunicación puede variar. En la tabla siguiente se enumeran los tipos de cambios que puede esperar para el servicio de Escritorio administrado de Microsoft.

|  | Funcionalidad | Actualizaciones no relacionadas con la seguridad | Seguridad |
| ----- | ----- | ----- | ----- |
| **Tipo de cambio** | <ul><li>Actualizaciones de características</li><li>Nuevas características o aplicaciones</li><li>Características desusadas</li></ul> | Revisiones de cliente para problemas | Actualizaciones de seguridad |
**Comunicación con la antelación suficiente** | Aviso de cinco días para los cambios que requieren acción | No se incluyen estos cambios en la versión mensual | No se incluyen cambios en la versión mensual |
**Canal de comunicación** | <ul><li>Centro de mensajes</li><li>Alerta de correo electrónico</li></ul> | <ul><li>Centro de mensajes</li><li>Alerta de correo electrónico</li></ul> | <ul><li>Centro de mensajes</li><li>Alerta de correo electrónico</li></ul> |
**Requiere acción de administrador global** | A veces | Rara vez | Rara vez |
**Tipo de acción** | Cambiar configuración | Comunicar los cambios a los usuarios | Cambiar la configuración de administración |
**Requiere pruebas** | Comprobar aplicaciones empresariales, incluidos los servicios de acceso remoto | A veces; probar la corrección con procesos o personalizaciones | De forma muy ocasional |
**Ejemplos de cambios** | <ul><li>Actualizaciones de características: El Portal de administración de TI simplifica el envío y revisión de vales de soporte técnico</li><li>Nuevas características o aplicaciones: Semi-Annual versión de una actualización Windows 10 características</li></ul> | Revisiones basadas en errores notificados por los clientes |

## <a name="standard-operating-procedures"></a>Procedimientos operativos estándar

Microsoft implementa y opera el servicio de Escritorio administrado de Microsoft en la instancia de nube de Microsoft donde puede llevar a cabo otras actividades administrativas. Microsoft es el único responsable de la configuración, configuración y operación específicas de Microsoft Managed Desktop.

En el caso de los productos locales, la organización asume toda la responsabilidad de administrar la configuración y las actividades operativas y de configuración.

| Categorías | Microsoft will | El cliente lo hará |
| ----- | ----- | ----- |
| Red (proxy, inspección de paquetes, VPN) | Aconsejar y planear con los clientes para minimizar los riesgos para los usuarios empresariales. | <ul><li>Crear una solicitud de soporte técnico que solicite información para un cambio de configuración planeado. Incluya los detalles de configuración, el ámbito, la escala de tiempo y otros detalles pertinentes que Microsoft debe revisar.</li><li>Solo aplique un cambio una vez que Microsoft Managed Desktop Operations haya evaluado y recomendado.</li></ul> |
Cuentas de servicio  | <ul><li>Implemente, almacene y administre las credenciales de forma segura.</li><li>Comunique el acceso no autorizado o el uso de estas credenciales al equipo de operaciones de seguridad.</li></ul> | <ul><li>Crear una solicitud de soporte técnico que solicite información para un cambio de configuración planeado. Incluya detalles de configuración, ámbito, escala de tiempo y otros detalles pertinentes para que Microsoft lo revise.</li><li>Solo aplique un cambio una vez que Microsoft Managed Desktop Operations haya evaluado y recomendado.</li><li>No asignar directivas, autenticación multifactor, acceso condicional o implementación de aplicaciones a las cuentas de servicio de escritorio administrado de Microsoft.</li><li>No restablezca la contraseña ni use las credenciales.</li><li>Abra una solicitud de soporte técnico de Sev C a Operaciones de escritorio administrado de Microsoft si se observa actividad sospechosa en los registros de auditoría de Intune o Azure, relacionados con estas cuentas de servicio.</li></ul>
| Grupos de dispositivos | <li> Implemente y asigne la pertenencia a dispositivos dentro de los grupos de Escritorio administrado de Microsoft.</li><li>Use los grupos de Escritorio administrado de Microsoft para administrar la asignación y la versión de la configuración y las actualizaciones de los dispositivos.</li></ul> | <ul><li>Crear una solicitud de soporte técnico que solicite información para un cambio de configuración planeado. Incluya detalles de configuración, ámbito, escala de tiempo y otros detalles pertinentes para que Microsoft lo revise.</li><li>Solo aplique un cambio una vez que Microsoft Managed Desktop Operations haya evaluado y recomendado.</li><li>Solo asigne dispositivos a cualquier grupo de Escritorio administrado de Microsoft siguiendo los pasos descritos en [Asignar dispositivos a un grupo de implementación](../working-with-managed-desktop/assign-deployment-group.md).</li><li>Solo use los grupos para asignar certificados corporativos para servicios como VPN, Windows Hello para empresas o cifrado de correo electrónico o configuración de perfiles wifi corporativos.</li><li>Cuando exista la administración en colaboración, excluya explícitamente todos los grupos de Escritorio administrado de Microsoft al implementar el cliente de Configuration Manager.</li></ul>
| Directivas | <ul><li>Implemente y administre las directivas de Escritorio administrado de Microsoft que rigen el estado de configuración de los dispositivos dentro del servicio.</li><li> Implemente actualizaciones, en directivas o Windows, de forma incremental mediante grupos de dispositivos.</li><li>Excluir explícitamente los grupos de escritorio administrado que no son de Microsoft.</li></ul> | <ul><li>Crear una solicitud de soporte técnico que solicite información para un cambio de configuración planeado. Incluya detalles de configuración, ámbito, escala de tiempo y otros detalles pertinentes para que Microsoft lo revise.</li><li>Solo aplique un cambio una vez que Microsoft Managed Desktop Operations haya evaluado y recomendado.</li><li>No editar ni asignar directivas de Escritorio administrado de Microsoft a dispositivos o usuarios que no están administrados por el servicio de Escritorio administrado de Microsoft.
Microsoft 365 Defender para endpoint.</li></ul> | Supervisar e investigar dispositivos dentro del ámbito del servicio de Escritorio administrado de Microsoft. | <ul><li>Crear una solicitud de soporte técnico que solicite información para un cambio de configuración planeado. Incluya detalles de configuración, ámbito, escala de tiempo y otros detalles pertinentes para que Microsoft lo revise.</li><li>Solo aplique un cambio una vez que Microsoft Managed Desktop Operations haya evaluado y recomendado.</li></ul>
| Microsoft Store para Empresas | Configure y mantenga el perfil Windows Autopilot para el servicio de Escritorio administrado de Microsoft. | <ul><li>Crear una solicitud de soporte técnico que solicite información para un cambio de configuración planeado. Incluya detalles de configuración, ámbito, escala de tiempo y otros detalles pertinentes para que Microsoft lo revise.</li><li>Solo aplique un cambio una vez que Microsoft Managed Desktop Operations haya evaluado y recomendado.</li><li>No modifique la configuración del perfil de Microsoft Managed Desktop Windows Autopilot ni agregue o quite los dispositivos asignados.</li></ul>
| Certificados | | <ul><li>Cree una solicitud de soporte técnico 60 días antes de que expire un certificado, solicitando información para un cambio de configuración planeado. Incluya detalles de configuración, ámbito, escala de tiempo y otros detalles pertinentes para que Microsoft lo revise.</li><li>Solo aplique un cambio una vez que Microsoft Managed Desktop Operations haya evaluado y recomendado.</li><li>Actualice todos los certificados necesarios para configurar perfiles de certificado, perfiles VPN y Wi-Fi certificados.</li></ul>|

## <a name="device-wipe-with-factory-reset"></a>Borrado del dispositivo con restablecimiento de fábrica

El equipo de Operaciones de escritorio administrado de Microsoft puede realizar un restablecimiento de fábrica de los dispositivos inscritos en el servicio cuando sea necesario. El restablecimiento es útil si necesitas dar un dispositivo a un empleado diferente o si un empleado deja tu empresa.

Existen algunos requisitos:

- El administrador global debe enviar una solicitud de soporte técnico.
- Incluya el nombre del equipo del dispositivo en la solicitud.
- La cuenta de usuario debe estar en Azure AD antes de restablecer el dispositivo.

El equipo de operaciones de escritorio administrado:

- Busque el nombre del dispositivo en Intune.
- Envíe el comando de restablecimiento de fábrica al dispositivo.

> [!NOTE]
> No quite la cuenta de usuario de Azure AD antes de restablecer el dispositivo. Si el usuario no está en Azure AD, Intune no puede enviar el comando de restablecimiento de fábrica al dispositivo.

El dispositivo arrancará en la "experiencia de inicio" y todas las aplicaciones preinstaladas y la configuración se aplicarán de nuevo. El usuario del dispositivo debe proporcionar información de configuración inicial de nuevo.

Cuando el dispositivo se haya restablecido, puedes dáslo a otra persona de la organización. Ninguno de los datos del usuario anterior ni los datos de empresa estarán en el dispositivo. El siguiente usuario pasará por el mismo proceso que hizo la persona anterior con un nuevo dispositivo de Escritorio administrado de Microsoft.

BitLocker es un componente clave de la seguridad de datos en este proceso. Con el cifrado de BitLocker en dispositivos de Escritorio administrado de Microsoft, los datos de la unidad permanecen seguros incluso después de que el dispositivo se haya restablecido de fábrica. Los datos que se encontraban en la unidad no estarán disponibles para el siguiente usuario del dispositivo. Para obtener más información, consulta [Introducción a BitLocker](/windows/security/information-protection/bitlocker/bitlocker-overview).

Para obtener más información, consulta [Restablecer un dispositivo de fábrica](/intune/remote-actions/devices-wipe#factory-reset-a-device).
