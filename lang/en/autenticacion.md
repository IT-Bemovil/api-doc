# Authentication

### API Stages

#### Production environment

Production URL for making real transactions

{% hint style="info" %}
https://apiv2.bemovil.net
{% endhint %}

#### Sandbox environment

Testing URL for conducting test transactions

{% hint style="info" %}
https://apiv2.sandbox.bemovil.net
{% endhint %}

### Authorization

The authentication method will be via headers in the "Authorization" field, with the token provided by the company.

```json
{
  "Headers": {
    "Authorization": "Bearer TOKEN"
  }
}
```
