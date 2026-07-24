## API reference

| API | Type | Description |
| --- | :-: | --- |
| `VRPaymentSdk.init(listener: OnResultEventListener)` | function | Initializes the SDK and registers the result listener. Must be called before using `VRPaymentSdk.instance`. |
| `VRPaymentSdk.instance` | singleton | Shared SDK instance used for configuration and launching payments. |
| `OnResultEventListener` | interface | Interface for handling post-payment events (`paymentResult`). |
| `fun paymentResult(paymentResult: PaymentResult)` | function | Callback invoked when transaction state changes or payment is completed. |
| `VRPaymentSdk.instance?.launch(token: String, context: Context)` | function | Opens the payment flow. |
| `VRPaymentSdk.instance?.launch(token: String, context: Context, paymentMethodConfigurationId: Int? = null)` | function | Opens the payment flow. `paymentMethodConfigurationId` is optional and can be used to preselect a payment method. |
| `VRPaymentSdk.instance?.setDarkTheme(theme: JSONObject)` | function | Overrides or extends the default dark theme colors. |
| `VRPaymentSdk.instance?.setLightTheme(theme: JSONObject)` | function | Overrides or extends the default light theme colors. |
| `VRPaymentSdk.instance?.setCustomTheme(theme: JSONObject?, baseTheme: ThemeEnum)` | function | Forces a custom theme regardless of system appearance. Missing values are merged with the selected base theme. |
| `VRPaymentSdk.instance?.setAnimation(type: AnimationEnum)` | function | Sets transition animation style used inside the payment flow. |
| `VRPaymentSdk.instance?.SDK_VERSION` | property | Current SDK version. |
