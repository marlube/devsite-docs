# Ocultar botón de pago

| Brick  | Card Payment Form  |
| --- | --- |
| Momento de personalización  |  Al renderizar el brick  |
| Propiedad  | customization.visual.hidePaymentButton  |
| Tipo  | Boolean  |
| Observaciones  | Cuando true, el botón de envío del formulario no se muestra y pasa a ser necesario usar la función getCardFormData para obtener los datos del formulario (ver el ejemplo a continuación).  |

```javascript
const settings = {
    ...,
    callbacks: {
        onReady: () => {
            // callback chamado quando o Brick estiver pronto
        },
        onError: (error) => { 
            // callback chamado para todos os casos de erro do Brick
        },
    },
    customization: {
        visual: {
            hidePaymentButton: true
        }
    }
}
```

```html
<button type="button" onclick="createPayment();">Custom Payment Button</button>
```

```javascript
function createPayment(){
    window.cardPaymentBrickController.getFormData()
        .then((cardFormData) => {
            console.log('cardFormData received, creating payment...');
            fetch("/process_payment", {
                method: "POST",
                headers: {
                    "Content-Type": "application/json",
                },
                body: JSON.stringify(cardFormData),
            })
        })
        .catch((error) => {
            // tratamiento de error al intentar llamar getFormData()
        });
};
```

> PREV_STEP_CARD_ES
>
> Configurar la cantidad máxima y mínima de cuotas
>
> Si lo deseas, puedes configurar la cantidad máxima y mínima de cuotas. Aprende cómo.
>
> [Configurar cantidad máxima y mínima de cuotas](/developers/es/docs/checkout-bricks-beta/additional-customization/max-and-min-installments)

> NEXT_STEP_CARD_ES
>
> Ocultar títulos y banderas
>
> Además, si lo deseas, puedes ocultar los títulos de la UI y las banderas admitidas en Card Payment Brick.
>
> [Ocultar títulos y banderas](/developers/es/docs/checkout-bricks-beta/additional-customization/hide-title-and-flags)