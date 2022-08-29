---
title: ¿Qué hay de nuevo en el Centro de administración de Microsoft 365?
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
- MOE150
- FRP150
ms.custom:
- MACDashWhatsNew
- AdminSurgePortfolio
- admindeeplinkMAC
description: 'El Centro de administración de Microsoft 365: obtenga información sobre las características que se agregaron este mes.'
ms.openlocfilehash: 588e5d405bb0a343d95014892d23b62f2e1f28f4
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2022
ms.locfileid: "67388889"
---
# <a name="whats-new-in-the-microsoft-365-admin-center"></a>Novedades de la Centro de administración de Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> Es posible que parte de la información de este artículo no se aplique a Office 365 operados por 21Vianet.

::: moniker-end

Estamos agregando continuamente nuevas características a [la Centro de administración de Microsoft 365](admin-overview/admin-center-overview.md), solucionando problemas que aprendemos y realizando cambios en función de sus comentarios. Algunas características se implantan a diferentes velocidades para nuestros clientes. Si aún no ve una característica, [intente agregarse a la versión de destino](manage/release-options-in-office-365.md).

Y si desea saber las novedades de otros servicios en la nube de Microsoft:

- [Novedades de Azure Active Directory](/azure/active-directory/fundamentals/whats-new)
- [Novedades del Centro de administración de Exchange](/Exchange/whats-new)
- [Novedades de Microsoft Intune](/mem/intune/fundamentals/whats-new)
- [Novedades de la portal de cumplimiento Microsoft Purview](/Office365/SecurityCompliance/whats-new)
- [Novedades de Microsoft 365 Defender](../security/mtp/whats-new.md)
- [Novedades del Centro de administración de SharePoint](/sharepoint/what-s-new-in-admin-center)
- [Actualizaciones de Office](/OfficeUpdates/)
- [Cómo comprobar el estado de la versión de Windows](/windows/deployment/update/check-release-health)

## <a name="may-2022"></a>Mayo de 2022

### <a name="role-based-access-controls-rbac"></a>Controles de acceso basados en rol (RBAC)

Hay cuatro roles nuevos en el Centro de administración de Microsoft 365 para la administración de atributos de seguridad personalizados. Estos roles están disponibles para todos los usuarios en el Centro de administración de Microsoft 365 en **Roles**.

- **Administrador de asignación de atributos**   Asigne claves y valores de atributos de seguridad personalizados a objetos de Azure AD admitidos.

- **Lector de asignación de atributos**   Lee las claves y los valores de atributos de seguridad personalizados para los objetos de Azure AD admitidos.

- **Administrador de definición de atributos**   Defina y administre la definición de atributos de seguridad personalizados.

- **Lector de definición de atributos**   Lee la definición de atributos de seguridad personalizados.

También hay un nuevo rol que le permite conceder a los administradores solo el acceso que necesitan para administrar las visitas virtuales.

- **Administrador de visitas virtuales**   Administre y comparta la información y las métricas de las visitas virtuales desde los centros de administración o la aplicación Visitas virtuales.

Para más información sobre estos roles, consulte [Roles integrados de Azure AD](/azure/active-directory/roles/permissions-reference).

### <a name="quick-assist"></a>Asistencia rápida

Hemos movido Asistencia rápida a la Tienda Windows para mejorar el rendimiento y la seguridad de la aplicación. La aplicación windows Asistencia rápida le permite a usted y a los usuarios finales recibir o proporcionar asistencia para pc a través de una conexión remota.

Con la nueva aplicación Asistencia rápida Store, debería ver una mejora significativa en los tiempos de generación del código de acceso y una reducción de los errores de aplicación.

Para obtener más información, vea [Solucionar problemas de PC a través de una conexión remota](https://support.microsoft.com/windows/solve-pc-problems-over-a-remote-connection-b077e31a-16f4-2529-1a47-21f6a9040bf3) e [Instalar Asistencia rápida](https://support.microsoft.com/windows/install-quick-assist-c17479b7-a49d-4d12-938c-dbfb97c88bca)

## <a name="april-2022"></a>Abril de 2022

### <a name="nps-sentiment-insights"></a>NPS Sentiment Insights

NpS survey insights es un panel controlado por inteligencia artificial disponible en el Centro de administración de Microsoft 365.

En el centro de administración, **vaya a** >  Información de **encuestas npS** **de comentarios** >  del producto de mantenimiento.

Esta característica ayuda a los administradores a obtener información procesable derivada de encuestas NPS de Microsoft a las que los usuarios han respondido. Obtenga más información en [comentarios e información de NPS del producto de Microsoft para su organización](manage/manage-feedback-product-insights.md).

En función de sus comentarios, presentamos una nueva característica que identifica la opinión de cada comentario textual de NPS, para que pueda aprender lo que los usuarios sienten con respecto a los productos de Microsoft 365. Las etiquetas de sentimiento como **Positivo**, **Negativo** y **Otro** se asignan a los comentarios textuales de NPS.

:::image type="content" source="../media/product-feedback-nps-verbatims.png" alt-text="Captura de pantalla: Panel de comentarios del producto en la pestaña Conclusiones de encuestas de NPS":::

Con la característica de opinión en el panel de conclusiones de encuestas de NPS, podrá hacer lo siguiente:

- Visualice la tendencia de opinión de los últimos 12 meses en función de los comentarios textuales de NPS.

- Identifique la opinión por aplicación y plataforma.

Hay tres opiniones disponibles:

:::image type="content" source="../media/sentiment-examples.png" alt-text="Captura de pantalla: Ejemplos y descripciones de sentimiento":::

Para proporcionarle una mejor experiencia con el panel de información de encuestas de NPS, se recomienda comprobar los siguientes elementos:

- Anime a los usuarios a enviar comentarios.

- Confirme que las [directivas de encuestas en el producto](https://config.office.com) están habilitadas.

- Mejore la diagnosticabilidad mediante la habilitación [de Informe de errores de Windows](/windows/win32/wer/windows-error-reporting).

> [!NOTE]
> Si es cliente empresarial y está interesado en unirse a nuestras sesiones de diseño, envíenos un correo electrónico a: prosight@microsoft.com

### <a name="microsoft-365-admin-center-search"></a>Centro de administración de Microsoft 365 búsqueda

Ahora puede ver todos los resultados de búsqueda en una página independiente del explorador si busca en búsqueda global y selecciona **Entrar**.

Con nuestra nueva página independiente de resultados de búsqueda, puede explorar una lista más completa de resultados y volver fácilmente a la página del explorador para una experiencia de búsqueda más eficaz.

:::image type="content" source="../media/whats-new-search-page.png" alt-text="Captura de pantalla: Nueva página de búsqueda del explorador Centro de administración de Microsoft 365":::

### <a name="search-in-distribution-lists-to-add-priority-accounts"></a>Búsqueda en listas de distribución para agregar cuentas de prioridad

Anteriormente, solo podía etiquetar las cuentas de prioridad si las buscaba mediante el nombre, la dirección de correo electrónico o el puesto de trabajo de la persona. Con esta actualización, ahora puede buscar personas para agregar a cuentas de prioridad en una lista de distribución. Esto le permite agregar personas de forma masiva de forma eficaz y reduce el tiempo necesario para etiquetar a personas individuales de su organización.

:::image type="content" source="../media/search-by-distribution-list-priority-accounts.png" alt-text="Captura de pantalla: Búsqueda de cuentas de prioridad para agregar mediante una lista de distribución":::

- Puede etiquetar hasta 50 usuarios de una lista de distribución como cuentas de prioridad en una sola acción.

- Se ha introducido información adicional sobre el usuario, como el departamento y el puesto de trabajo, en la página Cuentas prioritarias.

- Solo puede etiquetar cuentas de usuario dentro de listas de distribución y no la propia lista. Los usuarios que ya se han etiquetado no aparecerán en la búsqueda de la lista de distribución.

## <a name="march-2022"></a>Marzo de 2022

### <a name="microsoft-365-lighthouse-ga"></a>disponibilidad general de Microsoft 365 Lighthouse

Las pequeñas y medianas empresas suelen confiar en asociados de TI de confianza para administrar sus entornos de TI. Facilitamos a los asociados proteger a los clientes a escala con la disponibilidad general de [Microsoft 365 Lighthouse](https://aka.ms/March1SMBPartnerBlog), un portal de administración multiinquilino para proveedores de servicios administrados (MSP). Microsoft 365 Lighthouse proporciona una experiencia completa a los clientes al capacitar a sus asociados para identificar y actuar rápidamente sobre amenazas, inicios de sesión anómalos y alertas de cumplimiento de dispositivos para mantenerlos seguros.

:::image type="content" source="../media/lighthouse.png" alt-text="Captura de pantalla: panel de Microsoft 365 Lighthouse":::

Microsoft 365 Lighthouse solo es un servicio asociado de TI y está disponible para los asociados inscritos en el programa Proveedor de soluciones en la nube (CSP) y administran clientes que tienen hasta 1000 usuarios con licencia con Microsoft 365 Empresa Premium, Microsoft 365 E3 o Microsoft Defender para Empresas suscripciones (en versión preliminar). Si es un asociado de TI inscrito en CSP de Microsoft, Microsoft 365 Lighthouse está disponible sin costo para su organización y está diseñado para ayudar a su negocio a escalar y crecer. Consulte la [biblioteca de ayuda de Microsoft 365 Lighthouse](../lighthouse/m365-lighthouse-overview.md) para obtener más información.

Para empezar a usar Microsoft 365 Lighthouse, consulte [Registro para Microsoft 365 Lighthouse](../lighthouse/m365-lighthouse-sign-up.md). Para obtener más información sobre Microsoft 365 Lighthouse, Defender para empresas y Microsoft 365 Empresa Premium, [únase a nosotros en nuestra serie de seminarios web de asociados](https://aka.ms/M365MDBSeries).

## <a name="february-2022"></a>Febrero de 2022

### <a name="net-promoter-score-nps-survey-insights"></a>Conclusiones de encuestas de puntuación de promotor neto (NPS)

Ahora puede ver los datos e información de las encuestas de NPS de los usuarios en el Centro de administración de Microsoft 365. Con esta nueva característica, puede obtener información útil de las respuestas de encuestas NPS de los usuarios finales y lograr una mayor satisfacción de los usuarios finales abordando cualquier problema y preocupación.

En el centro de administración, **vaya a** >  Información de **encuestas npS** **de comentarios** >  del producto de mantenimiento.

:::image type="content" source="../media/feedback-whatsnew.png" alt-text="Captura de pantalla: Mostrar la página Comentarios en el Centro de administración de Microsoft 365":::

Hemos identificado los temas comunes de los comentarios de los usuarios. A continuación, usamos técnicas de modelos de aprendizaje automático para entrenar los conjuntos de datos y organizar automáticamente los comentarios en temas principales.

Hay nueve temas disponibles. Busque más temas en futuras actualizaciones.

:::image type="content" source="../media/feedback-nine-topics.png" alt-text="Captura de pantalla: Se muestran los 9 nuevos temas de comentarios":::

El panel de información de la encuesta NPS también contiene estos tres nuevos informes y tablas dinámicas:

- Volumen de tendencias de NPS mensual de NPS durante los últimos 12 meses
- Capaz de identificar pasivos, promotores y detractores
- Volumen NPS por plataforma y aplicación

Para proporcionarle una mejor experiencia con el panel de información de encuestas de NPS:

- Anime a los usuarios finales a enviar comentarios
- Confirmación de que las directivas de encuestas en el producto están habilitadas
- Mejora del diagnóstico al activar Informe de errores de Windows

Obtenga más información en [comentarios e información de NPS del producto de Microsoft para su organización](manage/manage-feedback-product-insights.md).  

> [!NOTE]
> Si está interesado en unirse a nuestras sesiones de diseño, envíenos un correo electrónico a: prosight@microsoft.com

### <a name="microsoft-365-admin-center-video-training"></a>Centro de administración de Microsoft 365 entrenamiento en vídeo

Hemos actualizado nuestro Centro de administración de Microsoft 365 entrenamiento en vídeo. Vaya a la página [Administración biblioteca de vídeos de entrenamiento](https://go.microsoft.com/fwlink/?linkid=2197659) para obtener información sobre cómo configurar y administrar Microsoft 365 para su empresa.

:::image type="content" source="../media/admin-library-vid-training.png" alt-text="Captura de pantalla: Mostrar la biblioteca de entrenamiento de vídeo del centro de administración":::

## <a name="july-2021"></a>Julio de 2021

### <a name="microsoft-365-admin-center-search"></a>Centro de administración de Microsoft 365 búsqueda

Ahora puede buscar identificadores de incidentes en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2091030" target="_blank">Centro de administración de Microsoft 365</a>. Puede obtener información sobre los incidentes actuales a través de redes sociales, publicaciones del sector o de otros administradores. Ahora puede ir al Centro de administración para buscar más detalles sobre el incidente y comprender el impacto en su organización. Solo tiene que buscar el identificador de incidente en el centro de administración.

:::image type="content" source="../media/incident-id.png" alt-text="Captura de pantalla: Búsqueda del identificador de incidente en el centro de administración":::

### <a name="support-ticket-insight-for-premier-organizations"></a>Información de incidencias de soporte técnico para organizaciones Premier

Hemos agregado 2 gráficos denominados Tendencia del **volumen** y **Tendencia del volumen por producto** para proporcionarle información visual sobre el volumen de soporte técnico.

El gráfico de alineación de la pestaña **Tendencia de volumen** resalta la tendencia si los casos de soporte técnico aumentan o disminuyen para su organización mes a mes. Puede mantener el puntero sobre el gráfico para comprobar el número de casos de soporte técnico creados en cada mes.

:::image type="content" source="../media/SuppInsight-voltrnd.PNG" alt-text="Captura de pantalla: Gráfico que resalta la tendencia si los casos de soporte técnico aumentan o disminuyen durante el mes de la organización.":::

El gráfico **Tendencia de volumen por producto** muestra los tres productos principales de cada mes con los casos de soporte técnico más altos. Hemos habilitado el filtrado en la tabla y ahora puede filtrar los resultados por **Producto**, **Gravedad** y **Fecha**.

:::image type="content" source="../media/SuppInsight-voltrndproduct.PNG" alt-text="Captura de pantalla: Graph muestra los tres productos principales de cada mes con los casos de soporte técnico más altos":::

También hemos agregado 2 campos nuevos, **Gravedad** y **Fecha cerrada** en la tabla **Ver solicitud de servicio** para proporcionarle más información sobre los vales.

:::image type="content" source="../media/SuppInsight-date-sev.PNG" alt-text="Captura de pantalla: tabla que muestra la ordenación de vales de soporte técnico por gravedad y fecha.":::

Para consultar estas actualizaciones en <a href="https://go.microsoft.com/fwlink/p/?linkid=2166757" target="_blank">Centro de administración de Microsoft 365</a>, vaya a **Solicitudes del servicio de vista** de **soporte** >  técnico en el panel de navegación izquierdo.

## <a name="june-2021"></a>Junio de 2021

### <a name="microsoft-365-admin-center-search"></a>Centro de administración de Microsoft 365 búsqueda

Hemos agregado un par de nuevas categorías a la funcionalidad de búsqueda.

- Ahora puede buscar roles de administrador de Microsoft 365 en búsqueda global y ver y administrar rápidamente las asignaciones de roles desde cualquier página. Por ejemplo, busque **Intune administrador**.

- Ahora puede encontrar experiencias de configuración simplificadas a través de búsqueda global. Esto puede ayudarle a usted y a su equipo a empezar a usar rápidamente nuevas características. Por ejemplo, busque **establecer la contraseña para que nunca expire**.

Para obtener más información sobre la búsqueda en el centro de administración, consulte [Buscar en el Centro de administración de Microsoft 365](manage/search-in-the-mac.md).
