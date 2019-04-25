<a name="crit-networking-step1"></a>
### <a name="required-your-network-is-ready-for-microsoft-365-enterprise"></a>Obligatorio: la red está preparada para Microsoft 365 Enterprise

- Las oficinas tienen suficiente ancho de banda de internet para el tráfico de Microsoft 365, incluidas la instalación y las actualizaciones de Office 365, Microsoft Intune y Windows 10 Enterprise
- La red general se corresponde a una arquitectura de referencia de Office 365
- Los cambios de la red han sido pilotados y probados y cumplen con los requisitos de latencia de tráfico

Si es necesario, el [paso 1](../networking-provide-bandwidth-cloud-services.md) puede ayudarle con este requisito.

<a name="crit-networking-step2"></a>
### <a name="required-your-local-offices-have-local-internet-connections-and-name-resolution"></a>Obligatorio: las oficinas locales tienen conexión a Internet local y resolución de nombres

Ha configurado cada oficina local con acceso a Internet con un ISP local cuyos servidores DNS usan una dirección IP pública local que identifica su ubicación en Internet. Esto asegura el mejor rendimiento posible para los usuarios que accedan a Office 365 e Intune.

Si no usa un ISP local para cada sucursal, puede verse afectado el rendimiento porque el tráfico de red debe recorrer la estructura de una organización o las solicitudes de datos se procesan mediante servidores front-end remotos.

#### <a name="how-to-test"></a>Cómo probarlo
Use una herramienta o un sitio web desde un dispositivo de esa oficina para determinar la dirección IP pública que está usando el servidor proxy. Por ejemplo, use la página web [What Is My IP Address](https://www.whatismypublicip.com/) (¿Cuál es mi dirección IP?). Esta dirección IP pública asignada por su ISP debería ser geográficamente local. No debe ser de un intervalo de direcciones IP público de una oficina central ni de un proveedor de seguridad de red basado en la nube.

Si es necesario, el [paso 2](../networking-dns-resolution-same-location.md) puede ayudarle con este requisito.

<a name="crit-networking-step3"></a>
### <a name="optional-unneeded-network-hairpins-are-removed"></a>Opcional: eliminación de las redirecciones de red innecesarias

Ha examinado las redirecciones de red y ha determinado su impacto en el rendimiento de todas las oficinas. Ha eliminado las redirecciones de red cuando ha sido posible, o bien ha trabajado con su proveedor de red o seguridad de terceros para implementar emparejamiento de Microsoft 365 óptimo para su red.

Si es necesario, el [paso 3](../networking-avoid-network-hairpins.md) puede ayudarle con esta opción.


<a name="crit-networking-step4"></a>
### <a name="optional-you-have-configured-traffic-bypass-on-your-internet-browsers-and-edge-devices"></a>Opcional: ha configurado la omisión de tráfico en los exploradores de Internet y los dispositivos perimetrales

Ha implementado los archivos PAC más recientes en los navegadores de Internet locales para que el tráfico a los nombres de dominio DNS de Microsoft 365 omitan los servidores proxy.

Ha configurado los dispositivos de red perimetrales, como firewalls, la inspección e interrupción SSL y los dispositivos de inspección de paquetes, para usar la omisión de tráfico o procesar de forma mínima el tráfico a las categorías Optimizar y Permitir de los puntos de conexión de Microsoft 365.


#### <a name="how-to-test"></a>Procedimiento de prueba

Use las herramientas de registro de los dispositivos perimetrales de red para asegurarse de que el tráfico a los destinos de Microsoft 365 no se inspecciona, descifra u obstaculiza de otra manera.

Si es necesario, el [paso 4](../networking-configure-proxies-firewalls.md) puede ayudarle con esta opción.


<a name="crit-networking-step5"></a>
### <a name="optional-your-clients-and-office-365-applications-are-configured-for-optimal-performance"></a>Opcional: sus clientes y aplicaciones de Office 365 están configurados para un rendimiento óptimo

Ha optimizado la configuración del Protocolo de control de transmisión (TCP) en los dispositivos cliente y para los servicios de Exchange Online, Skype Empresarial Online, SharePoint Online y Project Online.

Si necesita ayuda con esta opción, vea el [paso 5](../networking-optimize-tcp-performance.md).
