---
title: ¿Por qué necesita usar PowerShell para Microsoft 365?
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: ''
ms.assetid: b3209b1a-40c7-4ede-8e78-8a88bb2adc8a
description: 'Summary: Understand why you must use PowerShell to manage Microsoft 365, in some cases more efficiently and in other cases by necessity.'
ms.openlocfilehash: cbbceddc98bebaed030f4cff2f183d473d716df6
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288472"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a>¿Por qué necesita usar PowerShell para Microsoft 365?

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Con el Centro de administración de Microsoft 365, puede administrar sus Microsoft 365 cuentas de usuario y licencias. También puede administrar los servicios Microsoft 365, como Exchange Online, Teams y SharePoint Online. Si en su lugar usa PowerShell para administrar estos servicios, puede y aprovechar el entorno de línea de comandos y lenguaje de scripting para la velocidad, automatización y capacidades adicionales.

En este artículo se muestra cómo usar PowerShell para administrar Microsoft 365 para:

- Mostrar información adicional que no se puede ver en el Centro de administración de Microsoft 365

- Configurar características y opciones solo es posible con PowerShell

- Realizar operaciones masivas

- Filtrar datos

- Imprimir o guardar datos

- Administrar en todos los servicios

Tenga en cuenta que PowerShell para Microsoft 365 es un conjunto de módulos para Windows PowerShell, que es un entorno de línea de comandos para Windows y plataformas basadas en aplicaciones. Este entorno crea un lenguaje de shell de comandos que se puede extender con módulos adicionales. Proporciona una forma de ejecutar comandos o scripts simples o complejos. Por ejemplo, después de instalar los módulos de PowerShell para Microsoft 365 y conectarse a la suscripción de Microsoft 365, puede ejecutar el siguiente comando para enumerar todos los buzones de usuario para Microsoft Exchange Online:

```powershell
Get-Mailbox
```

También podrías obtener la lista de buzones mediante el Centro de administración de Microsoft 365 pero contar los elementos de todas las listas para todos los sitios de todas las aplicaciones web no es fácil.

PowerShell para Microsoft 365 está diseñado para ayudarle a administrar Microsoft 365, no para reemplazar el Centro de administración de Microsoft 365. Los administradores deben poder usar PowerShell para Microsoft 365 porque hay algunos procedimientos de configuración que solo se pueden realizar a través de PowerShell para Microsoft 365 comandos. Para estos casos, debe saber cómo:

- Instale PowerShell para Microsoft 365 módulos (solo se realiza una vez para cada equipo de administrador).

- Conectar a la suscripción Microsoft 365 (una vez para cada sesión de PowerShell).

- Recopila la información necesaria para ejecutar el PowerShell necesario para Microsoft 365 comandos.

- Ejecute PowerShell para Microsoft 365 comandos.

Después de aprender estas habilidades básicas, no tiene que enumerar los usuarios de buzones mediante el **comando Get-Mailbox.** Tampoco tiene que comprender cómo crear un comando nuevo como el comando citado anteriormente para contar todos los elementos de todas las listas para todos los sitios de todas las aplicaciones web. Microsoft y la comunidad de administradores pueden ayudarle con las tareas necesarias.

## <a name="powershell-for-microsoft-365-can-reveal-information-that-you-cant-see-with-the-microsoft-365-admin-center"></a>PowerShell para Microsoft 365 puede revelar información que no puede ver con el Centro de administración de Microsoft 365

El Centro de administración de Microsoft 365 muestra mucha información útil. Pero no muestra toda la información posible que Microsoft 365 sobre usuarios, licencias, buzones y sitios. Este es un ejemplo para *usuarios y grupos* de la Centro de administración de Microsoft 365:

![Ejemplo de la presentación de usuarios y grupos en el Centro de administración de Microsoft 365.](../media/o365-powershell-users-and-groups.png)

Esta vista proporciona la información que necesita en muchos casos. En cambio, algunas veces necesitará más. Por ejemplo, Microsoft 365 licencias (y las características Microsoft 365 disponibles para un usuario) dependen en parte de la ubicación geográfica del usuario. Es posible que las directivas y características que se pueden extender a un usuario que reside en Estados Unidos no sean las mismas que las que puede extender a un usuario en India o Bélgica. Siga estos pasos en el Centro de administración de Microsoft 365 para determinar la ubicación geográfica de un usuario:

1. Haga doble clic en el **Nombre para mostrar** del usuario.

2. En el panel de presentación de propiedades de usuario, seleccione **detalles**.

3. En la presentación de detalles, seleccione **detalles adicionales**.

4. Desplácese hasta que encuentre el título **País o región:**

     ![Ejemplo de la información de región de un usuario en el Centro de administración de Microsoft 365.](../media/o365-powershell-usage-location.png)

5. Escriba el nombre para mostrar y la ubicación del usuario en una hoja de papel, o cópielo y péguelo en el Bloc de notas.

Debe repetir este procedimiento para cada usuario. Si tiene muchos usuarios, este proceso puede ser tedioso. Con PowerShell para Microsoft 365, puede mostrar esta información para todos los usuarios mediante el siguiente comando:

```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
>PowerShell Core no admite el módulo Microsoft Azure Active Directory para Windows PowerShell y cmdlets que tienen *Msol* en su nombre. Debe ejecutar estos cmdlets desde Windows PowerShell.
>

Este es un ejemplo de los resultados:

```powershell
DisplayName                               UsageLocation
-----------                               -------------
Bonnie Kearney                            GB
Fabrice Canel                             BR
Brian Johnson (TAILSPIN)                  US
Anne Wallace                              US
Alex Darrow                               US
David Longmuir                            BR
```

La interpretación de este comando de PowerShell es: Obtener todos los usuarios de la suscripción Microsoft 365 actual (**Get-AzureADUser**), pero solo mostrar el nombre y la ubicación de cada usuario (**Seleccione DisplayName, UsageLocation**).

Dado que PowerShell para Microsoft 365 admite un lenguaje de shell de comandos, puede manipular aún más la información obtenida por el comando **Get-AzureADUser.** Por ejemplo, tal vez quiera ordenar estos usuarios por su ubicación, agrupando todos los usuarios brasileños, todos los usuarios de Estados Unidos, y así sucesivamente. Este es el comando:

```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

Este es un ejemplo de los resultados:

```powershell
DisplayName                                 UsageLocation
-----------                                 -------------
David Longmuir                              BR
Fabrice Canel                               BR
Bonnie Kearney                              GB
Alex Darrow                                 US
Anne Wallace                                US
Brian Johnson (TAILSPIN)                    US
```

La interpretación de este comando de PowerShell es: obtener todos los usuarios de la suscripción Microsoft 365 actual, pero solo mostrar el nombre y la ubicación de cada usuario y ordenarlos primero por su ubicación y, a continuación, su nombre (**Sort UsageLocation, DisplayName**).

También puede usar filtrado adicional. Por ejemplo, si solo quiere ver la información sobre los usuarios que están en Brasil, use este comando:

```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation
```

Este es un ejemplo de los resultados:

```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

La interpretación de este comando de PowerShell es: Obtener todos los usuarios de la suscripción actual Microsoft 365 cuya ubicación es Brasil (**Donde {$ \_ . UsageLocation -eq "BR"}**) y, a continuación, muestra el nombre y la ubicación de cada usuario.

 **Una nota sobre dominios grandes**

Si tiene un dominio grande con decenas de miles de usuarios, probar algunos de los ejemplos que mostramos en este artículo podría llevar a la limitación. En función de factores como la potencia informática y el ancho de banda de red disponible, es posible que esté intentando hacer demasiado a la vez. Es posible que las organizaciones grandes quieran dividir algunas de estas operaciones de PowerShell en dos comandos.

Por ejemplo, el siguiente comando devuelve todas las cuentas de usuario y muestra el nombre y la ubicación de cada una:

```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

Esto funciona muy bien en los dominios más pequeños. Pero en una organización grande, es posible que desee dividir esa operación en dos comandos: un comando para almacenar la información de la cuenta de usuario en una variable y otro para mostrar la información necesaria. Aquí le mostramos un ejemplo:

```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

La interpretación de este conjunto de comandos de PowerShell es:
1. Obtener todos los usuarios de la suscripción Microsoft 365 actual y almacenar la información en una variable denominada $x (**$x = Get-AzureADUser**).
1.  Muestra el contenido de la variable *$x*, pero solo incluye el nombre y la ubicación de cada usuario (**$x | Seleccione DisplayName, UsageLocation**).

## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a>Microsoft 365 tiene características que solo puede configurar con PowerShell para Microsoft 365

La Centro de administración de Microsoft 365 está diseñada para proporcionar acceso a tareas administrativas comunes y útiles que se aplican a la mayoría de los entornos. En otras palabras, el Centro de administración de Microsoft 365 se diseñó para que el administrador típico pueda llevar a cabo las tareas de administración más comunes. Pero hay algunas tareas que no se pueden realizar en el Centro de administración.

Por ejemplo, el Centro de administración Skype Empresarial online proporciona algunas opciones para crear invitaciones a reuniones personalizadas:

![Ejemplo de la presentación de las invitaciones a reuniones personalizadas en el centro de administración de Skype Empresarial Online](../media/o365-powershell-meeting-invitation.png)

Con esta configuración, puede agregar un toque de personalización y profesionalidad a las invitaciones a reuniones. Pero hay más opciones para la configuración de reuniones que simplemente crear invitaciones a reuniones personalizadas. Por ejemplo, de forma predeterminada las reuniones permiten lo siguiente:

- A los usuarios anónimos obtener entrada automática a cada reunión.

- A los asistentes grabar la reunión.

- A todos los usuarios de la organización poder ser designados como moderadores cuando se unen a la reunión.

Esta configuración no está disponible en el centro de administración Skype Empresarial online. Puede controlarlos desde PowerShell para Microsoft 365. Este es un comando que deshabilita estas tres opciones:

```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> Para ejecutar este comando, debe instalar el Skype Empresarial [módulo de PowerShell en línea](https://www.microsoft.com/download/details.aspx?id=39366).

La interpretación de este comando de PowerShell es:

1. En la configuración de las nuevas reuniones de Skype Empresarial Online (**Set-CsMeetingConfiguration**), deshabilita permitir que los usuarios anónimos obtengan acceso automático a las reuniones (**-AdmitAnonymousUsersByDefault $False**).
2.  Deshabilitar la capacidad de los asistentes para grabar reuniones (**-AllowConferenceRecording $False**).
3. No designe a todos los usuarios de su organización como presentadores (**-DesignateAsPresenter "None"**).

Para restaurar esta configuración predeterminada (habilitar las opciones), ejecute este comando:

```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

También hay otros escenarios similares, por lo que los administradores deben saber cómo ejecutar PowerShell para Microsoft 365 comandos.

## <a name="powershell-for-microsoft-365-is-great-for-bulk-operations"></a>PowerShell para Microsoft 365 es ideal para operaciones masivas

Las interfaces visuales como la Centro de administración de Microsoft 365 son más valiosas cuando se tiene que realizar una sola operación. Por ejemplo, si necesita deshabilitar una cuenta de usuario, puede usar el Centro de administración para localizar y desactivar rápidamente una casilla. Esto puede ser más fácil que realizar una operación similar en PowerShell.

Pero si tienes que cambiar muchas cosas o algunas cosas seleccionadas dentro de un gran conjunto de otras cosas, es posible que Centro de administración de Microsoft 365 sea la mejor herramienta. Por ejemplo, diga que tiene que cambiar el prefijo en miles de números de teléfono o quitar el usuario específico *Ken Myer* de todos los sitios SharePoint online. ¿Cómo lo haría en el Centro de administración de Microsoft 365?

For the last example, say you have several hundred SharePoint Online sites, and you don't know which ones Ken Meyer is a member of. Tendría que empezar en el Centro de administración de Microsoft 365 y, a continuación, realizar este procedimiento para cada sitio:

1. Seleccione la **dirección URL** del sitio.

2. En el **cuadro propiedades de la colección de** sitios, seleccione el vínculo Dirección **del** sitio web para abrir el sitio.

3. En el sitio, seleccione **Compartir**.

4. En el **cuadro de** diálogo Compartir, seleccione el vínculo que muestra todos los usuarios que tienen permisos para el sitio:

     ![Ejemplo de visualización de los miembros de un sitio de SharePoint Online en el centro de administración de SharePoint Online](../media/o365-powershell-view-permissions.png)

5. En el **cuadro de diálogo Compartido** con, seleccione **Avanzadas**.

6. Desplácese hacia abajo en la lista de usuarios, busque y seleccione Ken Myer (suponiendo que tiene permisos para el sitio) y, a continuación, seleccione Quitar permisos **de usuario**.

Esto tardaría mucho *tiempo* en varios cientos de sitios.

La alternativa es ejecutar el siguiente comando en PowerShell para Microsoft 365 quitar Ken Myer de todos los sitios:

```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> Este comando requiere que instale el módulo [SharePoint PowerShell en línea.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

La interpretación de este comando de PowerShell es: Obtener todos los sitios de SharePoint en la suscripción Microsoft 365 actual (**Get-SPOSite**) y para cada sitio quitar Ken Meyer de la lista de usuarios que pueden tener acceso a él (**ForEach {Remove-SPOUser -Site $ \_ . Url -LoginName "kenmyer \@ litwareinc.com"}**).

Le recomendamos Microsoft 365 quitar a Ken Meyer de todos los sitios, incluidos aquellos a los que no tiene acceso. Por lo tanto, los resultados mostrarán errores para los sitios a los que no tiene acceso. Podemos usar una condición adicional en este comando para quitar Ken Meyer solo de los sitios que lo tienen en su lista de inicio de sesión. Pero los errores que se devuelven no causan ningún daño a los propios sitios. Este comando puede tardar unos minutos en ejecutarse en cientos de sitios, en lugar de horas de trabajo a través del Centro de administración de Microsoft 365.

Este es otro ejemplo de operación masiva. Use este comando para agregar a Todos los sitios de la organización *a Bonnie Kearney*, una nueva SharePoint administradora:

```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

La interpretación de este comando de PowerShell es: Obtener todos los sitios de SharePoint en la suscripción Microsoft 365 actual y para cada sitio permitir acceso a Bonnie Kearney agregando su nombre de inicio de sesión al grupo Miembros del sitio (**ForEach {Add-SPOUser -Site $ \_ . Url -LoginName "bkearney \@ litwareinc.com" -Group "Members"}**).

## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a>PowerShell para Microsoft 365 excelente para filtrar datos

El Centro de administración de Microsoft 365 proporciona varias formas de filtrar los datos para localizar fácilmente un subconjunto de información de destino. Por ejemplo, Exchange facilita el filtrado de prácticamente cualquier propiedad de un buzón de usuario. Por ejemplo, esta es la lista de buzones de todos los usuarios que viven en la ciudad de Bloomington:

![Ejemplo de realizar una búsqueda avanzada en el Centro de administración de Microsoft 365 para la lista de buzones de todos los usuarios que viven en la ciudad de Bloomington.](../media/o365-powershell-advanced-search.png)

El Centro de administración de Exchange también le permite combinar criterios de filtro. Por ejemplo, puede encontrar los buzones de todas las personas que viven en Bloomington y trabajan en el departamento de Finanzas.

Pero hay limitaciones en lo que puede hacer en el centro de administración Exchange administración. Por ejemplo, no se podían encontrar fácilmente los buzones de las personas que viven en *Bloomington* o San Diego, ni los buzones de todas las personas que no viven en Bloomington.

Puede usar el siguiente comando de PowerShell para Microsoft 365 para obtener una lista de buzones para todas las personas que viven en Bloomington o San Diego:

```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox&quot; -and ($_.City -eq &quot;San Diego&quot; -or $_.City -eq &quot;Bloomington")} | Select DisplayName, City
```

Este es un ejemplo de los resultados:

```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

La interpretación de este comando de PowerShell es: Obtener todos los usuarios de la suscripción Microsoft 365 actual que tienen un buzón en la ciudad de San Diego o Bloomington (**Where {$ \_ . RecipientTypeDetails -eq "UserMailbox" -and ($ \_ . City -eq "San Diego" -or $ \_ . City -eq "Bloomington")}**) y, a continuación, muestra el nombre y la ciudad de cada uno (**Select DisplayName, City**).

Y este es el comando para enumerar todos los buzones para las personas que viven en cualquier lugar excepto Bloomington:

```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

Este es un ejemplo de los resultados:

```powershell
DisplayName                               City
-----------                               ----
MOD Administrator                         Redmond
Alex Darrow                               San Diego
Allie Bellew                              Bellevue
Anne Wallace                              Louisville
Aziz Hassouneh                            Cairo
Belinda Newman                            Charlotte
Bonnie Kearney                            San Diego
David Longmuir                            Waukesha
Denis Dehenne                             Birmingham
Garret Vargas                             Seattle
Garth Fort                                Tulsa
Janet Schorr                              Bellevue
```

La interpretación de este comando de PowerShell es: Obtener todos los usuarios de la suscripción Microsoft 365 actual que tienen un buzón no ubicado en la ciudad de Bloomington (**Donde {$ \_ . RecipientTypeDetails -eq "UserMailbox" -and $ \_ . City -ne "Bloomington"}**) y, a continuación, muestra el nombre y la ciudad de cada uno.

### <a name="use-wildcards"></a>Usar caracteres comodín

También puede usar caracteres comodín en los filtros de PowerShell para que coincidan con parte de un nombre. Por ejemplo, supongamos que está buscando una cuenta de usuario. Todo lo que puede recordar es que el apellido del usuario era *Anderson* o tal vez *Henderson* o *Jorgenson*.

Puede realizar un seguimiento de ese usuario en el Centro de administración de Microsoft 365 mediante la herramienta de búsqueda y realizar tres búsquedas diferentes:

- Una para  *Anderson*

- Otra para  *Henderson*

- Y otra para  *Jorgenson*

Dado que los tres nombres terminan en "son", puede decir a PowerShell que muestre todos los usuarios cuyo nombre termina en "son". Este es el comando:

```powershell
Get-User -Filter '{LastName -like "*son"}'
```

La interpretación de este comando de PowerShell es: Obtener todos los usuarios de la suscripción Microsoft 365 actual, pero usar un filtro que solo enumera los usuarios cuyos apellidos terminan en "son" (**-Filter '{LastName -like " \* son"}'**). Significa \* cualquier conjunto de caracteres, que son letras en el apellido del usuario.

## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a>PowerShell para Microsoft 365 facilita la impresión o el guardado de datos

El Centro de administración de Microsoft 365 permite ver listas de datos. Este es un ejemplo del Centro de administración de Skype Empresarial Online que muestra una lista de usuarios que se han habilitado para Skype Empresarial Online:

![Ejemplo del centro de administración de Skype Empresarial Online que muestra una lista de usuarios que han sido habilitados para Skype Empresarial Online](../media/o365-powershell-lync-users.png)

Para guardar esa información en un archivo, debe pegarla en un documento o en una Microsoft Excel hoja de cálculo. Cualquiera de los dos casos puede requerir formato adicional. Además, el Centro de administración de Microsoft 365 no proporciona una forma de imprimir directamente la lista mostrada.

Afortunadamente, puede usar PowerShell no solo para mostrar la lista, sino para guardarla en un archivo que se puede importar fácilmente a Excel. Este es un comando de ejemplo para guardar los datos de usuario de Skype Empresarial Online en un archivo de valores separados por comas (CSV), que luego se pueden importar fácilmente como una tabla en una hoja Excel datos:

```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

Este es un ejemplo de los resultados:

![Ejemplo de una tabla importada a una hoja de Excel para Skype Empresarial de usuario en línea que se guardó en un archivo de valores separados por comas.](../media/o365-powershell-data-in-excel.png)

La interpretación de este comando de PowerShell es: Obtener todos los usuarios de Skype Empresarial Online en la suscripción Microsoft 365 actual (**Get-CsOnlineUser**); obtener solo el nombre de usuario, UPN y ubicación (**Seleccione DisplayName, UserPrincipalName, UsageLocation**); y, a continuación, guarde esa información en un archivo CSV denominado C: \\ Logs \\SfBUsers.csv (**Export-Csv -Path "C: \\ Logs \\SfBUsers.csv" -NoTypeInformation**).

También puede usar opciones para guardar esta lista como un archivo XML o una página HTML. De hecho, con comandos de PowerShell adicionales, podría guardarlo directamente como un archivo Excel, con cualquier formato personalizado que desee.

También puede enviar el resultado de un comando de PowerShell que muestra una lista directamente a la impresora predeterminada en Windows. Este es un comando de ejemplo:

```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

Y este es el aspecto que tendrá el documento impreso:

![Ejemplo de un documento impreso que era el resultado de un comando de PowerShell enviado directamente a la impresora predeterminada en Windows.](../media/o365-powershell-printed-data.png)

La interpretación de este comando de PowerShell es: Obtener todos los usuarios de Skype Empresarial Online en la suscripción Microsoft 365 actual; obtener solo el nombre de usuario, UPN y ubicación; y, a continuación, envíe esa información a la impresora Windows predeterminada (**Out-Printer**).

El documento impreso tiene el mismo formato simple que la pantalla en la ventana de comandos de PowerShell. Para obtener una copia impresa, simplemente agregue **| Out-Printer** al final del comando.

## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a>PowerShell para Microsoft 365 permite administrar entre productos de servidor

Los componentes que Microsoft 365 están diseñados para funcionar juntos. Por ejemplo, supongamos que agrega un nuevo usuario a Microsoft 365 y especifica información como el departamento y el número de teléfono del usuario. Esa información estará disponible si accede a la información del usuario en cualquiera de los servicios de Microsoft 365: Skype Empresarial Online, Exchange o SharePoint.

Pero eso es para la información habitual que abarca el conjunto de productos. La información específica del producto, como la información sobre el buzón de correo Exchange usuario, normalmente no está disponible en todo el conjunto de aplicaciones. Por ejemplo, la información sobre si el buzón de un usuario está habilitado o no solo está disponible en el centro de administración Exchange usuario.

Suponga que quiere crear un informe que muestre la información siguiente de todos los usuarios:

- El nombre para mostrar del usuario

- Si el usuario tiene licencia para Microsoft 365

- Si el buzón de Exchange del usuario se ha habilitado

- Si el usuario está habilitado en Skype Empresarial Online

No puede producir fácilmente un informe de este tipo en el Centro de administración de Microsoft 365. En su lugar, tendría que crear un documento independiente para almacenar la información, como una hoja Excel hoja de cálculo. A continuación, obtenga todos los nombres de usuario y la información de licencias de Centro de administración de Microsoft 365, obtenga información del buzón del Centro de administración de Exchange Skype Empresarial, obtenga información en línea del Centro de administración de Skype Empresarial Online y, a continuación, combine esa información.

La alternativa es usar un script de PowerShell para compilar el informe por usted.

El siguiente script de ejemplo es más complicado que los comandos que ha visto hasta ahora en este artículo. Sin embargo, muestra el potencial de usar PowerShell para crear vistas de información que son difíciles de obtener de lo contrario. Este es el script para compilar y mostrar la lista que necesita:

```powershell
$x = Get-AzureADUser

foreach ($i in $x)
    {
      $y = Get-Mailbox -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled

      $y = Get-CsOnlineUser -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled
    }

$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB
```

Este es un ejemplo de los resultados:

```powershell
DisplayName             IsLicensed   IsMailboxEnabled   EnabledForSfB
-----------             ----------   ----------------   --------------
Bonnie Kearney          True         True               True
Fabrice Canel           True         True               True
Brian Johnson           False        True               False
Anne Wallace            True         True               True
Alex Darrow             True         True               True
David Longmuir          True         True               True
Katy Jordan             False        True               False
Molly Dempsey           False        True               False
```

La interpretación de este script de PowerShell es:

1. Obtener todos los usuarios de la suscripción Microsoft 365 actual y almacenar la información en una variable denominada *$x* (**$x = Get-AzureADUser**).
1. Inicie un bucle que se ejecute en todos los usuarios de la variable $x (**foreach ($i en $x).**
1. Defina una variable denominada *$y* y almacene la información del buzón del usuario en ella (**$y = Get-Mailbox -Identity $i.UserPrincipalName**).
1. Agregue una nueva propiedad a la información del usuario denominada *IsMailBoxEnabled*. Estadúdlo en el valor de la propiedad IsMailBoxEnabled del buzón del usuario (**$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).
1. Defina una variable denominada *$y* y almacene la información de Skype Empresarial Online del usuario en ella (**$y = Get-CsOnlineUser -Identity $i.UserPrincipalName**).
1. Agregue una nueva propiedad a la información del usuario denominada *EnabledForSfB*. Estabózcalo en el valor de la propiedad Enabled de la información de Skype Empresarial Online del usuario (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**).
1. Mostrar la lista de usuarios, pero incluir solo su nombre, si tienen licencia y las dos nuevas propiedades que indican si su buzón está habilitado y si están habilitados para Skype Empresarial Online (**$x | Seleccione DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**).

## <a name="see-also"></a>Vea también

[Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)

[Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

[Usar Windows PowerShell para crear informes en Microsoft 365](use-windows-powershell-to-create-reports-in-microsoft-365.md)