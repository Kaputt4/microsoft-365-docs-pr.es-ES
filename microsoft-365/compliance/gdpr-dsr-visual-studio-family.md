---
title: Solicitudes de interesados de la familia de Visual Studio para el RGPD y CCPA
description: Solicitudes de interesados de la familia de Visual Studio para el RGPD y CCPA
keywords: Visual Studio, Visual Studio Code, Visual Studio para Mac, documentación de Visual Studio, privacidad, RGPD y CCPA
localization_priority: Priority
audience: itpro
ms.prod: visual-studio-family
ms.topic: article
ms.date: 05/24/2018
author: robmazz
f1.keywords:
- NOCSH
ms.author: robmazz
manager: laurawi
ms.collection:
- GDPR
- M365-security-compliance
ms.workload:
- multiple
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 159e7a69f0714b93913c36d745641485d7c80798
ms.sourcegitcommit: 48b69caf6550e68cb14472ea8cfc76b53e7ae9c6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42225513"
---
# <a name="visual-studio-family-data-subject-requests-for-the-gdpr-and-ccpa"></a>Solicitudes de interesados de la familia de Visual Studio para el RGPD y CCPA

El [Reglamento General de Protección de Datos (RGPD)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) de la Unión Europea ofrece derechos a los individuos (que se denominan _interesados_ en el reglamento) para administrar sus datos personales. Los datos personales se definen de forma muy amplia según el RGPD como cualquier dato relacionado con una persona física, ya sea identificada o identificable. El RGPD ofrece a los interesados derechos específicos sobre sus datos personales, como la obtención de copias de sus datos, la solicitud de correcciones, impedir su tratamiento o eliminación o el envío en formato electrónico. Una solicitud formal realizada por un interesado a un responsable de los datos (que es un empleado o cualquier otro tipo de agencia u organización que tiene control sobre los datos personales) para realizar una acción en sus datos personales se denomina _solicitud de interesado_.

De forma similar, la Ley de Privacidad de Consumidores de California (CCPA) establece derechos y obligaciones de privacidad a los consumidores de California, incluidos derechos similares a los sancionados por el RGDP, como el derecho a eliminar, obtener acceso y recibir (portabilidad) sus datos personales.  La CCPA también prevé casos de divulgación de información, protecciones contra la discriminación en el ejercicio de derechos y requisitos de "cancelación/suscripción" para ciertas transferencias de datos clasificadas como "ventas". Las ventas se definen de forma amplia para incluir el uso compartido de datos con ánimo de lucro. Para obtener más información sobre la CCPA, consulte la [Ley de Privacidad de los Consumidores California](offering-ccpa.md) y las [Preguntas más frecuentes sobre la privacidad del consumidor de California](ccpa-faq.md).

Para obtener información general sobre el RGPD, consulte la [sección RGPD del Portal de confianza de servicios](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted).

## <a name="products-covered-by-this-guide"></a>Productos cubiertos en esta guía

Esta guía describe cómo usar las herramientas de Microsoft para exportar o eliminar datos personales recopilados durante una sesión autenticada (en la que se haya iniciado sesión) de Visual Studio y Visual Studio para Mac y sus extensiones de Microsoft y Visual Studio Code. Asimismo, en esta guía se explica cómo crear solicitudes de interesados para los datos personales que se recopilan al usar Visual Studio Developer Community, NuGet.org y el ASP.NET Web. Es posible que estos productos habiliten el uso de herramientas y extensiones que no sean de Microsoft y que Microsoft no sea procesador ni controlador de datos de estas herramientas y extensiones. Los usuarios deben ponerse en contacto con el proveedor de estas extensiones y herramientas para conocer sus directivas de recopilación de datos personales.

## <a name="additional-privacy-information"></a>Información de privacidad adicional

Nuestros procedimientos de procesamiento de datos se explican en los Términos de licencia del software de Microsoft que se incluyen junto con los productos, en la [declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?LinkId=660726) y en los [compromisos con el RGPD de Microsoft](https://docs.microsoft.com/legal/gdpr).

## <a name="visual-studio-visual-studio-for-mac-and-visual-studio-code"></a>Visual Studio, Visual Studio para Mac y Visual Studio Code

### <a name="personal-data-we-collect"></a>Los datos personales que recopilamos

En tanto que procesador de datos en virtud de lo estipulado en el RGPD, Microsoft recopila los datos que necesitamos de los usuarios para proporcionar experiencias y mejorar Visual Studio y Visual Studio para Mac, además de para facilitar extensiones de Microsoft aplicables a ellos y a Visual Studio Code. Existen dos categorías de datos: datos de cliente y registros generados por el sistema. Los datos de cliente son los datos de interacciones y transacciones que identifican al usuario que estos productos necesitan para realizar el servicio que prestan. Por ejemplo, para facilitar a los usuarios experiencias personalizadas como la configuración de itinerancia, necesitamos recopilar información de la cuenta de usuario y datos de configuración. En cuanto a los registros generados por el sistema, son datos de uso y de diagnóstico que sirven para detectar y solucionar problemas y mejorar nuestros productos y servicios. Este tipo de datos también puede contener información que identifique a los usuarios finales, como sus nombres de usuario. Los registros generados por el sistema se conservan durante un máximo de 18 meses. A modo de ejemplo, los registros generados por el sistema se agregan cada día de uso del producto e incluyen la fecha de uso, el producto empleado (por ejemplo, "Visual Studio 2017"), la acción realizada (por ejemplo, "vs/core/packagecostsummary/solutionload") y el número de veces que dicha acción se ha realizado, como se muestra en este ejemplo:

```Log
{Time":"2/23/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/core/packagecostsummary/solutionload","Target":"1 times",
"DevicePlatform":"Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}

{Time":"2/23/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/ide/connected/accountmanagement/account","Target":"1 times",
"DevicePlatform": "Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}

{"Time":"2/27/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/core/perf/satellitepagefileusage","Target":"23 times",
"DevicePlatform":"Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}
```

Para más información, vea [Registros generados por el sistema recopilados por Visual Studio](https://docs.microsoft.com/visualstudio/ide/diagnostic-data-collection).

Una solicitud de interesado solo se puede cursar con datos personales que guarden relación con una identidad autenticada; por ejemplo, como Visual Studio Code no admite el inicio de sesión, los registros generados por el sistema desde este producto no estarán vinculados a una identidad autenticada y no se podrá cursar este tipo de solicitudes. Pese a esto, algunas extensiones de Microsoft para Visual Studio Code pueden facilitar datos autenticados y estos datos sí son válidos en una solicitud de interesado. Para más información, vea [RGPD y Visual Studio Code](https://code.visualstudio.com/docs/supporting/faq#_gdpr-and-vs-code). En general, no guardamos datos de Visual Studio 2013 y versiones anteriores, si bien algunas extensiones y componentes pueden facilitar datos vinculados con identidades autenticadas y sí se podrá cursar la solicitud de interesado, tal como se describe abajo.

### <a name="how-users-can-control-personal-data"></a>Cómo pueden controlar los usuarios los datos personales

Visual Studio 2015 y las versiones posteriores, Visual Studio para Mac y Visual Studio Code cuentan con los siguientes medios para que los usuarios puedan detener la recopilación de datos y para que los poseedores de datos como usted puedan exportar o eliminar los datos que ya se hayan recopilado.

#### <a name="in-app-settings"></a>Configuración desde la aplicación

Los usuarios pueden controlar la configuración de privacidad de estos productos. Para más información, vea los siguientes temas:

- [Cómo administrar la configuración de privacidad en Visual Studio](https://docs.microsoft.com/visualstudio/ide/visual-studio-experience-improvement-program)
- [Cómo administrar la configuración de privacidad en Visual Studio para Mac](https://docs.microsoft.com/visualstudio/mac/visual-studio-experience-improvement-program)
- [Cómo desactivar los informes de telemetría en Visual Studio Code](https://code.visualstudio.com/docs/supporting/faq#_how-to-disable-telemetry-reporting).

#### <a name="exporting-or-deleting-data"></a>Exportar o eliminar datos

Los poseedores de datos pueden recurrir a uno de dos métodos posibles para administrar los datos de cliente y los registros generados por el sistema recopilados de los titulares de los datos, según cómo se haya registrado el producto de la familia de Visual Studio o las extensiones de Microsoft. En algunos casos, se deben usar ambos métodos. Por medio de estos métodos, los poseedores de datos pueden descargar una copia del historial de actividades administrado por el método en cuestión. El cierre de una cuenta de AAD o MSA elimina los datos de cliente de Visual Studio asociados y anonimiza los datos de identificación personal en los registros generados por el sistema que pertenezcan a estos productos. Los registros generados por el sistema anonimizados se conservan durante un máximo de 18 meses.

- Los usuarios que hayan registrado un producto de la familia de Visual Studio con una cuenta respaldada por un inquilino de Azure (como, por ejemplo, una cuenta de AAD o MSA asociada a una suscripción a Azure) pueden seguir las instrucciones de [Solicitudes de interesados de Azure para el RGPD](gdpr-dsr-azure.md).
- Los usuarios que hayan registrado un producto de la familia de Visual Studio sin una cuenta respaldada por un espacio empresarial de Azure (por ejemplo muchas cuentas que usan una cuenta Microsoft -MSA-), pueden dirigirse a [Centro de respuesta de privacidad de Microsoft basado en web](https://aka.ms/userprivacysite), disponible a través de la cuenta Microsoft, para ver, controlar y eliminar datos de actividades vinculados a su cuenta Microsoft en varios servicios Microsoft. En este escenario, el usuario es el poseedor de sus propios datos personales.

> [!NOTE]
> Cuando un titular de la cuenta MSA elimina su cuenta, todos los datos de identificación personal que pertenezcan a estos productos se eliminarán (tanto si la cuenta está respaldada por un inquilino de Azure como si no) y los registros generados por el sistema se anonimizarán.

En Visual Studio 2013, los datos que recopilamos se anonimizan, mientras que en Visual Studio de 2012 y versiones anteriores, los datos se eliminan inmediatamente en cuanto se reciben. En ambos casos, no hay nada que ver, exportar o eliminar a posteriori.

## <a name="visual-studio-developer-community"></a>Comunidad de desarrolladores de Visual Studio

Admitimos solicitudes para el [Reglamento general de protección de datos (RGPD)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) cursadas a través del sitio web de la [comunidad de desarrolladores](https://developercommunity.visualstudio.com). Puede ver, exportar o eliminar los datos de comentarios.

### <a name="personal-data-we-collect"></a>Los datos personales que recopilamos

Microsoft recopila datos que nos sirven para reproducir y solucionar los problemas que se nos haya notificado relativos a la familia de Visual Studio. Estos datos incluyen datos personales y comentarios públicos. Los datos personales engloban lo siguiente:

- Información de perfil de la [comunidad de desarrolladores](https://developercommunity.visualstudio.com)
- Preferencias y notificaciones
- Datos adjuntos y registros generados por el sistema facilitados al [informar de un problema en Visual Studio](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) o a través de la [comunidad de desarrolladores](https://developercommunity.visualstudio.com)
- Sus votos.

En cuanto a los comentarios públicos, se componen de problemas notificados, comentarios y soluciones.

### <a name="how-users-can-control-personal-data"></a>Cómo pueden controlar los usuarios los datos personales

#### <a name="view"></a>Ver

Haga lo siguiente para ver los datos relacionados con sus comentarios:

1. Inicie sesión en la [Comunidad de desarrolladores](https://developercommunity.visualstudio.com). En la esquina superior derecha, haga clic en su perfil y seleccione **Perfil y preferencias**.
2. Haga clic en cualquiera de estas pestañas: **Perfil**, **Notificaciones**, **Actividad** y **Datos adjuntos**, para ver los datos enviados a los sistemas de comentarios.
   1. **Perfil** es su perfil de la [comunidad de desarrolladores](https://developercommunity.visualstudio.com), esto es, su nombre de usuario, dirección de correo, sección Acerca de, etc.
   2. En **Notificaciones se indica cómo controlar las notificaciones de correo electrónico que recibe.
   3. En **Actividad** encontrará los elementos de comentarios en los que ha participado (publicando, comentando, etc.) y las actividades realizadas.
   4. **Datos adjuntos** es una lista con el historial de datos adjuntos en un formato similar a `FileName was attached to the problem "ProblemName" Tue, Apr 10, 18 2:27 PM`.

#### <a name="export"></a>Exportar

Puede exportar los datos de comentarios como parte de una solicitud de interesado. Crearemos uno o más archivos .zip que incluirán lo siguiente:

- Información de perfil de la [comunidad de desarrolladores](https://developercommunity.visualstudio.com)
- Configuración de preferencias y notificaciones
- Datos adjuntos facilitados al [informar de un problema en Visual Studio](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) o a través de la [comunidad de desarrolladores](https://developercommunity.visualstudio.com)

> [!NOTE]
> Se excluirán los siguientes comentarios públicos que haya proporcionado del archivo: comentarios, soluciones y problemas notificados.

Haga lo siguiente para iniciar una exportación:

1. Inicie sesión en la [Comunidad de desarrolladores](https://developercommunity.visualstudio.com). En la esquina superior derecha, haga clic en su perfil y seleccione **Perfil y preferencias**.
2. Haga clic en la pestaña **Privacidad** y, después, haga clic en **Crear un archivo** para solicitar la exportación de los datos.
3. El **estado del archivo** se actualizará para reflejar que los datos se están preparando. El tiempo que transcurre hasta que los datos estén disponibles dependerá de la cantidad de datos que se vayan a exportar.
4. Cuando los datos estén listos, le enviaremos un correo electrónico.
5. Haga clic en **Descargar archivo** en el correo electrónico, o bien vaya a la pestaña Privacidad para descargar los datos.

> [!NOTE]
> - No le enviaremos ningún correo electrónico si ha optado por no recibir notificaciones en la ficha Notificaciones.
> - Si vuelve a solicitar una exportación, el archivo antiguo se quitará y se creará otro.

#### <a name="delete"></a>Eliminar

Con el proceso de eliminación se quitará la siguiente información sobre el usuario de la [comunidad de desarrolladores](https://developercommunity.visualstudio.com):

- Información del perfil
- Configuración de preferencias y notificaciones
- Datos adjuntos facilitados al [informar de un problema en Visual Studio](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) o a través de la [comunidad de desarrolladores](https://developercommunity.visualstudio.com)
- Sus votos

> [!NOTE]
> La siguiente información pública no se eliminará, sino que se anonimizará: sus comentarios, soluciones y los problemas que haya notificado.
>
> [!IMPORTANT]
> Cuando una cuenta de AAD o MSA se elimina, se activa el proceso de eliminación de la [comunidad de desarrolladores](https://developercommunity.visualstudio.com).

Haga lo siguiente para iniciar una eliminación:

1. Inicie sesión en la [Comunidad de desarrolladores](https://developercommunity.visualstudio.com). En la esquina superior derecha, haga clic en su perfil y seleccione **Perfil y preferencias**.
2. Haga clic en la pestaña **Privacidad** y, luego, haga clic en **Eliminar los datos y la cuenta** para iniciar la eliminación de los datos.
3. Aparecerá una pantalla de confirmación.
4. Escriba "delete" (eliminar) en el cuadro y haga clic en **Eliminar mi cuenta**.

Cuando haga clic en **Eliminar mi cuenta**:

- La sesión se cerrará.
- Se eliminará su cuenta de la [comunidad de desarrolladores](https://developercommunity.visualstudio.com), junto con sus datos personales y datos adjuntos.
- Sus comentarios públicos se anonimizarán. Estos comentarios seguirán estando disponibles en la comunidad de desarrolladores y aparecerán indicados como procedentes de un usuario anónimo.
- Una vez eliminada la cuenta, no le enviaremos ningún correo electrónico porque ya no formará parte del sistema.
- Si informa de un problema nuevo o inicia sesión en la [comunidad de desarrolladores](https://developercommunity.visualstudio.com), se le considerará un usuario nuevo.
- Si elimina su cuenta de la [comunidad de desarrolladores](https://developercommunity.visualstudio.com), no significa que se va a eliminar también de otros servicios Microsoft.

## <a name="xamarin-forums"></a>Foros de Xamarin

### <a name="personal-data-we-collect"></a>Los datos personales que recopilamos

En la comunidad de usuarios de los [foros de Xamarin](https://forums.xamarin.com/), Microsoft recopila datos que usted nos proporciona para ayudarnos a reproducir y solucionar los problemas que pueda tener con productos y servicios de Microsoft. Estos datos incluyen datos personales y comentarios públicos. Los datos personales que recopilamos son los datos de la cuenta de usuario (por ejemplo, los nombres de usuario y las direcciones de correo electrónico asociados a los foros de Xamarin), y los comentarios públicos que recopilamos incluyen errores, problemas, comentarios y soluciones que nos proporciona en los foros de Xamarin.

### <a name="how-you-can-control-your-data"></a>Controlar sus datos

#### <a name="xamarin-forums"></a>Xamarin Forums

##### <a name="view"></a>Ver

Los usuarios con cuentas de Xamarin Forums activas pueden ver sus datos personales y comentarios públicos (por ejemplo, todas las conversaciones y publicaciones que tengan registradas) desde la página de la cuenta de Xamarin Forums. También pueden editar estos datos personales en la misma página de la cuenta.

##### <a name="export"></a>Exportar

Xamarin Forums se hospeda por medio de un tercero, Vanilla Forums. Para solicitar la exportación de los datos públicos, hay que ponerse en contacto a través de forums@xamarin.com (dirección que supervisa el equipo de Xamarin). Tras ello, colaboraremos directamente con Vanilla Forums para cursar esta solicitud.

##### <a name="delete"></a>Delete

Xamarin Forums se hospeda por medio de un tercero, Vanilla Forums. Para solicitar la eliminación de los datos personales y públicos, hay que ponerse en contacto a través de forums@xamarin.com (dirección que supervisa el equipo de Xamarin). Tras ello, nos encargaremos de la solicitud de eliminación de datos personales del usuario.

> [!NOTE]
> Bugzilla para Xamarin ya no acepta nuevos problemas. Los antiguos usuarios de Xamarin Bugzilla pueden ver un archivo con todos los errores de los que han informado y todos los comentarios que han agregado a los errores en [https://xamarin.github.io/bugzilla-archives/](https://xamarin.github.io/bugzilla-archives/). Para solicitar la eliminación de datos personales incluidos en el archivo, los usuarios pueden archivar y solucionar en [https://github.com/xamarin/bugzilla-archives/issues/new/choose](https://github.com/xamarin/bugzilla-archives/issues/new/choose). Los comentarios públicos (por ejemplo, errores, problemas, comentarios y soluciones) que los usuarios han publicado en Xamarin Bugzilla no se eliminarán después de recibir una solicitud de eliminación. En su lugar, los comentarios públicos se harán anónimos eliminando el nombre y la dirección de correo electrónico asociados a los comentarios públicos creados por el usuario que envía la solicitud de eliminación.

## <a name="nuget"></a>NuGet

Para más información sobre las solicitudes de interesados en NuGet.org, vea [Solicitudes de datos de usuario](https://docs.microsoft.com/nuget/policies/data-requests).

## <a name="aspnet"></a>ASP.NET

Para más información sobre las solicitudes de interesados en el sitio web ASP.NET, vea [Sitio web ASP.NET y el tratamiento de solicitudes de interesados del RGPD](https://www.asp.net/gdpr).

## <a name="iisnet"></a>IIS.NET

Para más información sobre las solicitudes de interesados en el sitio web IIS.NET, vea [Sitio web IIS.NET y el tratamiento de solicitudes de interesados del RGPD](https://www.iis.net/gdpr).

## <a name="other-visual-studio-family-services"></a>Otros servicios de la familia de Visual Studio

### <a name="surveymonkey"></a>SurveyMonkey

De vez en cuando, invitamos a los clientes a que aporten sus comentarios sobre estos productos a través de SurveyMonkey. Estos datos se eliminan transcurridos 28 días. Al tramitar solicitudes de interesados relativas a estos productos, si ya contamos con respuestas de encuestas autenticadas, las incluimos en la exportación y eliminamos las solicitudes de interesados.

## <a name="learn-more"></a>Más información

- [Compromisos de Microsoft en virtud del RGPD con los clientes de nuestros productos de software empresarial generalmente disponibles](https://docs.microsoft.com/legal/gdpr)
- [Centro de confianza de Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
- [Portal de confianza del servicio](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)
- [Panel de privacidad de Microsoft](https://account.microsoft.com/privacy)
- [Centro de respuesta de privacidad de Microsoft](https://aka.ms/userprivacysite)
- [Solicitudes de interesados de Azure sobre el RGPD](gdpr-dsr-azure.md)
