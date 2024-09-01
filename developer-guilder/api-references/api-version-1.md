# API Version 1

## Pearl ID

### Create a new pearl ID

<mark style="color:green;">`POST`</mark> `/auth/api/v1/did/create`

Create a new pearl ID.

**Headers**

| Name         | Value              |
| ------------ | ------------------ |
| Content-Type | `application/json` |

**Body**

<table><thead><tr><th width="205">Name</th><th width="113" data-type="checkbox">Required</th><th width="541">Value</th></tr></thead><tbody><tr><td>id</td><td>true</td><td>A string that conforms to the rules in <a href="https://z0hqbo7agth.feishu.cn/wiki/KYKqww8ALiuc2skZJCfcaOfmnpd#IZFpdc1y8ovNUxxLVkIckNAJnXf">DID definition</a></td></tr><tr><td>version</td><td>true</td><td>Interger value</td></tr><tr><td>created</td><td>false</td><td>Datetime with format <code>yyyy-MM-DDTHH:mm:ss.SSST</code></td></tr><tr><td>updated</td><td>false</td><td>Datetime with format <code>yyyy-MM-DDTHH:mm:ss.SSST</code></td></tr><tr><td>authentication</td><td>true</td><td>A set of <a href="https://z0hqbo7agth.feishu.cn/wiki/KYKqww8ALiuc2skZJCfcaOfmnpd#CujFdDZCXop6VQxGWSsc3Q3jnge">VerificationMethod</a> id</td></tr><tr><td>recovery</td><td>false</td><td>A set of <a href="https://z0hqbo7agth.feishu.cn/wiki/KYKqww8ALiuc2skZJCfcaOfmnpd#CujFdDZCXop6VQxGWSsc3Q3jnge">VerificationMethod</a> id</td></tr><tr><td>verificationMethod</td><td>false</td><td>PublicKey's ID must conform to the rule:<code>id#key-{index}</code></td></tr><tr><td>proof</td><td>false</td><td>An object of <a href="https://z0hqbo7agth.feishu.cn/wiki/KYKqww8ALiuc2skZJCfcaOfmnpd#K8p1dBaMSogaJ1xmpfLcvWlWn6b">Proof</a></td></tr></tbody></table>

**Request Example**

```json
{
  "@context": "https://w3id.org/did/v1", // fixed value
  "id": "did:protocols:<method-specific-id>"
  "version": 1,
  "createdAt": "2024-08-13T12:00:00Z",
  "updatedAt": "2024-08-13T12:00:00Z"
  "verificationMethod": [
    {
      "id": "#keys-1",
      "type": "Secp256k1",
      "publicKeyHex": "xxxx"},
    {
      "id": "#keys-2",
      "type": "Secp256k1",
      "publicKeyHex": "xxx"}
  ],
  "authentication": ["#key-1"],
  "recovery": ["#key-2"]
  "proof": {
            "type": "Secp256k1",
            "creator": "did:xxx:xxx#key-1",
            "signatureValue": "xxx"
  }
}
```

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  "id": 1,
  "name": "John",
  "age": 30
}
```
{% endtab %}
{% endtabs %}
