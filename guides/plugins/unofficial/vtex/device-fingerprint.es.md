# Configuración de fingerprint

**Mercado Pago** tiene sus propias herramientas de prevención de fraude. **Device Fingerprint** es un identificador que actúa en el procesamiento de un pago, con el objetivo de mejorar el análisis del riesgo de fraude en cada transacción.

Siempre que sea posible, te recomendamos que envíes información sobre el comportamiento del cliente para detectar movimientos inusuales y evitar transacciones fraudulentas. No te preocupes, cuidamos los datos de tus clientes y no los compartimos con nadie.

**Para configurar device fingerprint**, sigue los pasos a continuación:

1. En el panel de administración de tu tienda, selecciona la opción **Checkout** del módulo **Configuración de la Tienda**.
2. Haz clic en el ícono **editar**, referente a la configuración de tu site.
3. Selecciona la pestaña **Código** y haz clic en **checkout6-custom.js** del módulo **Arquivos**.
4. Copia y pega el siguiente código y haz clic en **Guardar**.

```javascript
var script = document.createElement("script");
script.src = "https://www.mercadopago.com/v2/security.js";
script.setAttribute("output","vtex.deviceFingerprint");
script.setAttribute("view","checkout");
document.body.appendChild(script);
```

![Configuración de fingerprint](/images/vtex/devicefingerprint-es.gif)

> LEFT_BUTTON_RECOMMENDED_PT
>
> Verificación de logs
>
> Conoce los principales logs de VTEX.
>
> [Verificación de logs](https://www.mercadopago[FAKER][URL][DOMAIN]/developers/pt/guides/plugins/unofficial/vtex/logs)