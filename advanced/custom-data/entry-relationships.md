# Entry Relationships

When you create a field that uses `relationship` as a `field_type`, you update your entry values using the Relationship endpoints.

{% api-method method="post" host="https://api.moltin.com" path="/v2/flows/:flowSlug/entries/:entryId/relationships/:fieldSlug" %}
{% api-method-summary %}
Create Entry Relationship
{% endapi-method-summary %}

{% api-method-description %}
Create an Entry relationship to one or more resources. If any relationships already exist, the one's made in the request will be added to them.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="fieldSlug" type="string" required=true %}
The slug of the entry this field belongs to
{% endapi-method-parameter %}

{% api-method-parameter name="entryId" type="string" required=true %}
The **ID** of the entry this field belongs to
{% endapi-method-parameter %}

{% api-method-parameter name="flowSlug" type="string" required=true %}
The slug of the flow the entry belongs to
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
The Bearer token used to access the API.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="data.id" type="string" required=false %}
The **ID** of the related resource.
{% endapi-method-parameter %}

{% api-method-parameter name="data.type" type="string" required=false %}
Represents the resource type of the object
{% endapi-method-parameter %}

{% api-method-parameter name="data" type="object" required=false %}
Data to be stored
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "data": [
        {
            "type": "brand",
            "id": "0d28e5b6-f615-4e1c-b038-275cfde97927"
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="warning" %}
Replace the relationships between an entry and a resource. Unlike a `POST` to this endpoint, a `PUT` overrides any existing relationships.
{% endhint %}

{% api-method method="put" host="https://api.moltin.com" path="/v2/flows/:flowSlug/entries/:entryId/relationships/:fieldSlug" %}
{% api-method-summary %}
Update Entry Relationship\(s\)
{% endapi-method-summary %}

{% api-method-description %}
Replace the relationships between an entry and a resource. Unlike a `POST` to this endpoint, a `PUT` overrides any existing relationships
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="fieldSlug" type="string" required=true %}
The slug of the Flow the entry belongs to
{% endapi-method-parameter %}

{% api-method-parameter name="entryId" type="string" required=true %}
The **ID** of the entry this field belongs to
{% endapi-method-parameter %}

{% api-method-parameter name="flowSlug" type="string" required=true %}
The slug of the entry this field belongs to
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
The Bearer token used to access the API
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="data.id" type="string" required=false %}
The ID of the related resource
{% endapi-method-parameter %}

{% api-method-parameter name="data.type" type="string" required=false %}
Represents the resource type of the object
{% endapi-method-parameter %}

{% api-method-parameter name="data" type="object" required=false %}
Data to be stored
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "data": [
        {
            "type": "brand",
            "id": "0d28e5b6-f615-4e1c-b038-275cfde97927"
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="warning" %}
Removing a relationship between an entry and resource\(s\) deletes the relationships specified in the payload.
{% endhint %}

{% api-method method="delete" host="https://api.moltin.com" path="/v2/flows/:flowSlug/entries/:entryId/relationships/:fieldSlug" %}
{% api-method-summary %}
Delete Entry Relationships
{% endapi-method-summary %}

{% api-method-description %}
Remove all relationships between an entry and resources
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="fieldSlug" type="string" required=true %}
The slug of the entry this field belongs to
{% endapi-method-parameter %}

{% api-method-parameter name="entryId" type="string" required=true %}
The **ID** of the entry this field belongs to
{% endapi-method-parameter %}

{% api-method-parameter name="flowSlug" type="string" required=true %}
The slug of the Flow the entry belongs to
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
The Bearer token to grant access to the API
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=204 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

