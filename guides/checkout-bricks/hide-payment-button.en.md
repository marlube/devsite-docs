# Hide payment button

| Brick  | Card Payment Form  |
| --- | --- |
| Customization moment  | When rendering the brick  |
| Property  | customization.visual.hidePaymentButton  |
| Type  | Boolean  |
| Comments  | When true, the form submit button is not displayed and it becomes necessary to use the getCardFormData function to get the form data (see example below). |

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
            // error handling when calling getFormData()
        });
};
```

> PREV_STEP_CARD_EN
>
> Set up the maximum and minimum number of installments
>
> Check how to set up the maximum and minimum number of installments allowed in Card Payment Brick.
>
> [Set up the maximum and minimum number of installments](/developers/en/docs/checkout-bricks-beta/additional-customization/max-and-min-installments)

> NEXT_STEP_CARD_EN
>
> Hide UI titles and card brands
>
> Learn how you can hide the UI titles and the card brands in Card Payment Brick.
>
> [Hide UI titles and card brands](/developers/en/docs/checkout-bricks-beta/additional-customization/hide-title-and-flags)